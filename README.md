# spring-REST-Docs

- 목차
    1. API문서
    2. Spring REST Docs
    3. Swagger 와 비교
    4. 실습! API 문서 자동으로 만들기
    5. OpenAPI Spec
    6. 실습! Spring REST Docs와 SwaggerUI 조합

- API (Application Programming Interface)

    → 대부분 Server-Side (Back-end)에서 제공

    → 데이터의 조작(CRUD)을 하기 위함

    ex) 사용자의 정보는 Front-end에서 사용자의 정보를 조작하기 위해 Back-end에서 제공하는 API를 사용하게 된다.

- API 문서를 왜 만들어야 할까?

    → '제공자' ↔ '사용자' 사용방법 공유/협의 : url은 어떻게되는지, 파라미터 값은 어떻게 작성해야하는지, GET, POST 등 method는 무엇으로 쓰는지 작성해야한다.

    → API 버전 및 변경사항관리

- API 문서 기존방식(ex : 워드, 엑셀 등)의 단점
    1. 버전 변경 등 수정에 취약
    2. API와 문서 상태가 다를 수 있음 (버전,오류 등)
    3. 검증되지 못한 문서

- Spring REST Docs
    1. RESTful 서비스에 대한 정확하고 읽기 쉬운 문서를 생성하도록 돕는 것이 목적
    2. 테스트를 통하여 API의 문서생성
    3. 스니펫(Snippets)의 조합으로 API 문서 커스터마이징
    4. 간결한 적용, 다양한 생성 방법

- Spring REST Docs 의 장점
    1. 별도의 Html, PDF 파일로 API 문서 자동 생성 (Hosting 가능) → 자동화 가능
    2. Request / Response 테스트를 통하여 API 문서의 신뢰도 상승
    3. API 변경에 따른 API 문서 최신화 보장

- Swagger

    → API 문서화의 양대산맥중 하나

    → RESTful 문서에 대한 명세 보다는 API를 쉽게 호출해볼 수 있는 것에 초점

- Spring REST Docs 과 Swagger 비교
    |Spring REST Docs|Swagger|
    |---|---|
    |테스트 기반으로 실행|API 테스트 UI 제공|
    |문서에 대한 신뢰성|어노테이션을 통한 간단한 작업|
    |product 코드에 영향 없음|테스트 코드가 없어도 문서화 가능|
    |간결 + 명료|깔끔하게 정리되어 보기 좋음|
    |snippets 조합으로 커스터마이징 가능||

- 문서화를 위한 API
    |사용자|HTTP APT|
    |---|---|
    |생성|POST / api / user|
    |조회|GET / api / user /{id}|
    |수정|PUT / api / user|
    |삭제|DELETE / api / user / {id}|
   
- Database
    |Name|Datatype|
    |---|---|
    |id|BIGINT|
    |account|VARCHAR(45)|
    |email|VARCHAR(45)|
    |phone_number|VARCHAR(45)|
    |created_at|DATETIME|
    |updated_at|DATETIME|

- 실습 순서
    1. 프로젝트 생성
    2. 실습에 필요한 테스트 API 코드 작성
    3. Spring REST Docs 관련 설정 추가
    4. Test Code 작성으로 스니펫 생성(Snippets)
    5. 스니펫에 의해 html 문서가 만들어지도록 adoc 파일 구성
    6. 빌드시 생성된 html 파일이 호스팅 되도록 설정

- Swagger Open Api Spec

    → REST API 에 대한 설명, 생성, 사용 및 시각화 하기 위한 인터페이스 파일의 사양

    → Swagger 프레임워크의 일부였지만 오픈소스로 전환

    → 기본 내용

    - endpoint
    - HTTP Method, parameters
    - Input / Output
    - Authentication methods
    - Contact information, license, terms of use and other information

    → YAML 또는 JSON 으로 작성 가능

- Spring REST Docs 와 Swagger 조합
    1. Spring REST Docs의 만들어지는 문서 설정을 기반으로 OpenAPI Spec 파일을 생성
    2. 오픈소스

        → Gradle : https://github.com/ePages-de/restdocs-api-spec

        → Maven : [https://github.com/BerkleyTechnology](https://github.com/BerkleyTechnology)Services/restdocs-spec

    3. Swagger UI를 띄우고 생성된 OpenAPI Spec 파일을 읽는 방식
    4. Spring REST Docs의 장점

        → Test를 통과해야 문서가  생성

        → Product 코드에 영향 없음

    5. Swagger의 장점

        → API 테스트 UI를 제공

    6. Spring REST Docs는 MSA 환경 등 여러 API 문서를 한곳에서 조회 가능
    7. Spring REST Docs에 만들어진 Docs를 Open API Spec을 적용시켜서 Spec파일을 만들고, Swagger UI를 띄우며 확인 할 수 있다.



### *참고*
- - - 
- [FastCampus] 스프링 아카데미아 - Spring REST Docs : API 문서 자동화의 기본과 활용 
