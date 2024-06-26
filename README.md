
# 리눅스 명령어 조사
## top 명령어
### 1. 명령어 실행
#### top 명령어 출력 예시

` $ top `

* 기본적으로 top 명령어를 입력하면 시스템의 현재 상태와 모든 실행 중인 프로세스들의 실시간 정보를 표시합니다.
---
### 2. 화면 구성
* Summary Information (상단):
* 시스템의 요약 정보를 포함하며, 다음과 같은 항목들이 표시됩니다.
    * 시스템 시간: 현재 시간을 표시합니다.
    * 업타임: 시스템이 얼마나 오래 실행되고 있는지를 표시합니다.
    * 사용자 세션: 현재 로그인된 사용자 수를 표시합니다.
    * 로드 평균: 최근 1, 5, 15분 동안의 시스템 부하 평균을 표시합니다.
    * Tasks: 실행 중, 대기 중, 중지된, 좀비 프로세스의 수를 표시합니다.
    * CPU(s): CPU 사용량을 사용자(user), 시스템(system), 대기(idle) 등의 상태로 나누어 표시합니다.
    * 메모리: 전체 메모리, 사용 중인 메모리, 사용 가능한 메모리, 캐시된 메모리 등을 표시합니다.
    * 스왑: 전체 스왑 메모리, 사용 중인 스왑, 사용 가능한 스왑 등을 표시합니다.
