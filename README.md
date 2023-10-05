# State Space Equation
## * State Variables  
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
