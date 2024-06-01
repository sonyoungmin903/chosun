
## 리눅스 명령어 조사
## top
### 1. 명령어 실행
# top 명령어 출력 예시

` $ top `

*  기본적으로 top 명령어를 입력하면 시스템의 현재 상태와 모든 실행 중인 프로세스들의 실시간 정보를 표시합니다.
---
### 2. 화면 구성
*Summary Information (상단):
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


   
