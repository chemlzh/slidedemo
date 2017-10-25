class: center, middle

# 自我介绍

&nbsp;
&nbsp;

#### 李梓焓 (chemlzh@pku.edu.cn)  

主页: <https://github.com/chemlzh>

---

## 自我介绍

### 1. 学历

- 高中就读于：福建省漳平第一中学
- 现就读于：北京大学化学与分子工程学院

### 2. 兴趣爱好

- 化学
- 编程（主要是OI/ACM，不过目前没有打算参加ACM）
- 电子产品（略懂一点，千万不要老叫我修电脑或推荐产品）
- 弹钢琴（琴艺略菜，不敢在大佬前班门弄斧）
- ……

---

### 3. 个人优缺点

- 优点：热爱学习，对新事物有好奇心；对感兴趣或热爱的事物专注。
- 缺点：性子有时比较急；有点完美主义，有时做不出预期的效果会沮丧。

---

## 化学

#### 本人决定放刺尾鱼毒素（Maitotoxin）的键线式和填充模型来闪瞎你们的眼睛！
#### 这个分子的全合成连K.C.Nicolaou都没有完成，是成环学的圣杯！
#### <font color="red">侦测到在途的聚变打击！</font>

---

## 化学

<img src="https://upload.wikimedia.org/wikipedia/commons/4/4d/Maitotoxin_2D_structure.svg" height=287 width=800 style="margin: 0px 20px">

---

## 化学

<img src="https://upload.wikimedia.org/wikipedia/commons/e/e1/Maitotoxin-3D-vdW.png" height=386 width=800 style="margin: 0px 20px">

---

## OI之妙

#### OI不仅只是考察编程，还考察对数学模型的建构。许多OI题/OI题型的背后，都有很强的数学渊源  
#### 为了说明OI之妙，本人举这么一个例子

> “汉诺塔”，是一个众所周知的古老游戏。现在我们把问题稍微改变一下：如果一共有4根柱子， 而不是3根，那么至少需要移动盘子多少次，才能把所有的盘子从第1根柱子移动到第4根柱子上呢？  
> 为了编程方便，您只需要输出这个结果mod 10000的值。  

#### 三根柱子的汉诺塔我们都会做，但，四根呢？  
#### 实际上，这个问题可以推广到n（n>=3）根柱子的情形，而有可能成为全局最优的算法是Frame–Stewart算法。  
#### 2014年，Bousch证明了，对n=4的情形，Frame–Stewart算法是最优解。以下便是对该算法的大致解释和实现  

---

## OI之妙

根据英文wiki的资料，4-Hanoi tower满足递推公式：T[n,4]=T[k,4]*2+T[n-k,3],
其中T[i,j]表示初始时有i个盘,j个塔时所用的最少步数  
且k满足k=n-round(sqrt(2n+1))+1,round()表示四舍五入的函数  
故从1开始递增，连续运用以上递推式即可得出答案  

---

## OI之妙

```cpp
#include <algorithm>  
#include <cmath>  
#include <cstdio>  
#include <cstring>  
#include <iostream>  
#include <vector>  
#define REP(x,y,z) for (long i=x;i<=y;i+=z)  

using namespace std;
long N, a[50005], b[50005];

int main() {
	scanf("%ld", &N);
	b[1] = 2;
	for (long i = 2; i <= N; i++) b[i] = (b[i - 1] * 2) % 10000;
	for (long i = 1; i <= N; i++) {
		long k = i - (long)round(sqrt(2 * i + 1)) + 1;
		a[i] = (a[k] * 2 + b[i - k] - 1) % 10000;
	}
	printf("%ld\n", a[N]);
}
```

---

## 小实验：用remark插入`\(\LaTeX{}\)`公式

单行公式列表：

1. `\(\int_a^bf(x)dx\)`
2. `\(x={a \over b}\)`

公式显示：

$$e^{i\pi} + 1 = 0$$

---

class: center, middle

# 谢谢
