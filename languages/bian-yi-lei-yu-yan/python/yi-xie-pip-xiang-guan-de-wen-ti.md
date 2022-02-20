# 一些pip相关的问题

### 代理问题

```
WARNING: Retrying (Retry(total=4, connect=None, read=None, redirect=None, status=None)) after connection broken by 'ProxyError('Cannot connect to proxy.', FileNotFoundError(2, 'No such file or directory'))': /simple/htmltestrunner/
WARNING: Retrying (Retry(total=3, connect=None, read=None, redirect=None, status=None)) after connection broken by 'ProxyError('Cannot connect to proxy.', FileNotFoundError(2, 'No such file or directory'))': /simple/htmltestrunner/
WARNING: Retrying (Retry(total=2, connect=None, read=None, redirect=None, status=None)) after connection broken by 'ProxyError('Cannot connect to proxy.', FileNotFoundError(2, 'No such file or directory'))': /simple/htmltestrunner/
WARNING: Retrying (Retry(total=1, connect=None, read=None, redirect=None, status=None)) after connection broken by 'ProxyError('Cannot connect to proxy.', FileNotFoundError(2, 'No such file or directory'))': /simple/htmltestrunner/
WARNING: Retrying (Retry(total=0, connect=None, read=None, redirect=None, status=None)) after connection broken by 'ProxyError('Cannot connect to proxy.', FileNotFoundError(2, 'No such file or directory'))': /simple/htmltestrunner/
```

解决方案出处：

[https://github.com/pypa/pip/issues/9216](https://github.com/pypa/pip/issues/9216#issuecomment-789683024)

> This is the original request method of PipSession:
>
> ```
> def request(self, method, url, *args, **kwargs):
>         # Allow setting a default timeout on a session
>         kwargs.setdefault("timeout", self.timeout)
>         
>         # Dispatch the actual request
>         return super().request(method, url, *args, **kwargs)
> ```
>
> If you make a breakpoint there you gonna see that self.proxies is corrected setted from --proxies, however, when the call to the parent class is made the proxies get lost and urllib set it from the system, which then gets the wrong scheme (https instead of http).
>
> An easy fix I suggest is to add the following line at the request method in the file `pi\_internal\network\session.py, line 419`:
>
> ```
> def request(self, method, url, *args, **kwargs):
>      # Allow setting a default timeout on a session
>      kwargs.setdefault("timeout", self.timeout)
>      kwargs.setdefault("proxies", self.proxies)  # fix problem with proxies.
>
>     # Dispatch the actual request
>     return super().request(method, url, *args, **kwargs)
> ```
>
> This way the proxies are carried out correctly to the request, if no proxy is set an empty dict is passed.
