# 문자열에 숫자가 포함된지 확인하는 방법 (java string contains int)

### 해결방법
- 문자열을 문자로 분리하고, Character.isDigit(Char ch)를 이용해서 문자가 숫자인지 확인

```Java
String str = "123ABC";
for(char c : str.toCharArray()) {
    if(Character.isDigit(c)) { // 문자가 숫자일 때 true
        // 1, 2, 3일 때 동작
    }
}
```