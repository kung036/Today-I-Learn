#  int 배열 → Integer 배열 변환

### 해결방법) stream() 이용
``` Java
// int[] → Integer[]
int[] arr = { 1, 2, 3 };
Integer[] IntegerArr =
        Arrays.stream(arr) // IntStream
                .boxed() // Stream<Integer>
                .toArray(Integer[]::new); // Interger[]
```

# Integer 배열 → int 배열 변환

### 해결방법) stream() 이용
``` Java
// Integer[] → int[]
Integer[] IntegerArr = { 1, 2, 3 };
int[] arr = Arrays.stream(IntegerArr) // Stream<Integer>
        .mapToInt(i -> i) // IntStream
        .toArray(); // int[]
```