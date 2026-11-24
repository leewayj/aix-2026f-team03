# 12주차 활동지 / Week 12 Worksheet

**개발 착수 / Starting development**

- 작성일 / Date: 2026.11.18
- 참여자 / Present: 정윤지, 김은총, 박강민, 이진호

---

## ① 착수 점검표 / Start checklist

수업 시작 후 10분 안에 확인합니다. 체크되지 않은 항목이 있으면 그것부터 해결하고 개발을 시작합니다.
*Check within the first 10 minutes. Fix any unchecked item before you start coding.*

- [x] 초기 파일이 저장소에 올라와 있다 / Initial files are in the repository
- [x] 7주차 이슈가 GitHub에 등록되어 있고 담당자가 지정되어 있다 / Week 7 issues are on GitHub with owners
- [x] 팀원 모두 같은 환경에서 실행된다 / Everyone can run it in the same environment
- [x] 브랜치 규칙을 정했다 / Branch rule agreed — 

---

## ② 개발 일정 / Development schedule

5주차 **작업 순서**와 7주차 **이슈·마일스톤**을 바탕으로 이슈를 주차별로 배치합니다.
*Place your issues week by week, based on the Week 5 work order and Week 7 issues and milestones.*

- 11주차에 MVP가 동작해야 합니다. / Fill backwards from the deadlines.
- 선행 이슈가 끝나기 전에 뒤 이슈를 넣지 않습니다. / Never schedule an issue before the ones it depends on.
- 한 사람에게 몰리지 않았는지 확인합니다. / Check that no one is overloaded.

| 주차 Week | 수업 일정 Class | 끝낼 이슈 # Issues to close | 담당 Owner |
|---|---|---|---|
| 9주차 | 개발 착수(10/28~11/3) | 저장소 및 개발 환경 구성, 사용자 웹페이지 초기 구조, 예약 DB 설계, ESP32·LED 개발 준비, 관리자 페이지 초기 구조 | FE - 정윤지, 김은총, BE - 박강민, 이진호 |
| 10주차 | 막힘 진단 · 데모 시나리오 초안(11/4~11/10) | 예약 DB 및 API 구현, ESP32·LED 기본 제어, 관리자 예약 관리 기능 | FE - 정윤지, 김은총, BE - 박강민, 이진호 |
| 11주차 | **MVP 완료 · 중간 데모(11/11~11/17)** | 로드셀 착석 감지 및 전송, 좌석 상태 판별·LED 연동, 관리자 API 연동, 좌석 MVP 통합 및 시연 | FE - 정윤지, 김은총, BE - 박강민, 이진호 |
| 12주차 | 핵심 경로 테스트(11/18~11/24) | 핵심 시나리오 테스트, 웹 예외 처리, 센서·LED 안정성 검증, 통합 오류 수정 | FE - 정윤지, 김은총, BE - 박강민, 이진호 |
| 13주차 | **배포 · 실행 패키지(11/25~12/2)** | 실행 패키지 및 설치 문서, 발표자료·시연 영상, 최종 점검 및 제출 | FE - 정윤지, 김은총, BE - 박강민, 이진호 |

> 일정이 맞지 않으면 기능을 줄입니다. 뺀 기능은 5주차 Won't 목록에 옮깁니다.
> *If it doesn't fit, cut scope and move the feature to your Week 5 Won't list.*

---

## ③ 이번 주 목표 이슈 / This week's issues

| # | 제목 Title | 담당 Owner | 완료 Done |
|---|---|---|---|
| #1 | 사용자 화면에 예약 API 연결 및 예약 시간 표시 개선 | 박강민, 이진호 | 완료 |
| #2 | 관리자 예약 API 연결 및 좌석 상세에 센서·LED·장치 통신 상태 표시 | 정윤지, 김은총, 박강민 | 완료 |
| #3 | ESP32 착석 데이터 전송, 서버 LED 명령 수신 및 실기 연동 테스트 | 박강민, 이진호 | 완료 |
| #4 | 열람실 혼잡도 및 좌석 현황 조회 API 구현 | 정윤지 | 완료 |
| #5 | 사용자·관리자 화면 Vercel 배포 및 Render API 연동 | 정윤지 | 완료 |
| #6 | 관리자 예약 변경 시 사용자 좌석표와 ‘내 예약’ 자동 갱신 | 정윤지 | 완료 |
| #7 | 사용자 홈 혼잡도 카드를 착석 기준 집계 API에 연결 | 김은총 | 진행중 |

---

## ④ 오늘 진행한 것 / Progress today

- 사용자·관리자 페이지를 Vercel에 배포하고 두 페이지를 같은 Render API에 연결했다.
- 사용자 페이지에서 좌석을 예약하거나 반납하면 관리자 화면에 반영되는 것을 확인했다.
- 집중열람실 12번 좌석에 가상 예약을 등록해 사용자 좌석표와 ‘내 예약’이 새로고침 없이 갱신되는 것을 확인했다. 종료 시간을 15분 연장하자 ‘내 예약’의 종료 시각이 바뀌었고, 예약 삭제 후에는 좌석이 다시 ‘예약 가능’으로 표시됐다.
- 관리자 좌석 상세 화면에 LED·센서·장치 통신 상태를 표시하도록 수정했다. 제1열람실 1번 좌석의 테스트 화면에서 `비착석 → 착석 → 비착석` 변화를 확인했다. 배포 API를 기준으로 한 센서·LED 통합 시연은 후속 확인으로 남겼다.
- [x] 이번 활동에서 AI를 사용했다면 `PROMPTS.md`에 기록했습니다 / Logged any AI use in `PROMPTS.md`

---

> 수업 종료 시 커밋하세요 / Commit this at the end of class
> `git add docs/week-09.md && git commit -m "docs: 12주차 활동지 작성"`
