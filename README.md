# State Space Equation
## State Variables  
![image](https://github.com/kangjunhyeong/equation/assets/144297425/9fcf870a-1414-43f6-9bcb-36c9962d1837)  
System안에 States를 정의해서 문제를 푸는 것이 핵심이다.  
컴퓨터한테 일을 시키기 쉽게 식을 바꾸어 나가는 과정이다.  

## 1. spring-mass-damper system  

![image](https://github.com/kangjunhyeong/equation/assets/144297425/73793897-5f27-4cbd-b499-bd8ddd458384)  

$$
\ M \frac{d^2y(t)}{dt^2} + b \frac{dy(t)}{dt} + ky(t) = r(t) \
$$  

$$
\ x_1(t) = y(t) \ ,\ x_2(t) = \frac{dy(t)}{dt} \
$$  

위와 같이 state를 지정하면 x1과 x2에 대한 식으로 다음과 같이 변경이 가능하다.  

$$
\ \frac{dx_1(t)}{dt} = x_2(t) \  
$$

$$
\ \frac{dx_2(t)}{dt} = \frac{-b}{M}x_2(t) - \frac{-k}{M}x_1(t) + \frac{1}{M}r(t) \
$$

$$
\ y(t)=x_1(t)
$$
 
이와 같이 2차미분방정식이 2개의 1차미분방정식으로 바뀐다.  

## 2. RLC circuit system  

![image](https://github.com/kangjunhyeong/equation/assets/144297425/d5a3b351-3c2e-4c53-87fc-5f9635550985)  

$$
\ x_1(t) = v_c(t) \ , \ x_2(t) = i_L(t) \
$$  

KCL에 의하면  

$$
\ u(t) = C \frac{dx_1(t)}{dt} + x_2(t) \
$$

$$
\ \frac{dx_1(t)}{dt} = \frac{1}{C} (-x_2(t) + u(t)) \
$$  

KVL에 의하면  

$$
\ L \frac{dx_2(t)}{dt} + Rx_2(t) - x_1(t) = 0 \
$$  

$$
\ \frac{dx_2(t)}{dt} = \frac{1}{L} [x_1(t) - Rx_2(t)] \
$$  

$$
y(t)=Rx_2(t)
$$  

이와 같이 단순히 수학적 모델링으로 미분방정식을 세우는 것이 아닌 state를 통해 좀 더 쉽게 풀이를 할 수 있다.  

## 왜 state를 만들어야 하는가?  
state를 정의하면 일차미분방정식이 연립방정식이 된다.  

$$
\ i(t) = ax(t) + bu(t) \
$$  

이를 라플라스변환을 시켜주면

$$
\ sX(s) - x(0) = aX(s) + bU(s) \
$$  

$$
\ (s - a)X(s) = x(0) + bU(s) \
$$

$$
\ X(s) = \frac{1}{s-a}x(0) + \frac{1}{s-a}bU(s) \
$$

인버스라플라스를 해주면  

$$
\ x(t) = e^{at}x(0) + \int_{0}^{t} e^{a(t - \tau)}bu(\tau) d\tau \
$$  

이 식에서 $e^{at}\$ 를 $\{\\Phi\(t)}\$ 로 바꿔주면  

![image](https://github.com/kangjunhyeong/equation/assets/144297425/5aeba743-048a-4294-8c1d-df8f40956375)  

이렇게 식이 바뀌고 왼쪽 부분은 초기 상태가 $\{\\Phi\(t)}\$ 값에 의해서 바뀐 결과물이 되고 오른쪽 텀은 input이 $\{\\Phi\(t)}\$ 라는 것에 의해 바뀐 결과물이 됩니다. 왼쪽 값의 경우 input이 없을 때 초기 상태에서 결과가 어떻게 바뀌게 되는지를 의미하고 물리적인 의미를 갖게 됩니다. 이와 같이 의미 있는 수식이 됩니다.
