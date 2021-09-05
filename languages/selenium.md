# Python使用selenium
## 导包
```py
from selenium import webdriver
from selenium.webdriver.support.select import Select
#从selenium库内导入webdriver包
```

## 最大化窗口
```py
browser = webdriver.Firefox() #browser为变量名
browser.maximize_window()
```

## 打开指定网页
```py
browser.get("https://www.baidu.com")
```

## 搜索指定元素
### 通过各种方法搜索指定元素
```py
browser.find_Element_by_id('kw')
browser.find_element_by_name('wd')
browser.find_element_by_class_name('s_ipt')
browser.find_element_by_tag_name('input')
browser.find_element_by_css_selector('span>input#kw.s_ipt[name="wd"]')
browser.find_element_by_link_text('新闻')
browser.find_element_by_partial_link_text('新')
browser.find_element_by_xpath('//span/input[@id="kw" and @class= "s_ipt" and @name="wd"]')
```
### 次级词缀
#### 输入字符串
```py
.send_keys("test")
```
#### 点击
```py
.click()
```

## 窗口
### 获取所有窗口
```py
handles = browser.window_handles
```
### 窗口跳转
```py
browser.switch_to.window(handles[1])
```
### 窗口信息
```py
print(browser.title)
```

## Switch_to
### Frame
进入与退出
```py
browser.switch_to.frame('iframeResult')
browser.switch_to.default_content()
```
### Alert
确认与取消
```py
browser.switch_to.alert.accept()
browser.switch_to.alert.dismiss()
browser.switch_to.default_content()
```

## Select
### 确认选择
```py
select = browser.find_element_by_name('cars')
is_selected = select.is_selected()
if is_selected == False:
    browser.find_element_by_name('cars').click()
```
### 选择方式
```py
Select(select).select_by_index(1)
#索引选择

Select(select).select_by_visible_text('Fiat')
#可见文本选择

Select(select).select_by_value('audi')
#value属性选择
```

## 悬浮框
```py
more = browser.find_element_by_name('tj_briicon')
ActionChains(browser).move_to_element(more).perform()
```

## 等待
### 强制等待
```py
Sleep(3)
```
### 隐性等待
```py
browser.implicitly_wait(5)
browser.find_element_by_id('kw').send_keys("A")
```
### 显性等待
```py
WebDriverWait(browser,5,1).until(
    expected_conditions.presence_of_all_elements_located(
        (By.ID,'kw1')
```

## 设置浏览器参数
```py
from selenium import webdriver
profile = webdriver.FirefoxProfile()
profile.set_preference('browser.download.folderList', 2)  # 设置下载路径模式   1 默认 2 自定义
profile.set_preference('browser.download.dir', 'D:\\')  # 指定下载路径
profile.set_preference('browser.download.manager.showWhenStarting', False)  # 下载时不显示下载器
profile.set_preference('browser.helperApps.neverAsk.saveToDisk', 'application/zip')  # 无需弹窗提醒  下载格式zip

browser = webdriver.Firefox(firefox_profile=profile)
```

## 浏览器上传下载
### 上传
```py
browser.find_element_by_id('file').send_keys('C:\\Users\\Administrator\\Desktop\\1.jpg')
#最劣写法
up = browser.find_element_by_id('file')
up.send_keys('C:\\Users\\Administrator\\Desktop\\1.jpg')
#更优写法
```
### 下载
```py
browser.find_element_by_link_text('testsaveas.zip').click()
```
## unittest
### 简介
unittest 单元测试框架  
步骤：1.首先导入unittest模块；  
      2.创建一个测试类，继承TestCase；  
      3.定义setUp和tearDown方法。  
      setUp是测试前的初始化工作；  
      tearDown是测试后的清除工作。  
      4.创建测试用例，测试用例方法的命名需要以test开头。  
      在测试用例中，需要添加断言来判断实际结果与预期是否相符。  
      5.调用unittest.main()启动测试。  
### 断言
```py
assertTrue(x，[msg])  #断言x是否True，是True则测试用例通过。bool(x)
assertFalse(x，[msg])  #断言x是否False，是False则测试用例通过。
assertIn(a,b，[msg])  #断言a是否在b中，在b中则测试用例通过。
assertNotIn(a,b，[msg])  #断言a是否在b中，不在b中则测试用例通过。
assertEqual(a,b，[msg])  #断言a和b是否相等，相等则测试用例通过。
assertNotEqual(a,b，[msg])  #断言a和b是否相等，不相等则测试用例通过。
#msg='测试失败时打印的信息',默认为none.
```
### 基础模板
```py
class DBShop(unittest.TestCase):  # 2
    def setUp(self):  # 3
        self.browser = webdriver.Firefox()
        self.browser.maximize_window()
        self.browser.get('http://localhost')

    def tearDown(self):  # 3
        self.browser.quit()

    def test_login_success(self):  # 4
        #省略无聊的输入步骤
        self.browser.find_element_by_class_name('btn-primary').click()
        #登录按钮
        self.assertTrue(self.browser.find_element_by_link_text('退出'))
        #断言:assertTrue

if __name__=='__main__':  # 5
    unittest.main()
```


## csv数据文件
### 导入包
```py
import scv
```
### 读取
```py
f = open('user.csv', mode='r', encoding='utf-8')
users = csv.reader(f)
for user in users:
    userName = user[0]
    passWord = user[1]
```


## ddt
### 流程
```py
import ddt
@ddt.ddt #TODO 查询啥意思
```
## 关闭浏览器
```py
browser.close()
browser.quit()
```
