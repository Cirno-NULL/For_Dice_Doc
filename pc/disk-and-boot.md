# 磁盘和引导

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
      <th style="text-align:left">MBR</th>
      <th style="text-align:left">GPT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#x53EF;&#x652F;&#x6301;&#x6570;&#x91CF;</td>
      <td style="text-align:left">&#x6700;&#x591A;2TB</td>
      <td style="text-align:left">&#x6700;&#x591A;18EB</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x5206;&#x533A;&#x6570;&#x91CF;</td>
      <td style="text-align:left">&#x4E3B;&#x5206;&#x533A;&#x6700;&#x591A;&#x56DB;&#x4E2A;</td>
      <td style="text-align:left">
        <p>&#x51E0;&#x4E4E;&#x65E0;&#x9650;&#x5236;</p>
        <p>&#x76EE;&#x524D;windows&#x4EC5;&#x652F;&#x6301;&#x6700;&#x5927;128&#x4E2A;&#x5206;&#x533A;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x6D3B;&#x52A8;&#x4E3B;&#x5206;&#x533A;&#x6570;&#x91CF;</td>
      <td style="text-align:left">&#x6700;&#x591A;&#x4E00;&#x4E2A;</td>
      <td style="text-align:left">&#x2014;&#x2014;&#x65E0;&#x6B64;&#x6982;&#x5FF5;&#x2014;&#x2014;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x5206;&#x533A;&#x540D;&#x5B57;&#x957F;&#x5EA6;</td>
      <td style="text-align:left">&#x6CA1;&#x67E5;&#x5230;&#xFF0C;&#x8C8C;&#x4F3C;16&#x5B57;&#x8282;</td>
      <td
      style="text-align:left">&#x6700;&#x957F;72&#x5B57;&#x8282;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x7CFB;&#x7EDF;&#x5F15;&#x5BFC;</td>
      <td style="text-align:left">&#x652F;&#x6301;Legacy</td>
      <td style="text-align:left">&#x652F;&#x6301;UEFI&#x548C;Legacy</td>
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
      <td style="text-align:left">&#x53EF;&#x4EE5;&#x8BC6;&#x522B;MBR&#x548C;GPT&#x683C;&#x5F0F;&#x5206;&#x533A;</td>
      <td
      style="text-align:left">&#x65E0;&#x6CD5;&#x8BC6;&#x522B;GPT&#x683C;&#x5F0F;&#x5206;&#x533A;</td>
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

## 未知的层面：

1. MBR转gpt以后Legacy引导会失去效果，那么怎么转至UEFI引导？
2. UEFI似乎无法和Legacy互转？
3. UEFI引导似乎有很多种？
4. PE启动盘似乎也能同时安装多种系统安装工具，但是不知道怎么制作

## 已知的MBR格式硬盘Windows引导修复方式：

1. 找到一个PE盘
2. 修改bcd引导文件所在盘符为活动主分区
3. 修改bcd引导文件条目至正确的磁盘路径
4. 改完了，重启吧

## 不知道为啥始终无效且无意义的Ubuntu系统修复方式：

```text
sudo add-apt-repository ppa:yannubuntu/boot-repair && sudo apt-get update
sudo apt-get install -y boot-repair && boot-repair
boot repair
```

1. 不知道为啥始终无法修复ubuntu自己的引导
2. 在只有ubuntu所在硬盘的情况下运行这个东西的自动修复
3. Ubuntu直接进不去了
4. UEFI格式似乎也无法修改
5. 貌似是修复Grub的工具
6. 所以GRUB是个啥玩意？



