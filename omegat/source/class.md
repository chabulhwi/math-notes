# 부류의 정의
## [구문 1] 변수
### 가정
$ \mathrm{var} \ x $
### 주장
$ \mathrm{term} \ x $
### 붙임
1. $ \mathrm{var} \ x $는 "$ x $는 변수이다."라는 뜻의 진술이다.
1. $ \mathrm{term} \ x $는 "$ x $는 항이다."라는 뜻의 진술이다.
1. 이 구문은 변수가 항을 나타냄을 뜻한다.

## [구문 2] 집합
### 가정
$ \mathrm{term} \ a $
### 주장
$ \mathrm{wff} \ \mathrm{set} \ a $
### 붙임
1. $ \mathrm{wff} \ \varphi $는 "$ \varphi $는 잘세운식[well-formed formula, wff]이다."라는 뜻의 진술이다.
1. 이 구문은 $ a $가 항이면 $ \mathrm{set} \ a $가 잘세운식임을 뜻한다.
1. $ \mathrm{set} \ a $는 "$ a $는 집합이다."라는 뜻의 잘세운식이다.

## [구문 3] 부류
### 가정
$ \mathrm{term} \ A $
### 주장
$ \mathrm{wff} \ \mathrm{class} \ A $
### 붙임
1. 이 구문은 $ A $가 항이면 $ \mathrm{class} \ A $가 잘세운식임을 뜻한다.
1. $ \mathrm{class} \ A $는 "$ A $는 부류[class]이다."라는 뜻의 잘세운식이다.

## [구문 4.1] 부류 추상화 (1)
### 가정
1. $ \mathrm{wff} \ \varphi $
1. $ \mathrm{var} \ x $
### 주장
$ \mathrm{term} \ \left \{ x \ \middle| \ \varphi \right \} $
### 붙임
이 구문은 부류 추상화[class abstraction]가 항임을 뜻한다.

## [정의 4.2] 부류 추상화 (2)
### 가정
1. $ \mathrm{wff} \ \varphi $
1. $ \mathrm{var} \ x $
### 주장
$ \mathrm{class} \ \left \{ x \ \middle| \ \varphi \right \} $
### 붙임
이 정의는 부류 추상화가 부류임을 뜻한다.

## [정의 4.3] 부류 추상화 (3)
### 가정
1. $ \mathrm{wff} \ \varphi $
1. $ \mathrm{var} \ x \ y $
### 주장
$ \forall x \left [ \mathrm{class} \ x \rightarrow \left ( x \in \left \{ y \ \middle| \ \varphi \right \} \leftrightarrow \mathrm{set} \ x \wedge \left [ x / y \right ] \varphi \right ) \right ] $
### 붙임
1. $ \mathrm{var} \ x \ y $는 "$ x $와 $ y $는 변수이다."라는 뜻의 진술이다.
1. $ \left [ x / y \right ] \varphi $는 잘세운식 $ \varphi $에 있는 변수 $ y $를 변수 $ x $로 정확히 바꿔 얻은 잘세운식이다. 이런 치환을 정확한 치환[proper substitution]이라고 한다. (Megill 1993)

## [구문 5.1] 러셀 부류 (1)
### 주장
$ \mathrm{term} \ \mathrm{Ru} $
### 붙임
이 구문은 러셀 부류가 항임을 뜻한다.

## [정의 5.2] 러셀 부류 (2)
### 가정
$ \mathrm{var} \ y $
### 주장
$ \mathrm{Ru} = \left \{ y \ \middle| \ y \notin y \right \} $
### 붙임
러셀 부류란, 자신을 원소로 갖지 않는 모든 집합의 부류이다.

## [따름 정리 5.3] 러셀 부류 (3)
### 주장
$ \mathrm{class} \ \mathrm{Ru} $
### 증명
1. $ \mathrm{var} \ y $ (메타변수 유형 가정)
1. $ \mathrm{wff} \ y \notin y $ (1, 공리적 집합론의 구문)
1. $ \mathrm{class} \ \left \{ y \ \middle| \ y \notin y \right \} $ (2, 1, 정의 4.2)
1. $ \mathrm{Ru} = \left \{ y \ \middle| \ y \notin y \right \} $ (1, 정의 5.2)
1. $ \mathrm{class} \ \mathrm{Ru} $ (4, 3, $ = $ 다시 쓰기)
### 붙임
러셀 부류는 부류이다.

