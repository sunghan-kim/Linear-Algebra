# 고유값과 고유벡터 (eigenvalue & eigenvector)

# 1. 고유값, 고유벡터란?

## 1.1 수학적 정의

> 행렬 A를 선형변환으로 봤을 때, 선형 변환 A에 의한 변환 결과가 자기 자신의 상수배가 되는 0이 아닌 벡터를 고유벡터(eigenvector)라 하고 이 상수배 값을 고유값(eigenvalue)라 한다.

- 고유값, 고유벡터는 정방행렬에 대해서만 정의된다.
- 즉, n x n 정방행렬 A에 대해 $Av = \lambda v​$를 만족하는 0이 아닌 열벡터 $v​$를 고유벡터, 상수 $\lambda​$를 고유값이라 정의한다.

$$
A v = \lambda v \qquad \qquad \text{--- (1)}
$$


$$
\begin{pmatrix}
a_{11} & \cdots & a_{1n} \\
\vdots & \ddots & \vdots \\
a_{n1} & \cdots & a_{nn} 
\end{pmatrix}

\begin{pmatrix}
V_1 \\
\vdots \\
V_n
\end{pmatrix}

= \lambda \,
\begin{pmatrix}
V_1 \\
\vdots \\
V_n
\end{pmatrix}

\qquad \qquad \text{--- (2)}
$$


- $\lambda​$  : 행렬 A의 고유값
- $v​$ : 행렬 A의 $\lambda​$에 대한 고유벡터

<br>

- 고유값과 고유벡터는 행렬에 따라 정의되는 값이다.
- 어떤 행렬은 이러한 고유값, 고유벡터가 아예 존재하지 않을 수도 있고, 어떤 행렬은 하나만 존재하거나 또는 최대 n개까지 존재할 수 있다.

<br>

# 2. 기하학적 의미

## 2.1 행렬(선형변환) A의 고유벡터

- 선형변환 A에 의해 방향은 보존되고 스케일(scale)만 변화되는 방향 벡터

<br>

## 2.2 고유값

- 그 고유벡터의 변화되는 스케일의 정도

<br>

# 3. 고유값 분해를 이용한 대각화 - eigendecomposition

- 고유값, 고유벡터는 정방행렬의 대각화와 밀접한 관련이 있다.
  (eigendecomposition은 정방행렬에 대해서만 가능함)

<br>

## 3.1 대각행렬과 행렬곱

- 대각행렬 뒤에 곱하면 행렬의 열벡터들이 대각원소의 크기만큼 상수배된다.
- 대각행렬 앞에 곱하면 행렬의 행벡터들이 상수배가 된다.

<br>

- 예를 들어, 3 x 3 행렬의 경우를 보면 다음과 같다.


$$
\begin{pmatrix}
v_{11} & v_{12} & v_{13} \\
v_{21} & v_{22} & v_{23} \\
v_{31} & v_{32} & v_{33}
\end{pmatrix}

\begin{pmatrix}
\lambda_1 & 0 & 0 \\
0 & \lambda_2 & 0 \\
0 & 0 & \lambda_3
\end{pmatrix}

=

\begin{pmatrix}
\lambda_1 v_{11} & \lambda_2 v_{12} & \lambda_3 v_{13} \\
\lambda_1 v_{21} & \lambda_2 v_{22} & \lambda_3 v_{23} \\
\lambda_1 v_{31} & \lambda_2 v_{32} & \lambda_3 v_{33}
\end{pmatrix}

\qquad \qquad \text{--- (3)}
$$
<br>

## 3.2 대각화 분해

- 행렬 A의 고유값을 $\lambda_i$, 고유벡터를 $v_i$, $i=1, 2, \cdots, n$이라 하자.


$$
\begin{matrix}
A v_1 = \lambda_1 v_1 \\
A v_2 = \lambda_2 v_2 \\
\vdots \\
A v_n = \lambda_n v_n \\
\end{matrix}
\qquad \qquad \text{--- (4)}
$$
<br>

