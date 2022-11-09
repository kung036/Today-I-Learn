# **JSON**

## **JSON**

-   **JSON(JavaScript Object Notation)**
    -   데이터 교환을 위한 객체 형태의 포맷
    -   JSON과 JavaScript의 차이 존재
    -   키와 값 사이의 공백 존재 X
-   데이터 송수신 가능 조건
    1.  수신자와 발신자가 같은 프로그램 사용
    2.  범용적인 형태의 데이터 송수신 → 대표적인 형태 : JSON
-   직렬화(serialize) : 객체를 범용적인 형태(JSON)으로 변경하는 과정
<br></br>

-   **JSON in Java**
    -   자바에서 JSON으로 변환된 객체 타입 : 문자열(String)
    -   구현 : jackson 라이브러리의 ObjetMapper 클래스, net.minidev.json 라이브러리의 JSONParser 클

``` Java
ObjectMapper mapper = new ObjectMapper();
JSONParser jsonParser = new JSONParser();

// TEXT 형식
// null, boolean, String, 배열, HashMap 등 다양한 객체의 타입

// 자바 객체 → JSON 객체
String json = mapper.writerValueAsString(TEXT);

// JSON 객체 → 자바 객체
객체_타입 obj = mapper.readValue(json, 객체타입);

// String → JSON 객체
String str = "{\"data\":10}";
JSONObject object = (JSONObject)(jsonParser.parse(str));
long num = (long)object.get("memberId");
```
