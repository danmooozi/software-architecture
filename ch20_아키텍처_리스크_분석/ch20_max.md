> 리스크 스토밍 활동을 통해 리스크를 도출, 평가, 식별하는 핵심 기술과 프랙티스를 소개
> 

### 20.1 리스크 매트릭스

- **리스크 분류**: 낮음(1), 중간(2), 높음(3)으로 분류
- **리스크 평가**:
    - **영향도** × **발생 가능성**으로 정량화
    - 1-2: 낮음 (밝은 회색)
    - 3-4: 중간 (중간 회색)
    - 6-9: 높음 (짙은 회색)
- **예시**:
    - **데이터베이스 가용성**:
        - **영향도**: 높음
        - **발생 가능성**: 낮음
        - **최종 리스크**: 중간 (3)
![Screenshot 2024-12-11 at 13 19 47](https://github.com/user-attachments/assets/0bf7b518-4fab-464e-9b3e-4085bb736782)


## **20.2** 리스크 평가

![Screenshot 2024-12-11 at 13 19 55](https://github.com/user-attachments/assets/88e61eb9-f7ea-4738-9d39-7802e5b70652)

- **리스크 평가 리포트** *(그림 20-2)*
    - **구성**: 리스크 매트릭스로 평가된 기준, 서비스/도메인 영역별 누적치
    - **리스크 등급**:
        - **낮음**: 1-2 (밝은 회색)
        - **중간**: 3-4 (중간 회색)
        - **높음**: 6-9 (짙은 회색)
- **리스크 비교 예시** *(그림 20-2)*
    - **누적 리스크**:
        - **데이터 무결성**: 17점 (최고 리스크)
        - **가용성**: 10점 (최저 리스크)
    - **도메인 영역**:
        - **고객 등록**: 24점 (최고 리스크)
        - **주문 이행**: 8점 (최저 리스크)
- **리스크 필터링** *(그림 20-3)*
    - **목적**: 중요한 리스크만 강조하여 신호대잡음비(SNR) 개선
        
      ![Screenshot 2024-12-11 at 13 20 04](https://github.com/user-attachments/assets/c4b480f3-acbe-4937-a1da-b6428da6852b)

- **리스크 방향성** *(그림 20-4)*
    
    ![Screenshot 2024-12-11 at 13 20 20](https://github.com/user-attachments/assets/5fac1d00-3ffc-4715-9749-b1ced918ec79)

    
    - **표시 방법**:
        - **부호**: + (개선), - (악화)
        - **화살표**: 방향 표시 (예: 성능 4-, 확장성 6+)
        - **색상**: 초록색(개선), 빨간색(악화)
- **명확한 방향성 표시** *(그림 20-5)*
    
    ![Screenshot 2024-12-11 at 13 20 32](https://github.com/user-attachments/assets/fc431e0f-7a1d-4987-b540-bdc82e85ca5c)

    
    - **방법**:
        - 리스크 등급 번호와 화살표 병기
        - 색상으로 방향성 강조 (빨간색: 악화, 초록색: 개선)
- **객관적 분석**
    - **방법**: 피트니스 함수로 리스크 흐름과 방향성 지속 측정

## 20.3 리스크 스토밍

### 1. **리스크 스토밍 개요**

- **정의**: 리스크 스토밍은 특정 범위 내의 아키텍처 리스크를 찾아내기 위한 **협력적 활동**. *(그림 20-6)*
- **목적**:
    - 아키텍트 한 명이 모든 리스크를 파악하기 어렵기 때문에, 여러 전문가와 함께 리스크를 식별하고 평가.
- **참여자**:
    - **아키텍트**: 리스크 스토밍을 주관하며 다이어그램 관리
    - **선임 개발자 및 기술 책임자**: 기술적 리스크 식별 및 해결 방안 논의
    - **개발자**: 구현 관점에서 리스크를 평가하고 아키텍처를 더 잘 이해

---

### 2. **리스크 스토밍 주요 리스크 영역**

- **검증되지 않은 기술**
- **성능 문제**
- **확장성**
- **가용성** (전이적 종속성 포함)
- **데이터 소실**
- **단일 장애 지점 (Single Point of Failure)**
- **보안 리스크**

---

### 3. **리스크 스토밍 수행 과정**

리스크 스토밍은 **개별 활동**과 **협력 활동**으로 나뉜다.

1. **식별 (Identification)** *(개별 활동)*
    - **개별 파트**에서 참가자들은 리스크 매트릭스를 사용해 각자 리스크를 할당한다.
    - **목적**: 각자 자신의 관점에서 리스크를 파악하고, 다른 사람의 의견에 방해받지 않도록 한다.
2. **합의 (Consensus)** *(협력 활동)*
    - 모든 참가자가 함께 모여 식별된 리스크에 대해 논의하고 합의점을 찾는다.
    - **목적**: 리스크에 대한 공감대를 형성하고, 평가 결과를 확정한다.
3. **완화 (Mitigation)** *(협력 활동)*
    - 합의된 리스크에 대해 해결 및 완화 방안을 논의한다.
    - **목적**: 리스크를 줄이기 위한 구체적인 계획을 수립한다.

---

### 4. **리스크 스토밍 도구: 아키텍처 다이어그램**

- **사용 방법**:
    - **전체 리스크 평가**: 종합 아키텍처 다이어그램 사용
    - **부분 리스크 평가**: 특정 서비스나 도메인 영역의 다이어그램 사용
- **아키텍트의 역할**:
    - 다이어그램을 최신 상태로 업데이트
    - 모든 참가자가 볼 수 있도록 다이어그램 관리

---

### 5. **리스크 스토밍 예시** *(그림 20-6)*

- **AWS 일래스틱 로드 밸런서**가 웹 서버(엔진엑스)와 각 EC2 인스턴스를 처리
- **애플리케이션 서비스**는 MySQL, 레디스 캐시, 몽고DB를 호출해 로그를 남김
- **푸시 확장 서버**도 MySQL, 레디스 캐시, 몽고DB와 연계

![Screenshot 2024-12-11 at 13 20 44](https://github.com/user-attachments/assets/8f20a720-125f-4aac-96e3-3248ca7677bb)

---

### 6. **리스크 스토밍의 핵심 활동**

1. **식별**: 각자 리스크를 할당
2. **합의**: 함께 리스크를 논의하고 확정
3. **완화**: 리스크 해결 방안 모색

리스크 스토밍을 통해 **리스크를 체계적으로 식별하고 평가**하며, 이를 바탕으로 **시스템의 안전성과 확장성**을 개선할 수 있다.

### 20.3.1 식별 (Identification)

참가자가 **독립적으로** 아키텍처 리스크를 찾아내는 활동.

1. **초대장 발송**: 아키텍트가 리스크 스토밍 일정을 안내하고, 아키텍처 다이어그램과 분석 영역을 공유한다.
2. **리스크 분류**: 참가자는 리스크를 **낮음(1-2), 중간(3-4), 높음(6-9)**으로 분류하고, 색상별 포스트잇에 기록한다.
3. **부문별 집중**: 혼란을 방지하기 위해 한 번에 **한 가지 리스크 부문**(예: 성능)만 분석하는 것이 좋다.

---

### 20.3.2 합의 (Consensus)

참가자들이 모여 리스크의 존재와 심각도를 **조율**하는 협력적 활동이다.

1. **포스트잇 부착**: 각자가 찾은 리스크를 아키텍처 다이어그램에 표시한다.
2. **리스크 검토**: 의견이 다르면 토론을 통해 합의한다.
3. **사례**:
    - **의견 차이**: 리스크 중간(3)과 높음(6)으로 평가된 경우, 이유를 설명하고 조정한다.
    - **지식 부족**: 특정 기술을 몰라 리스크를 높게 평가한 경우, 논의를 통해 정확히 판단한다.

---

### 20.3.3 완화 (Mitigation)

합의된 리스크를 **줄이거나 제거**하는 방안을 찾는 단계.

1. **리스크 대응 전략**: 아키텍처 변경, 리팩터링 등으로 리스크를 완화한다.
2. **비용-효과 분석**: 비용과 비즈니스 가치를 고려해 최적의 해결책을 선택한다.
3. **사례**: 고비용 클러스터링 대신 데이터베이스 분할로 비용을 절감하며 리스크를 완화한다.

**리스크 스토밍**은 리스크를 식별하고, 협력적으로 해결책을 찾는 중요한 프로세스이다.

### 20.4 애자일 스토리 리스크 분석

- 리스크 스토밍은 아키텍처뿐만 아니라 다른 소프트웨어 개발 분야에서도 유용하게 사용된다.
- 예를 들어, 애자일 이터레이션에서 유저 스토리의 리스크를 평가하기 위해 리스크 매트릭스를 활용한다.
- 매트릭스는 **영향도**와 **가능성**의 두 차원으로 리스크를 식별하고, 이를 통해 리스크가 높은 스토리를 우선 순위로 설정하여 관리한다.

### 20.5 리스크 스토밍 예시

### 콜 센터 시스템 요구사항

- **주요 요구사항**:
    - 서드파티 진단 엔진 사용, 250명의 간호사와 수십만 명의 셀프 서비스 환자 동시 지원
    - **HIPAA** 규정 준수, 데이터 요청 급증 대응, 간호사 프로필에 따른 통화 연결
    - **시스템 아키텍처**: 3개의 웹 기반 유저 인터페이스와 4개의 주요 서비스 (사례 관리 서비스, 간호사 프로필 관리 서비스 등)
        
        ![Screenshot 2024-12-11 at 13 20 56](https://github.com/user-attachments/assets/f424dced-df9d-4bce-8008-cd8a268d9778)

        

### 20.5.1 가용성

- **리스크 스토밍 결과**:
    - **중앙 데이터베이스**: 영향도 높고 가능성 중간, 리스크 높음 (6)
    - **진단 엔진**: 영향도 높고 가능성 알 수 없음, 리스크 높음 (9)
    - **의무 기록 가용성**: 리스크 낮음 (2)
- **해결책**:
    
    데이터베이스를 **2개로 분리**하여 가용성 향상 및 보안성 강화
    
    ![Screenshot 2024-12-11 at 13 21 05](https://github.com/user-attachments/assets/f442427d-56e5-4ece-ae3a-61562834aa1c)

    

![Screenshot 2024-12-11 at 13 21 17](https://github.com/user-attachments/assets/ba84f7ff-4e38-4d1d-a6d8-22eb6f4a2a9e)

### 20.5.2 탄력성

- **리스크 스토밍 결과**:
    - **진단 엔진**의 리스크 높음 (9), 예상 처리량을 초과할 가능성
    - **해결책**:
        - 비동기 큐와 **2개의 메시지 채널**을 추가하여 부하 분산
        - **진단 캐시**를 도입하여 요청량 감소
            
            ![Screenshot 2024-12-11 at 13 21 29](https://github.com/user-attachments/assets/5fe4d9cd-a380-448e-863b-e840d5bec674)

          

### 20.5.3 보안

- **리스크 스토밍 결과**:
    - **API 게이트웨이**에서 의무 기록 노출 위험, 리스크 높음 (6)
    - **해결책**:
        - **유저 유형별 API 게이트웨이 분리**로 보안성 강화
            
            
            ![Screenshot 2024-12-11 at 13 21 40](https://github.com/user-attachments/assets/b74606a0-6441-4bde-acab-1c1b8e73835d)


---

- 리스크 스토밍을 통해 가용성, 탄력성, 보안 측면에서 시스템 아키텍처를 개선할 수 있었다.
- **리스크 매트릭스**와 **아키텍처 검토**가 주요 역할을 하였으며, 이를 통해 시스템의 주요 리스크를 사전에 식별하고 해결책을 마련할 수 있었다.