- 이제 식 (4) 를 한꺼번에 표현하여 정리하면 다음이 성립함을 알 수 있다.


$$
\begin{matrix}
\begin{align*}
A \, [v_1 \; v_2 \; \cdots \; v_n] &= 
[\lambda_1 v_1 \; \lambda_2 v_2 \; \cdots \; \lambda_n v_n] \\
&=
[v_1 \; v_2 \; \cdots \; v_n]
\begin{bmatrix}
\lambda_1 & 		  & & 0 \\
		  & \lambda_2 & &   \\
		  &           & \ddots & \\
0		  & 		  &        & \lambda_n		  
\end{bmatrix}
\end{align*}
\end{matrix}

\qquad\qquad \text{--- (5)}
$$
<br>

- 즉, 행렬 A의 고유벡터들을 열벡터로 하는 행렬 P, 고유값들을 대각 원소로 하는 대각행렬을  $\Lambda​$ 라 하면 다음  식이 성립한다.


$$
AP = P \Lambda \qquad\qquad \text{--- (6)}
$$
<br>

- 즉,

$$
A = P \Lambda P^{-1} \qquad\qquad \text{--- (7)}
$$

<br>

- 이와 같이 행렬 A는 자신의 고유벡터들을 열벡터로 하는 행렬과 고유값을 대각원소로 하는 행렬의 곱으로 대각화 분해가 가능하다.
- 이러한 대각화 분해를 eigendecomposition이라고 한다.

<br>

## 3.3 대각화 분해의 예

- 한 예로, A 가 다음과 같을 떄 A는 다음과 같이 대각화가 가능하다.

$$
A = 
\begin{bmatrix}
1 & 1 & 0 \\
0 & 2 & 1 \\
0 & 0 & 3 
\end{bmatrix}
=
\begin{bmatrix}
1 & 1 & 1 \\
0 & 1 & 2 \\
0 & 0 & 2 
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 0 \\
0 & 2 & 0 \\
0 & 0 & 3 
\end{bmatrix}
{
\begin{bmatrix}
1 & 1 & 1 \\
0 & 1 & 2 \\
0 & 0 & 2 
\end{bmatrix}    
}^{-1}

\qquad\qquad \text{--- (8)}
$$

<br>

## 3.4 대각화 분해가 가능한 정방행렬

- 모든 정방행렬이 이런 방식의 eigendecomposition이 가능한 것은 아니다.
- 하지만 대각화가 가능한 경우는 뒤에 적기로 하고 일단은 대각화를 하면 어떤 게 좋은 지 알아보자.

<br>

## 3.5 대각화 분해의 활용

- 행렬 A이 eigendecomposition을 알면 행렬식 값 det(A), A의 거듭제곱, 역행렬, 대각합(trace), 행렬의 다항식 등을 매우 손쉽게 계산할 수 있다.

<br>

### 3.5.1 행렬 A의 행렬식 값 ; det(A)

$$
\begin{align*}
det(A) &= det \left( P \Lambda P^{-1} \right) \\
&= det(P) \; det(\Lambda) \; det(P)^{-1} \\
&= det(\Lambda) \\
&= \lambda_1 \, \lambda_2 \, \cdots \, \lambda_n
\end{align*}

\qquad\qquad \text{--- (9)}
$$

<br>

### 3.5.2 행렬 A의 거듭제곱

$$
\begin{align*}
A^k &= \left( P \Lambda P^{-1} \right)^k \\
&= \left( P \Lambda P^{-1} \right)
\left( P \Lambda P^{-1} \right)
\cdots
\left( P \Lambda P^{-1} \right) \\
&= P \Lambda^k P^{-1} \\
&= P \, diag(\lambda_1^k, \, \cdots, \, \lambda_n^k) \, P^{-1}
\end{align*}

\qquad\qquad \text{--- (10)}
$$

<br>

### 3.5.3 행렬 A의 역행렬

