# Spring 예상 면접 질문

## ✅ Spring이 뭐죠?

: 자바 플랫폼을 위한 오픈소스 애플리케이션 프레임워크

: 자바 엔터프라이즈 개발을 편하게 해주는 오픈소스 경량급 애플리케이션 프레임워크

: 동적인 웹 사이트 개발하기 위한 여러 가지 서비스를 제공함

: 대한민국 공공기관의 웹 서비스 개발 시 사용을 권장하고 있는 전자정부 표준프레임워크의 기반 기술.

### 💡 스프링(Spring)

스프링 프레임워크(Spring Framework)는 자바 플랫폼을 위한 오픈소스 애플리케이션 프레임워크로서 간단히 스프링이라고도 불린다. 동적인 웹 사이트를 개발하기 위한 여러가지 서비스를 제공하고 있다.

스프링은 DI, IOC를 통해 재사용 및 유지보수가 용이한 코드를 작성할 수 있고, 확장성을 가진 코드를 설계할 수 있다 또한 스프링이 제공해주는 기능들을 통해 개발자는 비즈니스 로직에만 집중할 수 있기 때문에 생산성을 증가 시킬 수 있다는 장점을 가지고 있다.

## ✅ Spring 프레임워크의 특징에 대해 말해보세요.

**DI (Dependency Injection) 의존성 주입**

- 설정 파일이나 어노테이션을 통해 객체간의 의존 관계를 설정하여 개발자가 직접 의존하는 객체를 생성할 필요없음

**AOP(Aspect Oriented Programming) 관점 지향 프로그래밍**

- 애플리케이션의 핵심 기능과 공통 기능을 각각 분리하여 개발할 수 있게 해줌
- 로직을 기준으로 중복된 코드들(공통 관심사항)을 뽑아서 Aspect로 모듈화하여 재사용하는 것입니다.
- 트랜잭션, 로깅, 보안 등 여러 모듈, 여러 계층에서 공통으로 필요로 하는 기능의 경우 해당 기능을 분리해 관리.

**POJO(Plain Old Java Object)**

- POJO란 **특정 기술에 종속되지 않는 순수한 자바 객체**를 의미
- **"진정한 POJO란 객체지향적인 원리에 충실하면서, 환경과 기술에 종속되지 않고 필요에 따라 재활용될 수 있는 방식으로 설계된 객체이다"**
- 순수 자바만을 사용하여 만든 객체이므로 특정 기술이나 환경에 종속되지 않는다.
- 코드가 단순해져서 테스트, 디버깅 또한 쉬워짐

**IOC(Inversion of Control) : 제어 반전**

: **컨트롤의 제어권이 개발자가 아니라 프레임워크에 있다는 뜻.**

: **객체의 생성부터 모든 생명주기의 관리까지 프레임워크가 주도하고 있음.**

: 객체를 생성하고, 직접 호출하는 프로그램이 아니라, 만들어둔 자원을 호출해서 사용.

## ✅ Spring과 Springboot 차이점에 대해 말해보세요.

## Spring Boot?

**스프링 프레임워크는 기능이 많은만큼 환경설정이 복잡한 편이다. 이에 어려움을 느끼는 사용자들을 위해 나온 것이 바로 스프링 부트다.** 스프링 부트는 스프링 프레임워크를 사용하기 위한 설정의 많은 부분을 자동화하여 사용자가 정말 편하게 스프링을 활용할 수 있도록 돕는다. 스프링 부트 starter 디펜던시만 추가해주면 바로 API를 정의하고, 내장된 탐캣이나 제티로 웹 애플리케이션 서버를 실행할 수 있다. 심지어 스프링 홈페이지의 이니셜라이저를 사용하면 바로 실행 가능한 코드를 만들어준다. 실행환경이나 의존성 관리 등의 인프라 관련 등은 신경쓸 필요 없이 바로 코딩을 시작하면 된다. 그리고 바로 그것이 스프링의 키 포인트이다.

## 차이점

Spring Boot는 Spring framework와 몇 가지면에서 차이가 있다.

- 1. **Embed Tomcat을 사용하기 때문에**, (Spring Boot 내부에 Tomcat이 포함되어있다.) **따로 Tomcat을 설치하거나 매번 버전을 관리해 주어야 하는 수고로움을 덜어준다.**
- 2. **starter을 통한 dependency 자동화** :아마 Spring 유저들이 가장 열광한 기능이 아닐까 싶다. 과거 Spring framework에서는 각각의 dependency들의 호환되는 버전을 일일이 맞추어 주어야 했고, 때문에 하나의 버전을 올리고자 하면 다른 dependeny에 까지 영향을 미쳐 version관리에 어려움이 많았다. 하지만, 이제 starter가 대부분의 dependency를 관리해주기 때문에 이러한 걱정을 많이 덜게 되었다.
- 3. **XML설정을 하지 않아도 된다.**
- 4. **jar file을 이용해 자바 옵션만으로 손쉽게 배포가 가능하다.**Spring Actuaor를 이용한 애플리케이션의 모니터링과 관리를 제공한다.

### 스프링부트(Spring Boot)

스프링부트는 스프링을 더 쉽게 이용하기 위한 도구라고 볼 수 있다. 스프링을 사용할 때 이것저것 세팅을 해야 될 요소가 너무 많아 불편함이 있었는데 스프링부트는 매우 간단하게 프로젝트를 설정할 수 있게하여 스프링 개발을 조금 더 쉽게 만들어주는 역할을 하고 있다.

!https://user-images.githubusercontent.com/70622731/156905823-02f58d50-93b3-4df5-a09a-9ae99a92b45d.png

