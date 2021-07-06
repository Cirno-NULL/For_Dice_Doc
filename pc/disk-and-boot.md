# 磁盘和引导

## 一些很有价值的相关文章

正在整理中

* [BIOS, UEFI, MBR, Legacy, GPT等概念整理](https://zhuanlan.zhihu.com/p/36976698)
  * （2018年）
  * 基础，概念性扫盲
  * 名词解释+扩展介绍
  * 没有覆盖所有的名词，新手向简单科普
* [科普贴：BIOS和UEFI的启动项](https://zhuanlan.zhihu.com/p/31365115)
  * （2018年）
  * 进阶，详解引导原理和过程
  * 目前看的半懂不懂的
* [BIOS、MBR、PBR等基础知识](https://blog.csdn.net/huangxy10/article/details/8166802)
  * （2012年）
  * 进阶，有很多扩展内容
  * 主要详解MBR格式硬盘的开机流程
  * 没有GPT内容，注意时间
* [关于UEFI启动+GPT分区的一些经验](https://zhuanlan.zhihu.com/p/37977078)
  * （2018年）
  * 细节性经验书
  * 目前看的半懂不懂的

## 暂时没看明白有待整理的一些碎片和一些想法

* 目前上面的所有东西都没看懂没法整理

## 磁盘分类

| 磁盘分类（未记录全部） |
| :--- |
| SSD（固态硬盘） |
| HDD（传统硬盘） |
| HHD（混合硬盘） |

## 磁盘引导格式

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x78C1;&#x76D8;&#x5F15;&#x5BFC;</th>
      <th style="text-align:left">GPT</th>
      <th style="text-align:left">MBR</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#x53EF;&#x652F;&#x6301;&#x6570;&#x91CF;</td>
      <td style="text-align:left">&#x6700;&#x591A;18EB</td>
      <td style="text-align:left">&#x6700;&#x591A;2TB</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x5206;&#x533A;&#x6570;&#x91CF;</td>
      <td style="text-align:left">
        <p>&#x51E0;&#x4E4E;&#x65E0;&#x9650;&#x5236;</p>
        <p>&#x76EE;&#x524D;windows&#x4EC5;&#x652F;&#x6301;&#x6700;&#x5927;128&#x4E2A;&#x5206;&#x533A;</p>
        <p>&#xFF08;2021&#x5E74;07&#x6708;&#xFF09;</p>
      </td>
      <td style="text-align:left">&#x4E3B;&#x5206;&#x533A;&#x6700;&#x591A;&#x56DB;&#x4E2A;</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>&#x4E3B;&#x5F15;&#x5BFC;&#x5206;&#x533A;</p>
        <p>&#xFF08;&#x53EF;&#x80FD;&#x4E0E;&#x4E8B;&#x5B9E;&#x6709;&#x51FA;&#x5165;&#xFF09;</p>
      </td>
      <td style="text-align:left">ESP&#x5206;&#x533A;</td>
      <td style="text-align:left">&#x975E;&#x9690;&#x85CF;&#x6D3B;&#x52A8;&#x4E3B;&#x5206;&#x533A;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x5206;&#x533A;&#x540D;&#x5B57;&#x957F;&#x5EA6;</td>
      <td style="text-align:left">&#x6700;&#x957F;72&#x5B57;&#x8282;</td>
      <td style="text-align:left">&#x6CA1;&#x67E5;&#x5230;&#xFF0C;&#x8C8C;&#x4F3C;16&#x5B57;&#x8282;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x7CFB;&#x7EDF;&#x5F15;&#x5BFC;</td>
      <td style="text-align:left">&#x652F;&#x6301;UEFI&#x548C;Legacy</td>
      <td style="text-align:left">&#x652F;&#x6301;Legacy</td>
    </tr>
  </tbody>
</table>

## 系统引导格式

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x7CFB;&#x7EDF;&#x5F15;&#x5BFC;</th>
      <th style="text-align:left">UEFI</th>
      <th style="text-align:left">Legacy</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#x78C1;&#x76D8;&#x5206;&#x533A;&#x683C;&#x5F0F;</td>
      <td style="text-align:left">
        <p>&#x53EF;&#x4EE5;&#x8BC6;&#x522B;MBR&#x548C;GPT&#x683C;&#x5F0F;&#x5206;&#x533A;</p>
        <p>&#xFF08;&#x53EF;&#x80FD;&#x5B58;&#x5728;&#x4E8B;&#x5B9E;&#x6027;&#x9519;&#x8BEF;&#xFF09;</p>
      </td>
      <td style="text-align:left">
        <p>&#x65E0;&#x6CD5;&#x8BC6;&#x522B;GPT&#x683C;&#x5F0F;&#x5206;&#x533A;</p>
        <p>&#xFF08;&#x53EF;&#x80FD;&#x5B58;&#x5728;&#x4E8B;&#x5B9E;&#x6027;&#x9519;&#x8BEF;&#xFF09;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>&#x5F15;&#x5BFC;&#x5206;&#x533A;</p>
        <p>&#xFF08;&#x6216;&#x8005;&#x8BF4;&#x5F15;&#x5BFC;&#x6587;&#x4EF6;&#x4F4D;&#x7F6E;&#xFF09;</p>
        <p>&#xFF08;&#x53EF;&#x80FD;&#x4E0E;&#x4E8B;&#x5B9E;&#x6709;&#x51FA;&#x5165;&#xFF09;</p>
      </td>
      <td style="text-align:left">
        <p>ESP&#x5206;&#x533A;</p>
        <p>&#x5E76;&#x4E14;&#x5B58;&#x5728;&#x81F3;&#x5C11;&#x4E00;&#x4E2A;&#x4E3B;&#x5206;&#x533A;</p>
      </td>
      <td style="text-align:left">&#x975E;&#x9690;&#x85CF;&#x6D3B;&#x52A8;&#x4E3B;&#x5206;&#x533A;</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>&#x7CFB;&#x7EDF;&#x5206;&#x533A;</p>
        <p>&#xFF08;&#x53EF;&#x80FD;&#x4E0E;&#x4E8B;&#x5B9E;&#x6709;&#x51FA;&#x5165;&#xFF09;</p>
      </td>
      <td style="text-align:left">
        <p>&#x5F3A;&#x5236;&#x8981;&#x6C42;</p>
        <p><b>&#x7CFB;&#x7EDF;&#x542F;&#x52A8;&#x6587;&#x4EF6;</b>&#x4E0E;<b>&#x7CFB;&#x7EDF;&#x6587;&#x4EF6;</b>
        </p>
        <p>&#x5FC5;&#x987B;&#x653E;&#x5728;&#x4E0D;&#x540C;&#x5206;&#x533A;</p>
      </td>
      <td style="text-align:left">&#x53EF;&#x4EE5;&#x653E;&#x5728;&#x540C;&#x4E00;&#x4E2A;&#x5206;&#x533A;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x754C;&#x9762;</td>
      <td style="text-align:left">&#x53EF;&#x4EE5;&#x505A;&#x6210;&#x56FE;&#x5F62;&#x5316;&#x754C;&#x9762;</td>
      <td
      style="text-align:left">&#x2014;&#x2014;&#x65E0;&#x6B64;&#x6982;&#x5FF5;&#x2014;&#x2014;</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>&#x5F15;&#x5BFC;&#x6587;&#x4EF6;</p>
        <p>&#x8C8C;&#x4F3C;&#x662F;windows&#x7684;</p>
      </td>
      <td style="text-align:left">efi&#x5F15;&#x5BFC;&#x6587;&#x4EF6;</td>
      <td style="text-align:left">bcd&#x5F15;&#x5BFC;&#x6587;&#x4EF6;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x53EF;&#x80FD;&#x8FD8;&#x6709;&#x66F4;&#x591A;&#x7684;&#x533A;&#x522B;</td>
      <td
      style="text-align:left">&#x4F46;&#x662F;&#x6211;&#x80FD;&#x67E5;&#x5230;&#x7684;&#x5C31;&#x8FD9;&#x4E9B;</td>
        <td
        style="text-align:left">&#x6240;&#x4EE5;&#x5C31;&#x8FD9;&#x6837;&#x4E86;</td>
    </tr>
  </tbody>
</table>

## 已知的MBR格式硬盘Windows引导修复方式：

1. 找到一个PE盘
2. 修改bcd引导文件所在盘符为活动主分区
3. 修改bcd引导文件条目至正确的磁盘路径
4. 改完了，重启吧

## 不会用的Ubuntu系统修复方式：

```text
sudo add-apt-repository ppa:yannubuntu/boot-repair && sudo apt-get update
sudo apt-get install -y boot-repair && boot-repair
boot repair
```

* 这到底是拿来修复什么东西的？
* 为啥修了半天一点正常反应都没有？

## 可用的多系统U盘制作工具

* [Ventoy](https://github.com/ventoy/Ventoy/)
  * 开源，免费
  * 使用前先调整一下默认设置，按需更改

