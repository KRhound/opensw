# 오픈소스SW개론 과제
![연습용 이미지]https://github.com/KRhound/opensw/blob/main/free-icon-terminal-7997977.png
## 과제 내용
- 리눅스 명령어 중에서 top, ps, jobs, kill 명령어에 대해서 조사해보자!
- 조사한 내용을 자신의 github 페이지에 README 파일로 정리함
- 마감기한 : 2024년 6월 2일 (일), 자정까지
- 과제 점수는 5점이며, 지각제출은 불허입니다.
- 다양한 Markdown 기능을 활용해보자! (이미지, 테이블, 불렛 등)
- 제출할 때는 github 페이지 링크와 pdf 파일을 같이 제시함
  * github 페이지의 내용을 pdf 파일로 인쇄하여 같이 반드시 첨부
  * 마감기한 이후에 수정하는 것을 방지하기 위한...
  * pdf 파일을 제시하지 않을 경우에는 과제 제출로 인정 안됨!!!
  * 정확한 링크 주소를 제대로 안보낼 경우에는 감점 처리함
  * 과제 제출 이후에는 commit과 push를 절대 수행하지 말 것
# 명령어 조사
 ## 1. top
현재 OS의 상태를 어플리케이션 입니다. Memory 사용량, CPU 사용량 등을 확인할 수 있습니다. 옵션 없이 top을 실행하면 실행하는 동안 일정한 interval 간격 (기본3초)으로 실시간에 근접 내용을 확인할 수 있으며. 리눅스에서 top 명령어를 실행하면 아래와 깉은 화면이 모니터에 출력됩니다.
### 명령어 옵션

| 옵션 | 설명 |
|----|--------|
|-a | 메모리 사용에 따라 정렬|
|-b | 배치 모드에서 시작|
|-c | 명령어 대신 명령어 라인을 보여줌|
|-d | 업데이트 간격을 조정|
|-h | 도움말|
|-H | 모든 개별 쓰레드가 보여짐|
|-i | 좀비(zombie) 또는 Idle 상태의 것들은 무시됨|
|-m | VIRT 대신 USED를 보고|
|-M | 메모리 유닛(K/M/G)을 보여줌|
|-n | 반복의 최대 수를 지정|
|-P | 지정된 프로세스 ID들만 보여줌|
|-s | 보안 모드로 시작|
|-S | 누적 시간 모드로 시작. 활성화되면 각 프로세스는 CPU를 사용한 시간과 함께 출력|
|-u | 지정된 유효 사용자에 의한 프로세스만 보여줌|
|-U | 지정된 사용자에 의한 프로세스만 보여줌. 사용자는 실제, 유효한, 저장된 및 파일시스템 UID를 의미|
|-v | 프로그램 라이브러리 버전을 출력|

### 실행 중 명령어
```
스페이스바 누름 : 화면 갱신
k : kill 명령 
r : nice 값 변경
    nice는 우선순위를 뜻하며, -20 ~ 20 까지 사용가능. 낮을수록 우선권이 높음. 기본값은 0
Z : 화면 출력 색상 변경
    a 또는 w를 누르면 색상이 순차적으로 변경되며 보여줌
z : Z로 변경된 출력 색상과 기본 출력 색상간 전환
B : 글자 두껍게
l : top 출력 상단의 load avg 항목 on/off
t : top 출력 상단의 프로세스와 cpu 항목 on/off
m : top 출력 상단의 메모리 항목 on/off
O : 화면 정렬(sort) 기준 지정
r : nice 조정 (-20 ~ 20. 우선순위 높음 ~ 낮음)
q : top 종료
```
## 2. ps
단순히 ps 명령어는 프로세스의 현재 상태를 출력하는 명령어이다. 하지만 수많은 옵션과 필드를 통해 프로세스에 대한 다양한 작업이 가능하다. ps만 입력하면 프로세스 목록이 나오는데, PID는 프로세스의 ID, PPID는 부모 프로세스를 의미한다.
### 명령어 옵션
```
-e : 현재 실행 중인 모든 프로세스 정보 출력
-f : 모든 정보 확인
-a : 실행 중인 전체 사용자의 모든 프로세스 출력
-u : 프로세스를 실행한 사용자와 프로세스 시작 시간 등을 출력
-x : 터미널 제어 없이 프로세스 현황 보기
```
## 3. jobs
명령어는 현재 돌아가고 있는 백그라운드 프로세스 리스트를 모두 출력해준다.
### 실행 후 표시 사항
```
+는 스택의 가장 위에 있다는 뜻이고
-는 바로 그다음 밑에 있다는 뜻이다.
```
## 4. kill
다른 프로세스를 중지시키는 명령어입니다.
### 명령어 옵션
```
-9 : SIGKILL 시그널을 보내며, 프로세스를 즉시 강제 종료합니다.
-15 : SIGTERM 시그널을 보내며, 프로세스에게 정상적인 종료를 요청합니다.
-s : 보낼 시그널을 지정합니다. 기본적으로 SIGTERM 시그널이 사용됩니다.
-l : 사용 가능한 시그널 목록을 보여줍니다.
-u : 프로세스의 유저 ID를 지정합니다.
-c : 프로세스의 이름을 지정합니다.
```
