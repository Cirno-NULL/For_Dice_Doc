# 磁盘和引导

| 磁盘分类（未记录全部） |
| :--- |
| SSD（固态硬盘） |
| HDD（传统硬盘） |
| HHD（混合硬盘） |

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
      style="text-align:left">&#x6CA1;&#x67E5;&#x5230;</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>&#x5F15;&#x5BFC;&#x6587;&#x4EF6;</p>
        <p>&#x8C8C;&#x4F3C;&#x662F;windows&#x7684;</p>
      </td>
      <td style="text-align:left">winload.efi</td>
      <td style="text-align:left">winload.exe</td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

然而这么多东西依旧没法解决怎么修复win系统引导

难道非要装一个pe系统到U盘里才能解决吗，rua！

