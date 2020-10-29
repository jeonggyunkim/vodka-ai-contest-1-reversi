# 보드카 배 리버시 AI 대회
## 대회 개요
DGIST의 구성원이라면 누구나 참가할 수 있는 게임 AI 대회입니다.

### 리버시에 대해서
Renegade, 리버시, 뒤집기 등 여러 이름으로 불리는 게임입니다.

1. 무조건 검은색 플레이어부터 시작합니다.
2. 각 플레이어는 번갈아 가면서 수를 둡니다.
3. 각 플레이어는 최소 1개의 말을 뒤집을 수 있는 곳이 있다면 무조건 말을 둬야 합니다.
4. 놓여진 말과 상하, 좌우, 대각선 8방향 안에 놓여진 첫 번째 자신의 말 사이에 있는 상대방의 말을 자신의 말로 뒤집습니다. 사이에 빈 공간이 있을 경우, 뒤집지 않습니다.
5. 만일 수를 둘 수 없는 경우, 차례는 무시됩니다.
6. 양 플레이어가 모두 말을 둘 수 없거나, 판이 가득 차면 게임은 종료됩니다.


## 대회 상금
대회 상금은 다음과 같습니다.
우승 | 50,000 상당
--- | ---
준우승 | 30,000 상당
참가상 | 10,000 상당 
* 참가자 수가 너무 많을 경우, 참가상은 변경될 수 있습니다.

## 대회 일정
대회 일정은 다음과 같습니다.
| 일시 | 내용 | 비고 |
| --- | --- | --- |
| 2020/11/14 | 참가자 모집 마감 | Github / 메일 |
| 2020/11/20 | 대회 내용 중계 | 유튜브 라이브 스트리밍 예정 |

## 대회 방식
대회는 최소 5명 이상의 참가자가 발생할 경우 시작됩니다.

대회는 리그전으로 시행되며, 각 유저는 다른 각각의 유저와 검정 시작 10번, 하양 시작 10번 총 20번의 경기를 치뤄, `([총 참가자 수] - 1) * 100` 개의 경기를 치릅니다.

이기면 10점, 비기면 5점으로 취급하며, 최종 점수가 가장 높은 사람이 최종 우승자가 됩니다.

실행 시간이 점수에 반경됩니다. 각 게임마다 자기 차례의 실행 시간을 모두 더해서 3초까지는 감점이 없으며, 그 뒤로는 1초당 1점씩 최대 5점 감점됩니다.

또한, 만일 Agent에서 유효하지 않은 행동을 시도할 경우, 각 시도당 1점씩 감점되며 해당 턴은 스킵됩니다. 최대 5점 감점됩니다.

아래는 예시입니다.

| 승패 | 총 실행시간 | 실수 | 얻는 점수 |
| --- | --- | --- | --- | --- |
| 승 | 1.5 | 0 | 10 |
| 승 | 5.2 | 2 | 10 - 2.2 - 2 = 5.8 |
| 패 | 2.7 | 1 | 0 - 1 = -1 |
| 무 | 4.1 | 0 | 5 - 1.1 = 3.9 |

실행 시간은 중계를 진행하는 컴퓨터가 기준이며, 아래 `PerformanceAnalysis.py` 파일을 실행한 결과는 다음과 같습니다.

## 제출 방식
* 본 Github Repository에 파일을 추가해 Pull Request를 보내시거나 메일()로 AI 코드를 보내주세요. 
* AI Agent를 제출했을 경우에는, 메일에 다음과 같은 내용을 담아서 보내주시기 바랍니다.
  * (Github으로 제출했을 경우) Github 계정명
  * 본명
  * DGIST 내 소속과 학번
  * 연락처 (상품을 받거나 기타 연락용, 핸드폰 번호나 이메일을 추천합니다.)
* Pull Request는 위 메일이 확인되면 Merge 됩니다.
* 미리 보낼 경우, 작동 테스트가 가능하니 이를 추천합니다.
* 본 대회를 위해 수집된 개인정보(본명, 연락처, 소속, 학번)은 본 대회의 운영을 원활히 하기 위한 목적과 대회 종료후 동아리 활동 내역 보관 목적으로서 저장되며, 다른 용도로 사용되지 않습니다.
* 제출한 AI Agent 코드는 본 퍼블릭 레포지토리에 공개됩니다.

## AI Agent 관련 제한 사항
* Pytorch, Tensorflow 등의 프레임워크는 자유롭게 사용 가능합니다.
* 위에서도 언급이 되었지만, 실행 시간이 오래 걸리게 될 경우에는 그에 따른 감점이 있으므로, 

## 대회 규칙
* 게임 시스템 자체에 대한 공격은 어떠한 이유던지 간에 즉시 실격으로 처리됩니다.

# 본 프로젝트에 대해서
## Dependencies

* python 3.9.0 >=
  * 낮은 버전도 Python 3이면 상관 없을 거 같습니다.
* pygame 2.0.0 >=
* numpy 1.19.3 >=

본 프로젝트는 다음과 같은 파일을 포함하고 있습니다.

## RenegadeGame.py
메인 게임 코드가 들어가 있는 파일입니다. AI 작성을 위한 다양한 보조 함수들을 제공하고 있으며, 각각의 내용이나 사용처는 Github 위키 페이지를 참조해 주세요. 본 파일은 수정해서는 안 됩니다.

## GUI.py
게임을 GUI로 실제로 확인할 수 있습니다. 실제로 자신이 만든 AI나, 미리 작성된 예시 AI와도 플레이 할 수 있습니다. 파일을 확인하고, 적당한 자리에 AI를 포함시켜 주세요. 자세한 가이드는 역시 Github 위키 페이지에 첨부되어 있습니다.

## GUIContest.py
모든 AI 작성이 완료된 뒤, 여기에 코드를 포함시켜 서로간 경쟁을 하게 됩니다. 코드 첨부는 운영진 측에서 할 예정이니, 본 파일을 수정하지 마십시오.

## PerformaceAnalyze.py
성능을 상대적으로 측정하기 위한 코드로서, 단순한 반복문을 담고 있습니다.

이 파일을 중계용 컴퓨터에서 실행한 결과를 위에 첨부합니다.