* ask Information (하단):
* 각 프로세스에 대한 상세 정보를 제공합니다. 다음과 같은 항목들이 포함됩니다:
    * PID: 프로세스 ID.
    * USER: 프로세스를 실행한 사용자.
    * PR: 프로세스의 우선 순위.
    * NI: 프로세스의 니스 값(nice value).
    * VIRT: 프로세스가 사용하는 가상 메모리의 총량.
    * RES: 프로세스가 사용하는 실제 메모리의 총량.
    * SHR: 프로세스가 사용하는 공유 메모리의 총량.
    * S: 프로세스의 상태 (R - 실행 중, S - 대기, T - 중지, Z - 좀비).
    * %CPU: 프로세스가 사용하는 CPU의 비율.
    * %MEM: 프로세스가 사용하는 메모리의 비율.
    * TIME+: 프로세스가 시작된 후 경과한 총 CPU 시간.
    * COMMAND: 프로세스를 시작한 명령어.
 # 디테일 영역
 ![스크린샷 2024-06-02 오전 9 18 10](https://github.com/sonyoungmin903/chosun/assets/171433314/99273c1d-0e87-4608-bb47-ab64a6831539)
* PID
   * PID는 프로세스 ID이며 프로세스를 구분하기 위한 겹치지않는 고유한 값입니다.
* USER
   * 해당 프로세스를 실행한 USER 이름 또는 효과를 받는 USER의 이름입니다.
* PR & NI
   * PR : 커널에 의해서 스케줄링되는 우선순위입니다.
   * NI : PR에 영향을 주는 nice라는 값입니다.
* VIRT, RES, SHR, %MEM
   * 해당 필드들은 프로세스의 메모리와 관련있습니다.
   * VIRT : 프로세스가 소비하고 있는 총 메모리입니다. 프로그램이 실행중인 코드, heap, stack과 같은 메모리, IO buffer 메모리를 포함합니다.
   * RES : RAM에서 사용중인 메모리의 크기를 나타냅니다.
   * SHR : 다른 프로세스와의 공유메모리(Shared Memory)를 나타냅니다.
   * %MEM : RAM에서 RES가 차지하는 비율을 나타냅니다.
* S : 프로세스의 현재 상태를 나타냅니다.
* TIME+ : 프로세스가 사용한 토탈 CPU 시간
* COMMAND : 해당 프로세스를 실행한 커맨드를 나타냅니다.

---
## ps 명령어
### ps 명령어는 process State의 약자
### 현재 실행 중인 프로세스와 상태를 출력하는 명령어
* PS 명령어 출력 항목
   * USER (BSD):프로세스 소유자의 이름
   * PID:프로세스의 식별 번호
   * PPID:부모 프로셋의 PID
   * %CPU:CPU 사용 비율의 추정치 (BSD)
   * %MEM:Memory 사용 비율의 추정치(BSD)
   * VSZ:K 단위 또는 페이지 단위의 가상 메모리 사용량
   * RSS:실제 메모리 사용량
   * TTY:프로세스와 연결된 터미널
   * S (System V):현재 프로세스와 연결된 터미널
   * TIME:총 CPU 사용 시간
   * COMMAND:프로세스의 실행 명령행
   * STIME:프로세스가 시작된 시간 혹은 날짜
   * C (System V):짦은 기간 동안의 CPU 사용률
   * F:플래그
   * PRI:실제 실행 우선순위
   * NI:nice 우선순위 번호
* ps 명령어 옵션
   * -A 모든 프로세스를 출력
   * a(BSD) 터미널과 연관된 프로세스를 출력, x 옵션과 같이 모든 프로세스를 출력할 때 사용
   * -a 세션 리더를 제외하고 데몬 프로세스처럼 터미널에 종속되지 않은 모든 프로세스를 출력
   * -e 커널 프로세스를 제외한 모든 프로세스를 출력
   * -f 출력을 풀 포맷으로 표기(유닉스 스타일 UID, PID, PPID 등이 함께 표시
   * -l (System V) 출력을 긴 포맷으로 표기
   * -o 출력 포맷을 지정
   * -M 64비트 프로세스들을 출력
   * -m 프로세스뿐만 아니라 커널 스래드도 출력
   * -p 특정 PID를 지정하여 출력
   * -r 현재 실행중인 프로세스 출력
   * u(BSD) 프로세스의 소유자를 기준으로 출력
   * -u [사용자] 특정 사용자의 프로세스 정보를 출력, 사용자를 지정하지 않는다면 현재 사용자 기준으로 출력
   * x(BSD) 데몬 프로세스처럼 터미널에 종속되지 않은 프로세스를 출력
   *  -x 로그인 상태에 있는 동안 아직 완료되지 않은 프로세스를 출력.
 
---
## jobs 명령어
### jobs 명령어는 작업의 상태를 표시하는 명령어
### 현재 쉘 세션에서 실행시킨 백그라운드 작업의 목록이 출력되며, 각 작업에는 번호가 붙어 있어 kill명령어 뒤에 '%번호' 등으로 사용할 수 있다. 
` jobs [옵션][작업번호] ` 


jobs 명령어는 현재 쉘 프로세스의 자식 백드라운드 프로세스들을 보여줌
```
    [15:51:12 oss]$ jobs
    [1]   Stopped      vi
    [2]-  Stopped      vi
    [2]+  Stopped      vi
```
jobs로 출력되는 백그라운드 작업의 상태값


<img width="511" alt="스크린샷 2024-06-02 오후 3 57 00" src="https://github.com/sonyoungmin903/chosun/assets/171433314/ad20a14a-eb5a-4577-869c-68280f04f793">


### 옵션


<img width="512" alt="스크린샷 2024-06-02 오후 3 57 17" src="https://github.com/sonyoungmin903/chosun/assets/171433314/bf47c4db-df47-47d8-960e-ca7e89d8df93">


---
## `kill` 명령어의 주요 기능
### 1. 기본 사용법
kill <PID>
<PID>: 종료할 프로세스의 ID를 지정합니다.
기본적으로 kill 명령어는 SIGTERM (신호 번호 15) 신호를 보냅니다.
### 2. 옵션
* -l: 신호 목록을 출력합니다.

`kill -l`
     
      
   * 사용할 수 있는 신호의 목록과 번호를 표시합니다.

     
      
* -s <SIGNAL> 또는 --signal <SIGNAL>: 보낼 신호를 지정합니다.

`kill -s SIGKILL <PID>`


* -9: SIGKILL 신호를 보내 강제 종료합니다.

`kill -9 <PID>`


* -15: SIGTERM 신호를 보내 정상 종료합니다. (기본값)

`kill -15 <PID>`
### 3. 신호
* SIGTERM (15): 프로세스를 정상적으로 종료합니다. 프로세스가 종료를 처리할 수 있는 기회를 제공합니다.
* SIGKILL (9): 프로세스를 즉시 강제 종료합니다. 프로세스가 종료를 처리할 기회를 가지지 못합니다.
* SIGSTOP (19): 프로세스를 일시 중지합니다.
* SIGCONT (18): 일시 중지된 프로세스를 다시 실행합니다.

### 4. 요약
기본 사용법: kill <PID>는 프로세스를 종료하는 기본 방법입니다.
옵션: -l, -s <SIGNAL>, -9, -15 등 다양한 옵션을 통해 특정 신호를 지정할 수 있습니다.
신호: SIGTERM, SIGKILL, SIGSTOP, SIGCONT 등 다양한 신호를 통해 프로세스를 제어할 수 있습니다.
이 명령어는 시스템 관리자나 개발자가 특정 프로세스를 제어하고 관리하는 데 매우 유용합니다. 프로세스를 안전하게 종료하거나 필요에 따라 강제 종료할 수 있어, 시스템의 안정성과 효율성을 유지하는 데 중요한 역할을 합니다.
