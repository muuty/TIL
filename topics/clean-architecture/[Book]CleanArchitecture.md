
# 1부. 소개
#### 6p
설계란 무엇인가? 아키텍처는? 둘 사이에는 어떤 차이가 있는가? (...) 첫째로 주장하고 싶은 바는 둘 사이에는 차이가 없다는 점이다.

#### 7p
소프트웨어 아키텍처의 목표는 필요한 시스템을 만들고 유지보수하는 데 필요한 인력을 최소화하는 데 있다.


#### 38p
좋은 아키텍처를 만드는 일은 객체지향 설계 원칙을 이해하고 응용하는 데서 출발한다.


#### 51
소프트웨어 아키텍트 관점에서 정답은 명확하다. OO란 다형성을 이용하여 전체 시스템의 모든 소스 코드 의존성에 대한 절대적인 제어 권한을 획득할 수 있는 능력이다. OO를 사용하면 아키텍트는 플러그인 아키텍처를 구성할 수 있고, 이를 통해 고수준의 정책을 포함하는 모듈은 저수준의 세부사항을 포함하는 모듈에 대해 독립성을 보장할 수 있다.


# 3부 설계 원칙
---
### SOLID 원칙의 목적 62p
SOLID 원칙의 목적은 중간 수준의 소프트웨어 구조가 아래와 같도록 만드는 데 있다.
- 변경에 유연하다.
- 이해하기 쉽다.
- 많은 소프트웨어 시스템에 사용될 수 있는 컴포넌트의 기반이 된다.


### SRP 원칙
SRP의 최종 버전은 아래와 같다.
'하나의 모듈은 오직 하나의 액터에 대해서만 책임져야 한다.'

### OCP 원칙
소프트웨어 객체는 확장에는 열려 있어야 하고, 변경에는 닫혀 있어야 한다.
이러한 목표를 달성하려면 시스템을 컴포넌트 단위로 분리하고, 저수준 컴포넌트에서 발생한 변경으로부터 고수준 컴포넌트를 보호할 수 있는 형태의 의졵성 계층구조가 만들어지도록 해야 한다.

### 리스코프 치환법칙
S타입의 객체 o1 각각에 해당하는 T1 타입 객체 o2가 있고, T 타입을 이용해서 정의한 모든 프로그램 P에서 o2의 자리에 o1을 치환하더라도 P의 행위가 변하지 않는다면, S는 T의 하위 타입이다.

### 인터페이스 분리 원칙
오퍼레이션을 인터페이스 단위로 분리하여서, 자신이 사용하지 않는 메서드에 의존하지 않아야 한다.

### 의존성 역전 원칙
'유연성이 극대화된 시스템'이란 소스코드 의존성이 추상에 의존하며 구체에는 의존하지 않는 시스템이다.
- 변동성이 큰 구체 클래스를 참조하지 말라. 대신 추상 인터페이스를 참조하라,
- 변동성이 큰 구체 클래스로부터 파생하지 말라.
- 구체 함수를 오버라이드 하지 말라.
- 구체적이며 변동성이 크다면 절대로 그 이름을 언급하지 말라.




# 컴포넌트 원칙
---

### 컴포넌트의 정의 - 100p
컴포넌트는 시스템의 구성 요소로 배포할 수 있는 가장 작은 단위다.

### 컴포넌트 내 클래스 배치에 대한 원칙 - 108p
- 어떤 클래스를 어떤 컴포넌트에 포함시켜야 할까?
- 세 가지 원칙을 참고할 수 있다.
    - REP: 재사용/릴리즈 등가 원칙
    - CCP: 공통 폐쇄 원칙
    - CRP: 공통 재사용 원칙

### REP: 재사용/릴리스 등가 원칙
- 재사용 단위는 릴리스 단위와 같다.
- 단일 컴포넌트는 응집성 높은 클래스와 모듈들로 구성되어야 한다. 컴포넌트를 구성하는 모든 모듈은 서로 공유하는 중요한 테마나 목적이 있어야 한다.


### CCP: 공통 폐쇄 원칙
- 동일한 이유로 동일한 시점에 변경되는 클래스를 같은 컴포넌트로 묶어라. 서로 다른 시점에 다른 이유로 변경되는 클래스는 다른 컴포넌트로 묶어라.
- 대다수의 애플리케이션에서 유지보수성은 재사용성보다 훨씬 중요하다. 코드가 변경되어야 한다면, 이러한 변경이 여러 컴포넌트에 분산되어 발생하기보다는, 차라리 변경 모두가 단일 컴포넌트에서 발생하는 편이 낫다.


### CRP: 공통 재사용 원칙
- 컴포넌트 사용자들을 필요하지 않는 것에 의존하게 강요하지 말라.



## 컴포넌트 사이의 관계에 대한 법칙들
- ADP: 의존성 비순환 원칙
    - 컴포넌트 의존성 그래프에 순환이 있어서는 안된다.
- SDP: 안정된 의존성 법칙
    - 더 안정된 쪽에 의존하라.
- SAP: 안정된 추상화 원칙
    - 컴포넌트는 안정된 정도만큼만 추상화되어야 한다.



# 5부. 아키텍처

