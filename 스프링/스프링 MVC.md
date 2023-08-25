# 스프링 MVC
- 웹 애플리케이션 개발을 위한 프레임워크
- 사용자의 요청을 처리하고 응답을 생성하는 구조

1. 사용자 요청
- 사용자가 웹 브라우저 등을 통해 웹 애플리케이션에 요청을 보낸다
- 웹 서버가 요청을 받으면 Front Controller인 `DispatcherServlet`이 요청을 가로챈다
2. Handler Mapping
  - `DispatcherServlet`은 요청을 처리할 적절한 컨트롤러(Controller)를 찾기 위해 Handler Mapping 호출한다
  - Handler Mapping은 요청된 URL을 특정 컨트롤러와 매핑시켜준다
3.  Controller 처리
  - 선택된 컨트롤러는 실제 요청을 처리
  - 요청에 따라 비즈니스 로직을 수행 (Service, Repository)
4.  Model 생성
  - 컨트롤러는 처리 결과를 사용자에게 보여주기 위해 Model을 생성
  - Model은 애플리케이션의 상태나 데이터를 나타내는 객체
  - 이 Model 객체에 필요한 데이터를 담아 뷰(View)에 전달 (view가 필요하다면)
5.  View 결정
  - 컨트롤러는 View 정보를 확인하고 `ViewResolver`를 통해 실제 뷰 객체로 변환
  - 이때 뷰는 사용자에게 보여지는 화면을 생성하는 역할
6.  View 표현
  - 선택된 뷰는 Model에 담긴 데이터를 기반으로 사용자에게 보여질 최종 HTML, XML 또는 다른 형식의 문서를 생성
  - 이 문서는 브라우저로 전달되어 사용자에게 표시됩니다.
7.  사용자 응답
  - 생성된 문서는 웹 서버를 통해 클라이언트(브라우저)로 전달
  - 사용자는 브라우저를 통해 해당 문서를 확인
