# 题目

- 导航
    
    [单次语句类](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9.md)
    
    [嵌套求和类](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9.md)
    
    [递归类](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9.md)
    
    [链表比较类](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9.md)
    
    [嵌套乘法类](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9.md)
    

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled.png)

选 D，背去吧

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%201.png)

选 C，$T(n)=O(n^2)$，问题规模是 n，执行时间是方

单次语句类

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%202.png)

$i=i*2$，设执行次数为$t$，判断条件$i=2^t\le n$，则$t\le \log_2n$，D

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%203.png)

$i++$，$t，t^3\le n,t\le \sqrt[3]n$ ，C

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%204.png)

$(t+1)^2\le n，t\le\sqrt n$

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%205.png)

$2^{t+1}<n/2，t<\log_2{n}$，C

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%206.png)

$i=t+1<n-1,t<n-2,O(n)$

嵌套求和类

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%207.png)

最坏，全换一遍

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%208.png)

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%209.png)

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%2010.png)

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%2011.png)

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%2012.png)

看着像单次语句，但结束条件是执行次数求和

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%2013.png)

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%2014.png)

$\sum_{i=1}^n\sum_{j=1}^i\sum_{k=1}^j1=\sum_{i=1}^n\frac{i^2+i}{2}$，可以简化为$\sum_{i=1}^ni^2$，有公式$=\frac{n(n+1)(2n+1)}{6}$，则$O(n^3)$

递归类

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%2015.png)

主要看原理，递归传n-1，一直到 1，那就是递归到第n层，B

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%2016.png)

其实是个纯数学题，他这个递归方程本身就是时间，而不是算法

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%2017.png)

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%2018.png)

链表比较类

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%2019.png)

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%2020.png)

采用头插法，两个比较，较小的插进去，最坏的就是每两个都要比较

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%2021.png)

答案没有m+n啊，这里是用到时间复杂度可将问题规模看作♾️，这里 m，n 都是♾️，那么他们两个谁大，另一个就可以忽略，所以 D

嵌套乘法类

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%2022.png)

乘法规则，选 C

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%2023.png)

![Untitled](%E9%A2%98%E7%9B%AE%20d94c093bc7af4de2aff9c7e5356fbaa9/Untitled%2024.png)

$O(m)*O(n)$=$O(mn)$