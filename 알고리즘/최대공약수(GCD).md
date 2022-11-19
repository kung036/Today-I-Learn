# **최대공약수(GCD)**

## **최대공약수(GCD)**

- **최대공약수(GCD)** : 공약수 중 가장 큰 수(공약수 : 두 수의 공통된 약수)

## 유클리드 호제법

- A>B인 두 자연수 A, B가 주어졌을 때, a%b = r이라고 한다면 A, B의 최대공약수 GCD(A, B)는 다음과 같다.  
  이때 r=0 일 때 B가 GCD(A, B)의 값이다.

```Java
GCD(A,B)=GCD(B,r)
```

## 구현

- 방법 1) 재귀
- 방법 2) 반복문

```Java
// 재귀 - 최대공약수
int GCD(int A,int B){
        if(A%B==0)return B;
        return GCD(B,A%B);
        }

// 반복문 - 최대공약수
        int GCD(int A,int B){
        while(B!=0){
        int r=A%B;
        A=B;
        B=r;
        }

        return A;
        }
```