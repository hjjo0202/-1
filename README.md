# 2020732014 조현준 과제1  

![image](https://github.com/user-attachments/assets/8ecb90e3-4953-4a46-a43e-649bc90b358f)  
${i_1}(t) = \frac{V_1(s)}{R}$  
${i_2}(t) = -C \frac{dV_2(s)}{dt} \quad \Rightarrow \quad I(s) = -C \cdot s \cdot V_2(s)$  
$\frac{V_1(s)}{R} = -C \cdot s \cdot V_2(s)$  
$V_2(s) = \frac{-V_1(s)}{R C s}$  
$\text{전달함수} \quad H(s) = \frac{-V_2(s)}{V_1(s)} = \frac{-1}{R C s}$  

![image](https://github.com/user-attachments/assets/753dad12-13a7-4270-87e4-e0b3106e7b83)  
$R(s) \cdot \frac{K}{s + 50} = Y(s)$  
단위계단 입력이므로 $r(t)$의 라플라스 변환  
$R(s) = \frac{1}{s}$  
$\therefore Y(s) = \frac{K}{s(s + 50)}$  
$\lim_{t \to \infty} y(t) = \lim_{s \to 0} s \cdot Y(s) = \lim_{s \to 0} \frac{sK}{s(s + 50)} = \frac{K}{50}$  
$\therefore 1이 되려면 \quad K = 50$  

![image](https://github.com/user-attachments/assets/9bb0ddac-04fa-4ec9-818c-da54a6e92634)  
$m \frac{d^2 x(t)}{dt^2} + b \frac{dx(t)}{dt} + kx(t) = \delta(t)$  
$s^2 X(s) + \frac{bs}{m} X(s) + \frac{k}{m} X(s) = \frac{1}{m}$  
$X(s) = \frac{1}{ms^2 + bs + k}$  
$x(t) = \mathcal{L}^{-1} \left( \frac{1}{ms^2 + bs + k} \right)$  

![image](https://github.com/user-attachments/assets/f92ec1ba-4c37-4c10-ac29-ca68a1594fe5)  
$M \frac{d^2 x(t)}{dt^2} = F(t) - b ( \frac{dx(t)}{dt} - \frac{dy(t)}{dt} ) - k ( x(t) - y(t) ) \quad \cdots (1)$  
$m \frac{d^2 y(t)}{dt^2} = b ( \frac{dx(t)}{dt} - \frac{dy(t)}{dt} ) + k ( x(t) - y(t) ) \quad \cdots (2)$  
(1)번 식을 라플라스 변환  
$M s^2 X(s) = F(s) - bs \left( X(s) - Y(s) \right) - k \left( X(s) - Y(s) \right) \quad \cdots (3)$  
(2)번 식을 라플라스 변환  
$m s^2 Y(s) = bs(X(s) - Y(s)) + k(X(s) - Y(s)) \quad \cdots (4)$  
(3)번 식을 $F(s)$에 대해 정리  
$F(s) = (M s^2 + bs + k) X(s) - (bs + k) Y(s) \quad \cdots (5)$  
(4)번 식을 $X(s)$에 대해 정리  
$m s^2 Y(s) = (bs + k) X(s) - (bs + k) Y(s)$  
$(bs + k) X(s) = m s^2 Y(s) + (bs + k) Y(s)$  
$X(s) = \frac{Y(s)( m s^2 + bs + k)}{bs + k} \quad \cdots (6)$  
(5)번 식에 (6)번 식 대입
$F(s) = (M s^2 + bs + k) \frac{Y(s)( m s^2 + bs + k )}{bs + k} - (bs + k) Y(s)$

$= Y(s)(\frac{(M s^2 + bs + k)(m s^2 + bs + k) - (bs + k)^2}{bs + k})$

$\therefore \frac{Y(s)}{F(s)} = \frac{bs + k}{(M s^2 + bs + k)(m s^2 + bs + k) - (bs + k)^2}$  

![image](https://github.com/user-attachments/assets/6c5dc6de-468b-4518-aa1d-a1e1dee070c0)  
$m_1 \frac{d^2 x(t)}{dt^2} = -K_1 x(t) - K_2 (x(t) - y(t)) \quad \cdots (1) \therefore \frac{d^2 x}{dt^2} = -2x(t) + y(t)$  
$m_2 \frac{d^2 y(t)}{dt^2} = -K_2 (y(t) - x(t)) - u(t) \quad \cdots (2) \therefore \frac{d^2 y}{dt^2} = x(t) - y(t) - u(t)$  
(1)번 식을 라플라스 변환  
$m_1 s^2 X(s) = -K_1 X(s) - K_2 (X(s) - Y(s))$  
$\Rightarrow s^2 X(s) = -X(s) - X(s) + Y(s) \Rightarrow s^2 X(s) + 2X(s) = Y(s)$  
$\Rightarrow X(s) (s^2 + 2) = Y(s) \quad X(s) = \frac{Y(s)}{s^2 + 2} \quad \cdots (3)$  
(2)번 식을 라플라스 변환  
$m_2 s^2 Y(s) = -K_2 (Y(s) - X(s)) - U(s)$  
$\Rightarrow s^2 Y(s) = X(s) - Y(s) - U(s) \quad \cdots (4)$  
(3)번 식을 (4)에 대입
$s^2 Y(s) - \frac{Y(s)}{s^2 + 2} + Y(s) = - U(s)$  
$Y(s) \left( s^2 - \frac{1}{s^2 + 2} + 1 \right) = -U(s) \quad \Rightarrow Y(s) \left( \frac{s^4 + 2s^2}{s^2 + 2}-\frac{1}{s^2+2}+\frac{s^2+2}{s^2+2} \right) = -U(s)$  
$Y(s) \left( \frac{s^4 + 3s^2 + 1}{s^2 + 2} \right) = -U(s) \quad \therefore \frac{Y(s)}{U(s)} = - \left( \frac{s^2 + 2}{s^4 + 3s^2 + 1} \right)$  




