## CrossEntropy
[link](https://hyunw.kim/blog/2017/10/26/Cross_Entropy.html)
```
어떤 문제에 대해 특정 전략을 사용할 때 에상되는 기대값. 전략은 확률분포로 표현됨.
확률분포로 된 어떤 문제 p(기계 p)에 대해 확률분포로 된 어떤 전략 q(전략 q)를 사용할 때의 기대값
```
주로 p_i는 특정 확률에 대한 참값 또는 목표 확률이고, q_i는 현재 학습한 확률값.
어떤 q_i를 학습하는 상태라면 p_i에 가까워질수록 cross entropy 값은 작아지게 됨.
Cross entropy는 negative log likelihood로 불리기도 함

- [likelihood](https://rpubs.com/Statdoc/204928)
