# 3장. 모듈성
### 모듈성

- 소프트웨어 아키텍처의 핵심 원칙으로, 시스템 구조와 유지보수성에 큰 영향을 미친다.
- 아키텍트가 모듈성을 효과적으로 구현하고 관리하는 것은 매우 중요하다.

## 3.1 정의

**사전적 정의**

- 복잡한 구조를 만드는 데 쓰이는 각각의 표준화한 부품이나 독립적인 단위
    - 이런 모듈성을 이용해 객체 지향 언어의 클래스나 함수형 언어의 함수가 될 만한 서로 연관된 코드를 논리적으로 묶는다.

**코드 패키징**

- 아키텍트는 개발자가 코드를 어떻게 패키징하는지 알아야 한다.
- 아키텍처에 중요한 영향을 미치기 때문.
- 여러 패키지가 서로 단단히 커플링되어 있으면 그 중 하나를 다른 작업에 사용하기가 아주 어려워지기 때문

**논리적 구분과 물리적 구분**

- 논리적 구분
    - 클래스, 함수처럼 코드를 묶어 놓은 덩어리
- 물리적 구분
    - 실제 시스템의 배포 및 실행 구조
    - 아키텍처를 재구축할 때에는 이렇게 커플링된 구조가 모놀리스를 나누는 데 걸림돌이 된다.

→ 따라서 모듈성은 특정 플랫폼에서 함축되어 있거나 불가피한 물리적 분리와 다른 개념으로 바라보는 게 좋다.

**예시 : 닷넷 플랫폼**

- 개발자는 상이한 (컴포넌트, 클래스 등의) 소프트웨어 자산을 서로 구분하기 위해 정확한 완전 정규화 명칭을 필요로 한다.
- 대부분의 언어에도 변수, 함수, 메서드 등을 구성하는 데 필요한 네임스페이스 역할을 하는 모듈성 메커니증이 존재
    - 가령, 자바 패키지 구조는 실제 클래스 파일의 물리적인 디렉터리 구조를 그대로 나타낸다.

## 3.2 모듈성 측정

### 3.2.1 응집

- 한 모듈듸 파트가 동일한 모듈 안에 얼마나 포함되어 있는지를 나타낸다.
- 모듈을 구성하는 파트가 얼마나 서로 연관되어 있는가, 하는 것.

**응집도 측정 범위**

- 기능적 응집
    - 모듈의 각 파트는 다른 파트와 연관되어 있고
    - 기능상 꼭 필요한 모든 것이 모듈에 들어있다.
- 순자적 응집
    - 두 모듈이, 한쪽이 데이터를 출력하면 다른 한쪽이 그것을 입력 받는 형태로 상호작용
- 소통적 응집
    - 두 모듈이, 각자 정보에 따라 작동하고 어떤 출력을 내는 형태로 통신체인을 형성
- 절차적 응집
    - 두 모듈은 정해진 순서대로 실행
- 일시적 응집
    - 모듈은 시점 의존성에 따라 연관
- 논리적 응집
    - 모듈의 내부 데이터는 기능적이 아니라, 논리적으로 연관되어 있는 경우.
- 동시적 응집
    - 같은 소스 파일에 모듈 구성 요소가 들어 있지만, 그 외에는 아무 연관성이 없다.

### LCOM

- 공유 필드를 통해 공유되지 않는 메서드의 총 개수

### 3.2.2 커플링

- 그래프 이론에 기반한 좋은 분석 도구들이 많다.
- 메서드의 호출과 반환은 호출 그래프를 형성하므로 수학적인 분석이 가능

**구심 커플링**

- 코드 아티팩트(컴포넌트, 클래스, 함수)로 유입되는 접속 수
- 해당 아티팩트가 다른 부분에 의해 얼마나 많이 사용되는지를 측정

**원심 커플링**

- 다른 코드 아티팩트로 유출되는 접속 수를 나타낸다.

### 3.2.3 추상도, 불안정도

**추상도**

- (추상 클래스, 인터페이스 등의) 추상 아티팩트와 구상 아티팩트의 비율
- 즉, 구현 대비 추상화 정도를 나타낸 것.

**불안정도**

- 코드베이스의 변동성을 의미
- 불안정도가 높은 코드베이스는 변경 시 커플링이 높아 깨지기 쉽다.

### 3.2.4 메인 시쿼스로부터의 거리

- 아키텍처 구조를 평가하는 몇 가지 전체적인 메트릭 중 하나로, 불안정도와 추상도를 이용하여 계산

### 3.2.5 커네이선스

**정적 커네이선스**

**명칭 커네이선스**

**타입 커네이선스**

**의미 커네이선스 또는 관례 커네이선스**

**위치 커네이선스**

**알고리즘 커네이선스**

**동적 커네이선스**

**실행 커네이선스**

**시점 커네이선스**

**값 커네이선스**

**식별 커네이선스**

**커네이선스 속성**

### 3.2.6 커플링과 커네이선스 메트릭을 통합

- 구조적 프로그래밍에서 데이터 커플링이라고 부르는 커네이선스는 커플링이 어떻게 나타나야 하는지 알려줌.

## 3.3 모듈에서 컴포넌트로
