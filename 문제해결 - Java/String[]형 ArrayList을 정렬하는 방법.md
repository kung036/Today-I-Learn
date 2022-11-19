# ArrayList<String[]>을 정렬하는 방법

### 해결방법) ArrayList의 sort() 메서드 활용


```Java
ArrayList<String[]> list = new ArrayList<>();
list.add(new String[]{"c", "a", "b"});
list.add(new String[]{"a", "b", "c"});
list.add(new String[]{"b", "c", "a"});
list.sort((o1, o2) -> Arrays.toString(o1).compareTo(Arrays.toString(o2))); // 오름차순 정렬
list.stream().forEach(str -> System.out.println(Arrays.toString(str))); // 출력

/*
[a, b, c]
[b, c, a]
[c, a, b]
*/
```
