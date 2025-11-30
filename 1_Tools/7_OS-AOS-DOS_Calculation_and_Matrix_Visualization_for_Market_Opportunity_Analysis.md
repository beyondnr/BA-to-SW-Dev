# 시장기회 분석을 위한 OS-AOS-DOS 계산 방법과 매트릭스 시각화 방법

## 1. 기회점수(OS) & 조정형 기회점수(AOS)

### 개념 및 수식

* **전통적 기회점수 (OS):** 고객의 불만족 수준 계산에 고객의 기대치(Importance)를 두 번 반영하는 문제가 있어 실제 시장감각을 왜곡할 수 있습니다.
  * `OS = Importance + (Importance - Satisfaction) = Importance x 2 - Satisfaction`
* **조정형 기회점수 (AOS, Adjusted Opportunity Score):** 불만족 수준을 비율 계산 형태 `(1-Satisfaction/5)`로 도출한 뒤 Importance를 곱하여 현실적 혁신기회 강도를 산출합니다.
  * `AOS = Importance x (1 - Satisfaction/5)`

### AOS 점수 해석

| 항목                       | 설명                                             |
| :------------------------- | :----------------------------------------------- |
| **Importance**       | 고객에게 Pain/Goal이 얼마나 중요한가 (1~5점)     |
| **Satisfaction**     | 현재 이 Pain이 얼마나 잘 해결되고 있는가 (1~5점) |
| **1-Satisfaction/5** | 충족되지 않은 영역(Unmet Need)의 비율            |
| **AOS**              | "중요하지만 덜 해결된 문제"의 강도               |

### AOS 시각화 구조 및 사분면 해석

* **Top (High Importance):**
  * **Q1 (High AOS):** 혁신기회 (High Importance + Low Satisfaction) → JTBD 인터뷰 대상, MVP 실험 우선
  * **Q2 (중간 AOS):** 개선기회 (High Satisfaction) → 지속적 개선 필요
* **Bottom (Low Importance):**
  * **Q3 (Low AOS):** 유지관리 (Low Satisfaction) → UX·마케팅 최적화 중심
  * **Q4 (0 근처):** 과잉투자 (High Satisfaction) → 자원 분배 재검토

### 매트릭스 기준점 설정

1. **점수 척도 기반 단순 기준점:** Likert 5점 척도의 중간값(3.0)을 사용. (Satisfaction 3.0, Importance 3.0, AOS 2.0~2.5)
2. **데이터 분포 기반 기준점:** 전체 평균값과 표준편차를 이용. (예: Importance 평균 3.6, Satisfaction 평균 2.9 등 실제 평가 분포에 맞게 설정)

---

## 2. 평가 대상 정의

우리가 설계한 솔루션에 대한 페르소나 스펙트럼과 고객 여정 지도에 대하여 기존 솔루션 생태계 하에서 고객이 겪고 있는 Pain/Job 상황을 평가합니다.

| 분석 단계                | 평가 단위                         | 평가 대상 질문                                                                      |
| :----------------------- | :-------------------------------- | :---------------------------------------------------------------------------------- |
| **페르소나 단계**  | 각 페르소나의 주요 Pain-Goal      | "이 사람에게 가장 중요한 고통은 무엇인가?"                  |
| **고객 여정 지도** | 여정 단계별 Pain Point / 개선기회 | "고객 여정 중 어디서 좌절이 가장 큰가?"                     |
| **JTBD 인터뷰**    | Job Statement 단위                | "이 고객이 진보를 이루기 위해 수행하는 일(Job)은 무엇인가?" |

---

## 3. AOS 산출 5단계 워크플로우

1. **Pain 리스트 정리:** Persona/CJM에서 Pain Goal 정리
2. **Importance 평가:** 고객 입장에서 중요도 평가 (1~5)
3. **Satisfaction 평가:** 현재 충족 수준 평가 (1~5)
4. **AOS 계산:** `AOS = Importance x (1 - Satisfaction/5)`
5. **Matrix 시각화:** X축(Satisfaction), Y축(Importance), Bubble(AOS)

---

## 4. AOS에서 시장 가중형 점수 DOS로 확장하기

AOS는 고객 한 명의 중요도를 반영한 지표라면, **DOS(Discovered Opportunity Score)**는 시장 규모와 맥락을 곱해 산출합니다. (실제 VC, PM들이 쓰는 구조와 유사)

* **DOS 계산식:** `DOS = (Importance - Satisfaction) x Market Relevance`
  * *Market Relevance:* TAM-SAM-SOM 비중, 시장 성장률, 채택 난이도, 확산성 등을 고려한 시장 파급력 (0.1~1.0)

### DOS 시뮬레이션 프롬프트 템플릿

> **# Context**
> 나는 [산업/분야명] 시장에서 [타깃 페르소나]를 대상으로 신규 서비스 기획을 진행 중이다.
>
> **# Task**
> 아래 Pain/Goal 목록에 대해 각 항목별로 다음 항목을 평가하고 DOS 점수를 계산하라.
> (Pain/Goal | Importance | Satisfaction | Market Relevance | DOS)
>
> **# Rules**
>
> 1. DOS = (Importance - Satisfaction) * Market Relevance
> 2. Market Relevance는 TAM, 성장률, 채택난이도, 확산성 등을 고려해 평가하라.
> 3. 결과는 DOS 내림차순 정렬.
> 4. "기회 해석(Insight)" 항목 추가.

---

## 5. 시각화 작업 단계 및 Matrix

1. **Pain 선정:** 페르소나별 Pain 3~5개 선정
2. **AOS 계산:** Importance, Satisfaction 평가 후 산출
3. **DOS 계산:** Market Relevance 추가하여 산출
4. **시각화:** AOS-DOS 결합형 Matrix 생성

### AOS-DOS 결합형 Matrix 구조

* **High AOS (Strong Need):**
  * **Q1. 혁신기회:** High AOS / High DOS
  * **Q2. 개선기회:** High AOS / Low DOS
* **Low AOS (Weak Need):**
  * **Q3. 유지관리:** Low AOS / High DOS
  * **Q4. 과잉투자:** Low AOS / Low DOS
