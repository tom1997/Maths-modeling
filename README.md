

%# 国赛A题

背景：
- 二维CT成像
- 平行入射
- 逆时针旋转180次
- 探测器：
  - 512个等距单位
  - 测量介值吸收衰减后的射线能量
  - 增益处理
- CT系统安装存在误差，需要参数标定，据此对未知结构样品进行成像
  - 方法： 借助已知结构的样品（模板）标定

## 第一问

已知模板几何信息与吸收率，求参数：
- 旋转中心
- 探测器单元之间距离
- X射线的180个方向
```c
#include <stdio.h>

int main(void)
{
  printf("Hello, wolrd\n");
}
```

$$\varphi = m\Delta$$
$$\frac{1+ M\times \ell}{2} + y\sin{(\theta-\varphi)} + x\cos{(\theta-\varphi)}=(n+\lambda)\times \ell$$
$$\tilde P(n,m) = P(n,m)\times h(n)$$
$$ \tilde P(n+\delta,m) = (1-\delta)P(n,m)+\delta P(n+1, m)$$
$$ a_m(i,j) = a_{m-1}(i,j)+\tilde P(n+\delta, m)$$
