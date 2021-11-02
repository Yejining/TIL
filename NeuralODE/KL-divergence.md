## KL divergence (Kullback-Leibler diverence)
```
두 확률분포의 차이를 계산하는데 사용되는 함수.
어떤 이상적인 분포에 대해 그 분포를 근사하는 다른 분포를 사용해 샘플링 시 발생하는 정보 엔트로피 차이 계산.
```
```
KL(p||q) = H(p, q) - H(p)
```
- KL divergence는 cross-entropy에서 entropy를 뺀 값
- H(p)는 고정된 상수값이기 때문에 Cross entropy를 최소화하는 것은 KL-divergence를 최소화하는 것과 같음.
- 거리 개념이 아님
