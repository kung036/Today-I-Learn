# 문자열을 forEach문으로 순회화는 방법

### 해결방법
- toCharArray() 메서드로 String을 char형 배열로 변경

```Java
String str = "Hello";
for(char c : str.toCharArray()) {
    System.out.println(c);
}
/* 실행결과
H
e
l
l
o
*/
```