## [정리 6] 러셀의 역설
### 주장
$ \mathrm{Ru} \notin \mathrm{Ru} \wedge \neg \mathrm{set} \ \mathrm{Ru} $
### 증명
1. $ \mathrm{var} \ x \ y $ (메타변수 유형 가정)
1. $ \mathrm{wff} \ y \notin y $ (1, 공리적 집합론의 구문)
1. $ \forall x \left [ \mathrm{class} \ x \rightarrow \left ( x \in \left \{ y \ \middle| \ y \notin y \right \} \leftrightarrow \mathrm{set} \ x \wedge \left [ x / y \right ] y \notin y \right ) \right ] $ (2, 1, 정의 4.3)
1. $ \forall x \left [ \mathrm{class} \ x \rightarrow \left ( x \in \left \{ y \ \middle| \ y \notin y \right \} \leftrightarrow \mathrm{set} \ x \wedge x \notin x \right ) \right ] $ (3, 정확한 치환)
1. $ \mathrm{term} \ \mathrm{Ru} $ (구문 5.1)
1. $ \mathrm{class} \ \mathrm{Ru} \rightarrow \left ( \mathrm{Ru} \in \left \{ y \ \middle| \ y \notin y \right \} \leftrightarrow \mathrm{set} \ \mathrm{Ru} \wedge \mathrm{Ru} \notin \mathrm{Ru} \right ) $ (5, 4, $ \forall $ 제거)
1. $ \mathrm{Ru} = \left \{ y \ \middle| \ y \notin y \right \} $ (1, 정의 5.2)
1. $ \mathrm{class} \ \mathrm{Ru} \rightarrow \left ( \mathrm{Ru} \in \mathrm{Ru} \leftrightarrow \mathrm{set} \ \mathrm{Ru} \wedge \mathrm{Ru} \notin \mathrm{Ru} \right ) $ (7, 6, $ = $ 다시 쓰기)
1. $ \mathrm{class} \ \mathrm{Ru} $ (따름 정리 5.3)
1. $ \mathrm{Ru} \in \mathrm{Ru} \leftrightarrow \mathrm{set} \ \mathrm{Ru} \wedge \mathrm{Ru} \notin \mathrm{Ru} $ (9, 8, 전건 긍정 논법)
1. $ \mathrm{Ru} \notin \mathrm{Ru} \wedge \neg \mathrm{set} \ \mathrm{Ru} $ (10, 논리곱과 쌍조건문의 정의)
### 붙임
1. $ \varphi $와 $ \psi $가 잘세운식이라고 하자. $ \varphi \leftrightarrow \psi \wedge \neg \varphi $가 참이면 $ \neg \varphi \wedge \neg \psi $ 또한 참이다. 이는 논리곱과 쌍조건문의 정의에 따른 결과이며, 위의 증명의 11단계에서 이용됐다.
1. 러셀 부류는 집합이 아니므로 어떤 부류의 원소도 될 수 없다. 따라서 러셀 부류는 그 자신의 원소가 아니다.
1. 집합이 아닌 부류를 진부류[proper class]라고 한다. 러셀 부류는 진부류이다.
1. 모든 집합은 부류이다. 여기에서는 그 증명을 생략하겠다.
1. Takeuti and Zaring 1982, chap. 4를 참고하라.

## 참고 문헌
1. Megill, Norman. 1993. “df-sb.” Metamath Proof Explorer. Last modified May 10, 1993. http://us.metamath.org/mpeuni/df-sb.html.
1. Takeuti, Gaisi, and Wilson M. Zaring, *Introduction to Axiomatic Set Theory*, Springer-Verlag, New York, second edition (1982) [QA248.T136 1982].