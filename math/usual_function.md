# 整式运算

## 基础平方公式

1.  表格

    $$
    \def\array stretch{} \begin{array}{l:l:c:c} 类型 & 公式 \\\hdashline 平方差公式： & (a+b)(a-b) = a^2-b^2 \\ \hdashline 平方差公式： & (a+b)^2 = a^2 +2ab + b^2 \\ & (a-b)^2 = a^2-2ab+b^2 \\\end{array}
    $$
2.  例题：

    $$
    x^2 + y^2 = 3 ， xy = 1 ， 求x-y
    $$

    $$
    \def\array stretch{} \begin{array}{r:l:c:c} 题解\\\hdashline (a-b)^2 & = a^2 - 2ab + b^2\\ ·&= 3-2\\ ·&= 1\\ \\\hdashline \because\sqrt[2]{1^{2}}\\ \therefore ans &= \pm1 \end{array}
    $$

## 整式运算

1.  表格

    $$
    \def\array stretch{} \begin{array}{l:l:l:l} 类型 & 公式 & 示例 \\\hdashline 合并同类项： & ax^2y+bx^y=(a+b)x^2y & 3x^2y+7x^2y \\ &&=(3+7)x^2y\\ &&=10x^2y\\\hdashline 单项式乘单项式： & ax^2y^3·bxy^2=abx^3y^5 & 3x^2y^3·5xy^2 \\ &&=15x^3y^5\\\hdashline 单项式乘多项式：& p(a+b+c)=pa+pb+pc & \\\hdashline 多项式乘多项式： & (a+b)(p+q)=ap+aq+bp+bq & \\\hdashline 单项式除以单项式： & 把\left[\large系数\right]与\left[\large同底数幂\right]分别相除 & 9a^3b^2/3a^2b^2 \\ &作为商的因式，对于只在被除式里&=3a\\ &含有的字母,则连同它的指数作为&27a^{10}b^5/9a^3b^2\\ &商的一个因式 & =3a^7b3 \\\hdashline 多项式除以单项式： &(am+bm)/m\\ &=am/m+bm/m\\ &=a+b \\\hdashline \end{array}
    $$
    单项式的次数和是各个位置的次数量相加

## 因式分解

$$
\def\array stretch{} 
\begin{array}{l:l:c:c} 
类型 & 公式 \\\hdashline 
提公因式法： & ma+mb+mc = m(a+b+c) \\ \hdashline 
公式法： & 完全平方公式：&a^2-b^2 = (a+b)(a-b) \\ 
& 完全平方公式：&a^2+2ab+b^2=(a+b)^2 \\ 
&&a^2-2ab+b^2=(a-b)^2\\\hdashline 
\end{array}
$$

如果多项式各项有公因式，应首先**提取公因式**，      
然后再利用**公式法**分解因式，      
因式分解必须分解到每一个多项式不能再分解为止    

例题：
$$
\def\array stretch{} 
\begin{array}{r:l:l:c} 
 例1：&ma^2+2mab+mb^2&\\
= & m(a^2+2ab+b^2) \\ 
= & m(a+b)^2 \\\hdashline
例2：&(1+a)(1-a)+a(a-2)& a=\frac{1}{2} \\
=&1^2-a^2+a^2-2a\\
=&1-2a\\
&代入a\frac{1}{2}\\
原式=&1-2*\frac{1}{2}=0\\\hdashline
例3：&(x+y)*(x-y)-(4x^3y-8xy^3)/2xy&x=-1,y=\frac{\sqrt{3}}{3}\\
=&x^2-y^2-4xy(x^2-2y^2)/2xy&这里化简的时候\\
=&x^2-y^2-2(x^2-2y^2)&-2y^2容易漏掉2\\
=&x^2-y^2-2x^2+4y^2\\
=&-x^2+3y^2\\
&代入x=-1，y=\frac{\sqrt{3}}{3}\\
原式=&-(-1)^2+3*(\frac{\sqrt{3}}{3})^2\\
=&-1+3(\frac{\sqrt{9}}{9})\\
=&-1+1\\
=&0\\\hdashline
例4：&(a+b)(a-b)+b(a+2b)-b^2&a=1,b=-2\\
=&a^2-b^2+ab+2b^2-b^2\\
=&a^2+ab\\
&代入a=1，b=-2\\
原式=&1-2\\
=&-1\\\hdashline
例5：&若a-b=1，求a^2-b^2-2b\\
=&(a+b)(a-b)-2b\\
=&a+b-2b\\
=&a-b\\
=&1\\\hdashline
例6：&(-x^2+5x+4)+(5x-4+2x^2)&x=-2\\
=&(-x^2+5x+4)+(2x^2+5x-4)\\
=&x^2+10x\\
=&4-20\\
=&-16\\\hline&
多项式加减\\\hline
例1：&多项式A=(x+2)^2+(1-x)(2+x)-3\\
(1)&化简多项式A；\\
(2)&若(x+1)^2=6，求A的值。\\\hline
(1.1)\\
A=&x^2+4x+4+2+x-2x-x^2-3\\
=&3x+6-3&过于暴力\\
=&3x+3\\\hdashline
(1.2)\\
A=&(x+2)(x+2)+(1-x)(x+2)-3\\
=&(x+2)(x+2+1-x)-3\\
=&3*(x+2)-3&相对优雅\\
=&3x+6-3\\
=&3x+3\\\hdashline
(2)&由(1)有A=3(x+1)\\
\because&(x+1)^2=6\\
\therefore&(x+1)=\plusmn\sqrt{6}\\
&A=\pm3\sqrt6\\\hline
例2：&(x-1)(2x-1)-(x+1)^2+1&x^2-5x=3\\
=&2x^2-x-2x+1-(x^2+2x+1)+1\\
=&2x^2-3x+1-x^2-2x-1+1\\
=&x^2-5x+1\\
&代入x^2-5x=3\\
原式=&3+1\\
=4\\\hline
&多项式乘除\\\hline
例1：&(1-3a)^2-2(1-3a)&a=1\\\hdashline
=&(1-3a)(1-3a)-(2)(1-3a)\\
=&(1-3a)(1-3a-2)\\
=&(-2)(-4)\\
=&8\\\hline
例2：&a(a-2b)+2(a+b)(a-b)+(a+b)^2&a=-\frac{1}{2}，b=1\\\hdashline
=&a(a-2b)+2(a+b)(a-b)+(a+b)(a+b)\\
=&a(a-2b)+[2(a-b)+(a+b)](a+b)\\
=&a(a-2b)+[2a-2b+a+b](a+b)\\
=&a(a-2b)+(3a-b)(a+b)\\
=&a^2-2ab+3a^2+3ab-ab-b^2\\
=&4a^2-b^2\\
&由a=-\frac{1}{2}，b=1\\
原式=&4*(-\frac{1}{2})^2-(1)^2\\
= &1-1\\
=&0\\\hline
例3&8(x^2-2y^2)-x(7x+y)+xy\\\hdashline
=&8x^2-16y^2-7x^2-xy+xy\\
=&x^2-16y^2&不要到此为止\\
=&(x+4y)(x-4y)&还能继续到这\\\hline
\end{array}
$$