$$
\begin{align*}
A^{-1} &= \left( P \Lambda P^{-1} \right)^{-1} \\
&= P \Lambda^{-1} P^{-1} \\
&= P \, diag(1/\lambda_1, \, \cdots, \, 1/\lambda_n) \, P^{-1}
\end{align*}

\qquad \qquad \text{--- (11)}
$$

<br>

### 3.5.4 행렬 A의 대각합(trace)

$$
\begin{align*}
tr(A) &= tr(P \Lambda P^{-1}) \\
&= tr(\Lambda) \quad \left( \because tr(AB) = tr(BA) \right) \\
&= \lambda_1 + \cdots + \lambda_n
\end{align*}

\qquad\qquad \text{--- (12)}
$$

<br>

### 3.5.5 행렬 A의 다항식

$$
\begin{align*}
f(A) &= a_0 E + a_1 A + \cdots + a_n A^n 
\quad \left( f(x) = a_0 + a_1 x + \cdots + a_n x^n \right) \\
&= a_0 P P^{-1} + a_1 P \Lambda P^{-1} + \cdots + a_n P \Lambda^n P^{-1} \\
&= P \left( a_0 P^{-1} + a_1 \Lambda P^{-1} + \cdots + a_n \Lambda^n P^{-1} \right) \\
&= P \left( a_o E + a_1 \Lambda + \cdots + a_n \Lambda^n \right) P^{-1} \\
&= P \, diag(f(\lambda_1), \, \cdots, \, f(\lambda_n)) \, P^{-1}
\end{align*}

\qquad\qquad \text{--- (13)}
$$

<br>

# 4. 고유값 분해(eigendecomposition) 가능 조건 - 일차독립

- 앞서 말했지만, 모든 정방행렬이 고유값 분해가 가능한 것은 아니다.
- n x n 정방행렬 A가 고유값 분해가 가능하려면 **행렬 A가 n개의 1차 독립인 고유벡터**를 가져야 한다.

<br>

## 4.1 일차 독립 (linearly independent)

- 어떤 벡터들의 집합 $\{ v_1, \, \cdots, \, v_n \}​$이 있을 때, 이들 벡터들 중 어느 한 벡터도 다른 벡터들의 일차결합으로 표현될 수 없으면 이 벡터들은 서로 일차독립이라고 정의한다.

<br>

### 4.1.1 벡터들의 일차결합

- 벡터들의 일차결합은 $a_1 v_1 + a_2 v_2 + \cdots + a_n v_n \quad (a_i \text{is constant})​$와 같이 상수를 곱하여 합친 형태를 말한다.

<br>

## 4.2 기저(basis)

- n 차원 공간은 최대 n개의 일차독립인 벡터들을 가질 수 있다.
- n개의 일차독립인 벡터들은 이 공간을 생성하는 기저(basis) 역할을 수행한다.

<br>

- 예를 들어, 3차원 공간의 좌표축 단위벡터들인 $v_1​$, $v_2​$, $v_3​$들이 있다고 하자.
  - $v_1 = (1, 0, 0)$
  - $v_2 = (0, 1, 0)$
  - $v_3 = (0, 0, 1)$
- 이 벡터들을 이용하여 3차원 공간의 모든 $(x, y, z)​$ 좌표를 생성할 수 있음을 알 수 있다.

<br>

- 어떤 일차독립인 벡터들의 집합 $\{ v_1, \, \cdots, \, v_n \}​$의 일차 결합을 통해 어떤 공간의 모든 좌표를 생성할 수 있으면 이 벡터들을 이 공간의 기저(basis)라고 정의한다.

<br>

## 4.3 고유값 분해 조건

- n차 정방행렬이 고유값 분해가 가능하려면 n개의 일차 독립인 고유벡터가 존재해야 한다.
- 이 말을 이해하기 위해서는 고유값, 고유벡터의 계산 과정에 대한 이해가 먼저 필요하다.

<br>

# 5. 고유값, 고유벡터의 계산







# References

[https://darkpgmr.tistory.com/105](https://darkpgmr.tistory.com/105)

