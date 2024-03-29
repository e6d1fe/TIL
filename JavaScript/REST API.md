### REST API

**REST**: HTTP의 장점을 최대한 활용할 수 있도록 클라이언트가 서버의 리소스에 접근하는 방식을 규정한 아키텍처

#### REST API의 구성

| 구성 요소 | 내용                           | 표현 방법        |
| --------- | ------------------------------ | ---------------- |
| 자원      | 자원                           | URI(엔드포인트)  |
| 행위      | 자원에 대한 행위               | HTTP 요청 메서드 |
| 표현      | 자원에 대한 행위의 구체적 내용 | 페이로드         |

#### REST API 설계 원칙

1. **URI는 리소스를 표현해야 한다.**  
   리소스를 식별할 수 있는 이름은 동사보다는 명사를 사용한다. (예를 들어 `getTodos` 대신에 `todos`)
2. **리소스에 대한 행위는 HTTP 요청 메서드로 표현한다.**  
   주로 GET, POST, PUT, PATCH, DELETE의 5가지 요청 메서드를 사용하여 CRUD를 구현한다.  
   이렇게 리소스에 대한 행위는 요청 메서드로 표현하며 URI에는 표현하지 않는다.

| HTTP 요청 메서드 | 종류           | 목적                  | 페이로드 |
| ---------------- | -------------- | --------------------- | -------- |
| GET              | index/retrieve | 모든/특정 리소스 취득 | X        |
| POST             | create         | 리소스 생성           | O        |
| PUT              | replace        | 리소스 전체 교체      | O        |
| PATCH            | modify         | 리소스 일부 수정      | O        |
| DELETE           | delete         | 모든/특정 리소스 삭제 | X        |
