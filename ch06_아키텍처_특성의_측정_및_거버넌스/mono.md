# 6. 아키텍처 특성의 측정 및 거버넌스

## 아키텍처 특성 측정

물리학이 아니다 : 아키텍처 특성은 대부분 의미가 모호합니다.

정의가 너무 다양하다 : 성능 같은 중요한 특성에 대한 정의가 같은 조직에서도 부서마다 일치하지 않는다.

너무 복합적이다 : 바람직한 아키텍처 특성은 대부분 더 작은 다른 여러 특성들로 구성됩니다.

이 세 가지 문제는 아키텍처 특성을 객관적으로 정의하면 모두 해결됩니다. 

?? 해결 된다고 ?? 

## 운영적 측정

아키텍처 특성은 성능,확장성처럼 비교적 정확하게 측정할수 있는 것도 많지만,팀 목표에 따라 그에 따른 해석은 미묘하게 갈릴 때가 많습니다.

수준 높은 팀은 달성하기 어려운 *성능* 수치를 정하는 대신,통계 분석 결과로 얻은 나름대로의정의에 기반합니다

도구가 발전하고 이해도가 높아지면서 팀이 측정할 수 있는 아키텍처 특성은 빠르게 진화하고 있습니다

## 구조적 측정

성능처럼 목표치가 확실하지 않은 메트릭도 있습니다.

잘 정의된 모듈성처럼 내부 구조에 관한 특성도 그렇습니다.

## 거버넌스와 피트니스 함수

일반적으로 소프트웨어 프로젝트에서 긴급성을 무시할 수는 없지,그래도 아키텍트는 거버넌스 메커니즘을 강구해야 합니다.아키텍처 거버넌스는 이름에서도 느껴지지만 아키텍트가 영향력을 행사하려는 모든 소프트웨어 개발 프로세스를 포괄합니다.

### 아키텍처특성 관리

조직 내부에서 소프트웨어 품질 보장 업무는 아키텍처 범주 안에 속하므로 아키텍처 거버넌스 항목입니다.

### 피트니스 함수

결과가 목표에 얼마나 근접했는지를 나타내는 목표 함수가 바로 피트니스 함수

### 아키텍처 피트니스 함수

어떤 아키텍처 특성 （또는 그런 특성들의 조합）의 객관적인 무결성을 평가하는 모든 메커니즘

## 순환의존성

모듈성은 대부분의 아키텍트가 관심을 기울이는 암묵적인 아키텍처 특성입니다.

아키텍트가 좋은 의도를 갖고 있더라도 많은 플랫폼에서 그에 반하는 어쩔 수 없는 일들이 벌어집니다

모듈성 관점에 바라볼 때 이와 같이 클래스나 컴포넌트를 별 생각없이 마구 임포트하는 건 정말 좋지 않습니다

## ‘메인 시퀀스로부터의 거리’ 피트니스 함수

피트니스 함수는 무거운 거버넌스 메커니즘보다는 아키텍트가 중요한 아키텍처 원칙을 표현하고 자동으로 검증할 수 있는 메커니즘을 보장합니다. 안전하지 않은 코드를 릴리스하면 안 된다는 것쯤은 개발자도 알고 있지만,일정의 압박에 시달리다 보면 다른 수십,수백 가지와 우선순위 경합이 벌어질 것입니다.
아키텍트가 보안 멍키 같은 구체적인 도구와 피트니스 함수 같은 일반적인 도구를 잘 활용하면 중요한 거버넌스 체크를 아키텍처 하부에 구체화할수 있습니다.