### 아키텍처의 정의 - 142p
- 소프트웨어 시스템의 아키텍처란 시스템을 구축했던 사람들이 만들어낸 시스템의 형태다. 그 모양은 시스템을 컴포넌트로 분할하는 방법, 분할된 컴포넌트를 배치하는 방법, 컴포넌트가 서로 의사소통하는 방식에 따라 정해진다.

### 아키텍처의 목적 - 143p
- 아키텍처의 주된 목적은 시스템의 생명주기를 지원하는 것이다. 좋은 아키텍처는 시스템을 쉽게 이해하고, 쉽게 개발하며, 쉽게 유지보수하고, 또 쉽게 배포하게 해준다. 아키텍처의 궁극적인 목표는 시스템의 수명과 관련된 비용은 최소화하고, 프로그래머의 생산성은 최대화하는 데 있다.


### 아키텍트의 목표 - 147p
- 아키텍트의 목표는 시스템에서 정책을 가장 핵심적인 요소로 식별하고, 동시에 세부사항은 정책에 무관하게 만들 수 있는 형태의 시스템을 구축하는 데 있다. 이를 통해 세부사항을 결정하는 일은 미루거나 연기할 수 있게 된다.
- 좋은 아키텍트는 결정되지 않은 사항의 수를 최대화한다.
- 아키텍트는 필요한 시스템을 만들고 유지하는 데 드는 인적 자원을 최소화한다.


### 인적 자원의 효율을 떨어뜨리는 요인 - 170p
- 인적 자원의 효율을 떨어뜨리는 요인은 바로 결합이다. 특히 너무 일찍 내려진 결정에 따른 결합이다.
- 어떤 종류의 결정이 이른 결정일까? 바로 시스템의 업무 요구사항, 즉 유스케이스와 아무런 관련이 없는 결정이다. 프레임워크, 데이터베이스, 웹 서버, 유틸리티 라이브러리, 의존성 주입에 대한 결정 등이 여기 포함된다.


### 저수준에서 고수준으로 - 194p
- 좋은 아키텍처라면 각 컴포넌트를 연결할 때 의존성의 방향이 컴포넌트의 수준을 기반으로 연결되도록 만들어야 한다. 즉, 저수준 컴포넌트가 고수준 컴포넌트에 의존하도록 설계되어야 한다.
- 수준을 엄밀하게 정의하자면 '입력과 출력까지의 거리'다. 입력과 출력 모두로부터 멀리 위치할수록 정책의 수준은 높아진다.



### 소리치는 아키텍처 - 208p
- 상위 수준의 디렉토리 구조, 최상위 패키지에 담긴 소스 파일을 볼 때, 이 아키텍처는 "헬스 케어 시스템이야" 또는 "재고 관리 시스템이야"라고 소리치는가? 아니면 "레일스야", "스프링/하이버네이트야", 아니면"ASP야"라고 소리치는가?

### 전달 메커니즘은 미루어야 할 결정사항이다 - 210p
- 과도한 문제를 일으키거나 근본적인 아키텍처를 뜯어고치지 않더라도 시스템을 콘솔 앱, 웹 앱, 리치 클라이언트 앱, 심지어 웹 서비스 앱으로도 전달할 수 있어야 한다.



### 클린 아키텍처 - 216~218p
- 이러한 아키텍처가 동작하도록 하는 가장 중요한 규칙은 의존성 규칙이다. "소스 코드 의존성은 반드시 안쪽으로, 고수준의 정책을 향해야 한다."

- 엔티티
    -  전사적인 핵심 업무 규칙을 캡슐화한다. 엔티티는 메서드를 가지는 객체이거나 일련의 데이터 구조와 함수의 집합일 수도 잇다.

- 유스케이스
    - 유스케이스는 애플리케이션에 특화된 업무 규칙을 포함한다. 또한 유스케이스 계층의 소프트웨어는 시스템의 모든 유스케이스를 캡슐화하고 구현한다. 유스케이스는 엔티티로 들어오고 나가는 데이터 흐름을 조정하며, 엔티티가 자신의 핵심 업무 규칙을 사용해서 유스케이스의 목적을 달성하도록 이끈다.

- 인터페이스 어댑터
    - 어댑터는 데이터를 유스케이스와 엔티티에게 가장 편리한 형식에서 데이터나 웹 같은 외부 에이전시에게 가장 편리한 형식으로 변환한다. 마찬가지로 이 계층은 엔티티와 유스케이스에게 가장 편리한 형식에서 영속성용으로 사용 중인 임의의 프레임워크(즉, 데이터베이스)가 이용하기에 가장 편리한 형식으로 변환한다.


- 프레임워크와 드라이버
    - 가장 바깥족 계층은 일반적으로 데이터베이스나 웹 프레임워크 같은 프레임워크나 도구들로 구성된다.
    - 프레임워크와 드라이버 계층은 모든 세부사항이 위치하는 곳이다. 웹은 사부사항이다. 데이터베이스는 세부사항이다.


### 테스트 - 262~263p
- 테스트는 태생적으로 의존성 규칙을 따른다.
    - 시스템 태부의 어떤 것도 테스트에 의존하지 않으며, 테스트는 시스템의 컴포넌트를 향해, 항상 원의 안쪽으로 의존한다.
- 소프트웨어 설계의 첫 번째 규칙은 언제나 같다. 변동성이 있는 것에 의존하지 말라. GUI