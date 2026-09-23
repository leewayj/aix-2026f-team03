# 4주차 활동지 / Week 4 Worksheet

**주제 선택과 요구 명세 / Choosing a problem & writing the spec**

- 작성일 / Date: 2026. 09. 23
- 참여자 / Present: 정윤지, 김은총, 박강민, 이진호

---

## ① 주제 선택 / Choosing one problem

| 항목 Item | 내용 |
|---|---|
| 선택한 주제 Chosen | 도서관 열람실 예약 좌석의 이용 상태를 시각적으로 표시하고, 생성형 AI를 활용해 좌석 이용 정보를 안내하는 스마트 좌석 시스템 |
| 선택 근거 Why | 대학생이 실제로 자주 경험할 수 있는 문제, 사용자 간 직접적인 갈등을 줄일 수 있음 |

## ② 성공 기준 가져오기 / Success criteria from Week 3

| 3주차 성공 기준 원문 Original (Week 3) | 모호한 표현 Vague words |
|---|---|
| *(예시) 학생들이 과제 제출 현황을 쉽게 확인할 수 있다* | *쉽게, 확인할 수 있다* |
| 예약 시간이 종료되면 기존 사용자가 이용 종료 사실을 즉시 인지하고 자리를 비워, 다음 예약자가 예약 시간부터 바로 좌석을 이용할 수 있는 상태 | 즉시 인지한다. |

## ③ Acceptance Criteria

최소 정상 경로 2개 + 실패 경로 1개. **판정 방법** 칸이 비면 아직 명세가 아닙니다.
At least two normal paths + one failure path. If "How to check" is empty, it is not yet a spec.

| # | 경로 Path | EARS 문장 Sentence | 판정 방법 How to check |
|---|---|---|---|
| *예시* | *정상* | *WHEN 학생이 과제 목록을 열면 THE 시스템은 SHALL 과목별 미제출 과제를 마감일 순으로 표시한다* | *미제출 과제 3건을 만든 뒤 목록을 열어 마감일 순으로 나오는지 확인* |
| AC-1 | 정상 Normal | WHEN 학생이 좌석을 예약하면  THE 시스템은  SHALL 예약된 좌석에 LED를 점등한다. | 좌석 예약을 해본 뒤 해당 좌석에 LED가 점등되는 지 확인 |
| AC-2 | 정상 Normal | WHEN 학생이 예약한 좌석의 시간이 끝나면  THE 시스템은  SHALL 예약된 좌석의 LED를 소등한다. | 좌석에 예약된 시간이 끝났을 때 LED가 소등되는 지 확인 |
| AC-3 | 실패 Failure | IF 예약 시간이 종료 후 5분 이상 사용자가 계속 좌석을 이용하고 있으면 THEN  THE 시스템은 SHALL 예약 종료 알림등을 점멸하여 좌석을 비워야 함을 알린다. | 5분 이상 사용자가 계속 좌석을 이용 시 예약 종료 알림등이 점멸되는지 확인 |
| AC-4 | 실패 Failure | IF 예약자가 1시간 이상 좌석을 사용하지 않으면  THEN  THE 시스템은 SHALL 예약 정책에 따라 해당 예약을 취소하고 좌석을 이용 가능 상태로 변경한다. | 관리자 페이지에서 자리 비움 경고 알림이 뜨는지 확인 |

> 확인할 동작이 더 있으면 AC-4부터 행을 추가해 쓰십시오.
> If there are more behaviors to check, add rows from AC-4.

- [x] 이번 활동에서 AI를 사용했다면 `PROMPTS.md`에 기록했습니다 / Logged any AI use in `PROMPTS.md`

---

> 수업 종료 시 커밋하세요 / Commit this at the end of class
> `git add docs/week-04.md && git commit -m "docs: 4주차 활동지 작성"`
