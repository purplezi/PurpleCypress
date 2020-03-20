##  插值和拟合

插值（同拉格朗日插值），会有龙格现象
```
% longge phenomenon(插值阶数过高的偏离现象)
for i=3:2:11
    x=linspace(-1,1,i);
    y=1./(1+25*x.^2);
    p=polyfit(x,y,i-1);
    xx=-1:0.01:1;
    yy=polyval(p,xx);
    plot(xx,yy,'b');
    hold on;
    grid on;
end
plot(x,1./(1+25*x.^2),'r');
```
<img src=Fitting_img/longge.png width=80%>

### 最小二乘法

<img src=Fitting_img/LeastSquares.png width=80%>


### 评价标准

<img src=Fitting_img/FittingAssessment.png width=80%>


### 采用cftool拟合

<img src="Fitting_img/cftool.png" width=80%>

* Custom Equations：用户自定义的函数类型
* Exponential：指数逼近，有2种类型， $ae^{bx} 、 ae^{bx} + ce^{dx}$
* Fourier：傅立叶逼近，有7种类型，基础型是 a0 + a1*cos(x*w) + b1*sin(x*w)
* Gaussian：高斯逼近，有8种类型，基础型是 $a1e^{-((x-b1)/c1)^2}$
* Interpolant：插值逼近，有4种类型，linear、nearest neighbor、cubic spline、shape-preserving
* Polynomial：多形式逼近，有9种类型，linear ~、quadratic ~、cubic ~、4-9th degree ~
* Power：幂逼近，有2种类型，$a*x^b 、a*x^b + c$
* Rational：有理数逼近，分子、分母共有的类型是linear ~、quadratic ~、cubic ~、4-5th degree ~；此外，分子还包括constant型
* Smoothing Spline：平滑逼近（翻译的不大恰当，不好意思）
* Sum of Sin Functions：正弦曲线逼近，有8种类型，基础型是 a1*sin(b1*x + c1)
* Weibull：只有一种，$abx^{b-1}*e^{-a*x^b}$