### 스프링부트는 스프링에 어떤점이 개선된걸까?

1. 의존성관리
2. 자동설정
3. 내장 WAS

### 1. 의존성 관리

기존 Spring은 개발에 필요한 모듈의 의존성을 각각 다운받아줘야 했으며, 각 모듈의 버전을 개발자가 하나하나 명시해줘야했다.

SpringBoot는 `spring-boot-starter`를 통해 의존성 관리를 더 편리하게 해준다.

`spring-boot-starter`는 프로젝트에 설정해야 할 다수의 의존성들을 starter가 이미 포함하고 있기 때문에 우리는 starter에 대한 의존성 추가 만으로도 프로젝트를 시작하거나 새로운 기능을 추가할 수 있다.

`spring-boot-starter-jpa` 의존성을 추가했을 때 `spring-aop`, `spring-jdbc`등의 의존성이 이미 안에 선언되어 있다.

!https://user-images.githubusercontent.com/70622731/156871620-45bbc495-d399-4453-b90a-79377fec524e.png

`spring-boot-starter-jpa` 안으로 들어가 보면 이미 여러 의존성들이 정의되어 있어 starter만 정의하여도 쉽게 하위 의존성들을 관리할 수 있게된다.

!https://user-images.githubusercontent.com/70622731/156871566-091dd031-b332-4f74-a390-3c82d3591256.png

그리고 의존성을 추가할 때 Spring에서는 버전을 개발자가 직접 명시해줬어야 했는데 SpringBoot는 버전을 명시할 필요없이 가장 적합한 버전을 설정해준다.

maven인 경우 의존성들을 부모 자식관계로 관리하기 때문에 `spring-boot-stater-parent`를 통해 각 모듈의 현재 스프링부트 버전에 가장 적합한 버전을 제공해준다.

!https://user-images.githubusercontent.com/70622731/156871732-abd5a8e2-b47e-4ebf-8bb4-bec3b6b177ef.png

gradle인 경우는 `io.spring.dependency-management` 플러그인을 통해 각 모듈의 현재 스프링부트 버전에 가장 적합한 버전을 제공해준다.

!https://user-images.githubusercontent.com/70622731/156871454-ff5ffb7c-4761-4670-9173-2d4ca7e27aa0.png

### 2. 자동설정

기존의 스프링은 환경설정이 복잡하고 많은 설정을 했어야 했는데(db연결할때 datasource 설정을 매번 직접 bean을 생성했어야 했다.) 스프링부트에서는 이러한 환경설정을 @SpringBootApplication을 통해 자동설정을 해준다.

!https://user-images.githubusercontent.com/70622731/156871833-67330d59-6f1d-4a85-abea-1ba2aa662263.png

@SpringBootApplication이 어떠한 역할을 하는지 알아보기 위해서 안으로 들어가보면

!https://user-images.githubusercontent.com/70622731/156871862-9f1b9f09-1445-431d-a21c-a2c84f2f7461.png

위 그림과 같이 여러 어노테이션이 붙어있다.

**@SpringBootConfiguration**

SpringBoot의 설정을 나타내는 어노테이션으로, Spring의 @Configuration을 대체한다.

**@EnableAutoConfiguration**

자동 설정의 핵심 어노테이션으로, 클래스 경로에 지정된 내용을 기반으로 설정 자동화를 수행한다.

**@ComponentScan**

basePackages 프로퍼티 값에 별도의 경로를 설정하지 않으면 해당 어노테이션이 위치한 패키지가 루트경로가 되어 빈으로 등록할 클래스들을 탐색한다.

### SpringBoot에 bean 등록과정

SpringBoot는 Bean을 두 번에 걸쳐 등록한다.

1. @ComponentScan

처음에는 Spring과 마찬가지로 Component-scan을 통해 component를 찾고 bean 생성을 진행한다. 그 과정에서 우리가 설정한 bean들이 생성된다.

1. @EnableAutoConfiguration

그 후에는 @EnableAutoConfiguration으로 추가적인 Bean들을 읽어서 등록하게 된다. 메인 클래스(@SpringBootApplication)를 실행하면, @EnableAutoConfiguration에 의해 META-INF/spring.factories 안에 들어있는 수많은 자동 설정들이 조건에 따라 적용이 되어 수 많은 Bean들이 생성되고, 스프링 부트 어플리케이션이 실행되는것이다.

즉, SpringBoot는 Component scan을 통해서 모은 component들의 정보와 META-INF/spring.factories 파일에 사전 정의한 auto-configuration 내용에 의해 bean 생성을 진행한다.

!https://user-images.githubusercontent.com/70622731/156872544-8ffef322-9cc5-42e3-8fff-0b1db4586e1a.png

### 3. 내장 WAS

기존 Spring을 이용한 프로젝트는 war(Web application ARchive)파일로 배포할 수 있었다. war파일은 웹 어플리케이션을 압축해 저장해놓은 파일로, tomcat과 같은 was에서 돌아갈 수 있는 구조를 담고 있었다.

따라서 Spring으로 개발한 프로젝트를 배포하기 위해서는 웹어플리케이션이 압축된 war파일과 프로그램을 실행시킬 was가 필요했다.

!https://user-images.githubusercontent.com/70622731/156872719-d24361b1-d159-4e30-a5d6-c6e7b7ce53b1.png

war파일을 실행시킬 was를 직접 설정해주어야 한다.

하지만 SpringBoot는 Tomcat이나 Jetty같은 내장 서버를 가지고 있기 때문에 jar 파일로 배포할 수 있다. 따라서 SpringBoot로 개발한 프로젝트를 배포하기 위해서는 단순히 jar 파일만 필요하다.
