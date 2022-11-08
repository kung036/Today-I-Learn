# Ingeter 배열 역순

### 해결방법) 리스트로 변환 후 Collections.reverse() 메서드 이용
- Integer 배열을 리스트로 변환해서 Collections.reverse() 메서드 이용

``` Java
// Integer[] 배열
Integer[] arr = { 1, 2, 3 };
List<Integer> list = Arrays.asList(arr); // 배열(int X) → List
Collections.reverse(list); // Collections.reverse() 메서드를 이용해서 역순으로 만들기
Integer[] reverseArr = list.toArray(arr); // List → 배열

System.out.println(Arrays.toString(reverseArr)); // [3, 2, 1]
```