# 第五次作业 归结原理

## 一 用归结原理求解问题

**结论：李明有好身材。林丽是否有好身材，现有条件无法确定。**

### 1 谓词定义

论域为人，常量 $l$ 表示李明，$n$ 表示林丽。定义如下谓词。

| 谓词 | 含义 |
| --- | --- |
| $A(x)$ | $x$ 喜爱糖果 |
| $F(x)$ | $x$ 有好身材 |
| $E(x)$ | $x$ 吃掉南瓜 |
| $B(x)$ | $x$ 买了南瓜 |
| $C(x)$ | $x$ 雕刻南瓜 |
| $D(x)$ | $x$ 买了糖果 |

本题用一元谓词概括人的行为；第三条中的雕刻或吃掉，均指其购买的南瓜。

### 2 将已知条件表示为谓词公式

六条已知条件依次为：

$$
\forall x\,[A(x)\rightarrow\neg F(x)]
$$

$$
\forall x\,[E(x)\rightarrow F(x)]
$$

$$
\forall x\,[B(x)\rightarrow(C(x)\lor E(x))]
$$

$$
B(l)
$$

$$
D(n)
$$

$$
\neg C(l)
$$

### 3 化为子句集

利用 $P\rightarrow Q\equiv\neg P\lor Q$ 消去蕴含，省略全称量词，并将不同子句中的变量改名，得到：

$$
\begin{aligned}
C_1&:\quad\neg A(x_1)\lor\neg F(x_1)\\
C_2&:\quad\neg E(x_2)\lor F(x_2)\\
C_3&:\quad\neg B(x_3)\lor C(x_3)\lor E(x_3)\\
C_4&:\quad B(l)\\
C_5&:\quad D(n)\\
C_6&:\quad\neg C(l)
\end{aligned}
$$

以下各子句中的变量均默认全称量化。

### 4 归结证明

为证明李明有好身材，将待证结论 $F(l)$ 的否定加入子句集：

$$
C_7:\quad\neg F(l)
$$

按下列顺序归结。其中，$\theta$ 表示合一时使用的代换，$\Box$ 表示空子句。

1. 由 $C_3$ 与 $C_4$，取 $\theta_1=\{x_3\mapsto l\}$，消去互补文字，得：

   $$
   R_1:\quad C(l)\lor E(l)
   $$

2. 由 $R_1$ 与 $C_6$ 归结，得：

   $$
   R_2:\quad E(l)
   $$

3. 由 $C_2$ 与 $R_2$，取 $\theta_2=\{x_2\mapsto l\}$，归结得：

   $$
   R_3:\quad F(l)
   $$

4. 由 $R_3$ 与 $C_7$ 归结，得：

   $$
   R_4:\quad\Box
   $$

得到空子句，说明原已知条件与 $\neg F(l)$ 不相容，因此原已知条件蕴含 $F(l)$，即**李明有好身材**。

对林丽，题目只给出 $D(n)$，并未给出 $A(n)$，也没有“买糖果就喜爱糖果”的规则。因此，不能由购买糖果推出她喜爱糖果，更不能据此推出她没有好身材；现有条件既不能推出 $F(n)$，也不能推出 $\neg F(n)$。

## 二 用归结原理证明结论

### 1 英文题目翻译

1. 每个孩子都喜爱圣诞老人。
2. 任何喜爱圣诞老人的人都喜爱每一只驯鹿。
3. 鲁道夫是一只驯鹿，并且鲁道夫长着红鼻子。
4. 任何长着红鼻子的对象，要么是奇怪的，要么是小丑。
5. 没有驯鹿是小丑。
6. Serooge 不喜爱任何奇怪的对象。

**待证结论：Serooge 不是孩子。** 人名 Serooge 沿用原题拼写。

### 2 谓词与常量定义

论域包含人、驯鹿及题目涉及的其他对象。常量 $t$ 表示圣诞老人，$r$ 表示鲁道夫，$s$ 表示 Serooge。

| 谓词 | 含义 |
| --- | --- |
| $K(x)$ | $x$ 是孩子 |
| $L(x,y)$ | $x$ 喜爱 $y$ |
| $R(x)$ | $x$ 是驯鹿 |
| $N(x)$ | $x$ 长着红鼻子 |
| $W(x)$ | $x$ 是奇怪的 |
| $J(x)$ | $x$ 是小丑 |

### 3 将已知条件表示为谓词公式

六条已知条件依次为：

$$
\forall x\,[K(x)\rightarrow L(x,t)]
$$

$$
\forall x\forall y\,[(L(x,t)\land R(y))\rightarrow L(x,y)]
$$

$$
R(r)\land N(r)
$$

$$
\forall x\,[N(x)\rightarrow(W(x)\lor J(x))]
$$

$$
\forall x\,[R(x)\rightarrow\neg J(x)]
$$

$$
\forall y\,[W(y)\rightarrow\neg L(s,y)]
$$

待证结论为：

$$
\neg K(s)
$$

### 4 化为子句集

消去蕴含，使用德摩根律，将合取式拆为不同子句，再省略全称量词并将变量标准化，得：

$$
\begin{aligned}
C_1&:\quad\neg K(x_1)\lor L(x_1,t)\\
C_2&:\quad\neg L(x_2,t)\lor\neg R(y_2)\lor L(x_2,y_2)\\
C_3&:\quad R(r)\\
C_4&:\quad N(r)\\
C_5&:\quad\neg N(x_5)\lor W(x_5)\lor J(x_5)\\
C_6&:\quad\neg R(x_6)\lor\neg J(x_6)\\
C_7&:\quad\neg W(y_7)\lor\neg L(s,y_7)
\end{aligned}
$$

反证时，将结论 $\neg K(s)$ 的否定加入子句集：

$$
C_8:\quad K(s)
$$

### 5 归结过程

先由鲁道夫的性质推出 Serooge 不喜爱鲁道夫。

1. 由 $C_6$ 与 $C_3$，取 $\theta_1=\{x_6\mapsto r\}$，归结得：

   $$
   R_1:\quad\neg J(r)
   $$

2. 由 $C_5$ 与 $C_4$，取 $\theta_2=\{x_5\mapsto r\}$，归结得：

   $$
   R_2:\quad W(r)\lor J(r)
   $$

3. 由 $R_2$ 与 $R_1$ 归结，得：

   $$
   R_3:\quad W(r)
   $$

4. 由 $C_7$ 与 $R_3$，取 $\theta_3=\{y_7\mapsto r\}$，归结得：

   $$
   R_4:\quad\neg L(s,r)
   $$

再由反证假设推出 Serooge 喜爱鲁道夫。

5. 由 $C_1$ 与 $C_8$，取 $\theta_4=\{x_1\mapsto s\}$，归结得：

   $$
   R_5:\quad L(s,t)
   $$

6. 由 $C_2$ 与 $R_5$，取 $\theta_5=\{x_2\mapsto s\}$，归结得：

   $$
   R_6:\quad\neg R(y_2)\lor L(s,y_2)
   $$

7. 由 $R_6$ 与 $C_3$，取 $\theta_6=\{y_2\mapsto r\}$，归结得：

   $$
   R_7:\quad L(s,r)
   $$

8. 由 $R_7$ 与 $R_4$ 归结，得：

   $$
   R_8:\quad\Box
   $$

得到空子句，说明原已知条件与假设 $K(s)$ 不相容，故待证结论成立：

$$
\neg K(s)
$$

即 **Serooge 不是孩子**。
