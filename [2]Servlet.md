# Servlet

- 서블릿은 톰캣 같은 웹 애플리케이션 서버를 직접 설치하고, 그 위에 서블릿 코드를 클래스 파일로 빌드해서 올린 다음에 톰캣 서버를 실행하면 된다.
- 위 과정이 너무 번거로워서, 스프링 부트는 톰캣 서버를 내장하고 있으므로, 톰캣 서버 설치 없이 편리하게 서블릿 코드를 실행할 수 있다.

## SpringBoot Servlet 환경 구성

`@ServletComponentScan` : 나의 패키지를 포함, 하위 패키지를 찾아서 서블릿을 자동 등록한다

## Servlet 컨테이너 동작 방식
1. 스프링부트 시작하면서 스프링 부트가 내장 톰캣 서버를 띄운다
2. 내장 톰캣 서버는 내부에 서블릿 컨테이너 기능을 가지고 있어서, 서블릿 컨테이너를 통해 서블릿을 생성한다
3. HTTP 요청이 들어오면, WAS (Web Application Server)는 HTTP 요청이 들어오면 HTTP 요청 메시지를 기반으로 request 객체를 생성한다
4. WAS는 Response 객체 정보로 HTTP 응답 정보를 생성하여 반환한다


## HttpServletRequest
- HTTP 요청 메시지를 개발자가 직접 파싱해서 사용해도 되지만, 불편하다 
- 서블릿은 개발자가 HTTP Request 메시지를 편리하게 사용할 수 있도록 HTTP Request 메시지를 파싱한다
- 그리고 그 결과를 `HttpServletRequest` 객체에 담아서 제공한다

### 임시 저장소 기능
- 저장 : `request.setAttribute(name, value)`
- 조회 : `request.getAttribute(name)`

### 세션 관리 기능
- `request.getSession(create: true)`

## HttpServletRequest 사용 방법

