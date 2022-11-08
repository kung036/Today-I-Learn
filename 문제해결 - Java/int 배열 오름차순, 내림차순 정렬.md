# int 배열 오름차순 정렬

### 해결방법 1) stream 이용
``` Java
int[] arr = { 3, 2, 1 };

// 스트림으로 오름차순 정렬
int[] sortArr = Arrays.stream(arr)  // IntStream
        .sorted() // 오름차순 정렬
        .toArray(); // int[]
        
System.out.println(Arrays.toString(sortArr)); // [1, 2, 3]
```

### 해결방법 2) Arrays.sort() 메서드 사용

``` Java
int[] arr = { 3, 2, 1 };

// Arrays.sort() 메서드 사용
Arrays.sort(arr);

System.out.println(Arrays.toString(arr)); // [1, 2, 3]
```

#  int 배열 내림차순 정렬
### 해결방법)
- int 배열을 Integer 배열로 변환 후 Arrays.sort() 메서드 이용해서 내림차순 정렬, 정렬 후 Integer 배열을 int 배열로 변환

``` Java
int[] arr = { 1, 2, 3 };

// int[] -> Integer[]
Integer[] IntegerArr = Arrays.stream(arr) // IntStream
                .boxed() // Stream<Integer>
                .toArray(Integer[]::new); // Interger[]

// 내림차순으로 정렬
Arrays.sort(IntegerArr, Comparator.reverseOrder());

// Integer[] -> int[]
int[] reverseArr = Arrays.stream(IntegerArr) // Stream<Integer>
        .mapToInt(i -> i) // IntStream
        .toArray(); // int[]
```
