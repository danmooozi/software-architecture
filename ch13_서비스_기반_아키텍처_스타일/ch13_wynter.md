# CHAPTER13 서비스 기반 아키텍처 스타일

마이크로서비스 아키텍처 스타일의 일종으로, 아키텍처가 유연해서 실용적인 아키텍처 스타일 중 하나입니다.

## 13.1 토폴로지

서비스 기반 아키텍처의 기본 토폴로지는 각각 따로 배포된 유저 인터페이스와 원격 서비스, 그리고 모놀리스 데이터베이스로 이루어진 대규모 분산 레이어 구조입니다.

이 아키텍처 스타일에서 서비스는 큼지막한 단위로 분리해 별도로 배포하는 애플리케이션의 일부입니다. 서비스를 배포하는 방식 자체는 여느 모놀리식 애플리케이션과 동일하므로 컨테이너화가 필수는 아닙니다.

서비스 기반 아키텍처의 도메인 서비스는 각각 단일 인스턴스로 배포하지만, 인스턴스를 여럿 둘 수도 있습니다.

서비스는 원격 액세스 프로토콜로 유저 인터페이스 외부에서 접속할 수 있습니다.

서비스 개수가 적어서 데이터베이스 커넥션은 대개 문제가 안 되지만 데이터베이스 자체의 변경은 이슈가 될 수 있습니다.

## 13.2 토폴로지 변형

## 13.3 서비스 설계 및 세분도

도메인 서비스는 레이어드 아키텍처 스타일이나 모듈러 모놀리스 아키텍처 스타일로 설계할 수 있음

어떻게 설계하든 유저인터페이스 -> 비즈니스 기능을 위해 API 액세스 퍼사드가 필요함. 이 친구는 비즈니스 요청을 오케스트레이트함. 이런 요청을 마이크로서비스 아키텍처에서 처리한다면 별도 배포된 다수의 전용 원격 서비스를 오케스트레이션해야 합니다. 세분도 관점에서 보면, 내부 클래스 수준의 오케스트레이션과 외부 서비스의 오케스트레이션이라는 차이점이 마이크로서비스와의 중요한 차이점.

## 13.4 데이터베이스 분할

테이블 스키마 변경 시 문제가 될 수 있습니다. 테이블 스키마를 올바르게 변경하지 않을 경우 모든 서비스에 악영향을 미치기 때문에. 엔티티 객체를 커스텀 공유 라이브러리에 둡니다. 이게 결국 언 ㅡ서비스가 실제로 테이블 변경에 영향을 받을지를 미리 예측하기란 어렵습니다.

리스크를 낮추는 방법은 데이터베이스를 논리적으로 분할하고 이런 논리 분할을 연합 공유 라이브러리를 통해 명시하는 것입니다.

## 13.5 아키텍처 예시

## 13.6 아키텍처 특성 등급

평균 등급이 높은듯.

## 13.7 언제 이 아키텍처 스타일을 사용하는가

어쩌면 가장 실용적인 아키텍처. 도메인 주도 설계와 궁합이 잘 맞습니다. ACID 트랜잭션이 더 잘 보존됩니다.

우리회사에서는 이 서비스 기반 아키텍처 스타일을 기본적으로 쓰는 것 같넹???
