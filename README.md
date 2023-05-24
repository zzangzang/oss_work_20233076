# 리눅스 명령어
# 1 .top
### 1-1. top 명령어란?
> 실시간으로 CPU 사용률을 체크해주는 유틸리티로, 작업관리자와 비슷한 성격을 가지고 있다. top 명령어를 사용하여 CPU, 메모리, 디스크, 네트워크 등의 시스템 성능 지표와 실행 중인 프로세스 목록을 볼 수 있다. 
### 1-2. 사용 구문
> `top[옵션]`    
> *~~옵션 없이 명령어를 실행하면 interval 간격(기본 3초)으로 화면을 갱신하며 정보를 보여줌.~~*
### 1-3. 사용 예시
* **실행결과**
> ![top 실행결과](https://postfiles.pstatic.net/MjAyMjAxMzFfMjAx/MDAxNjQzNjA4MzIxMjk0.g0Mi1bBv0QNNVYycebt8sFDgOi2SnwYIy-0el8mzNdQg.REMOZJ03m8Vopg4sJvL_1iCcGIhgBafDiutsda0k9hcg.PNG.dktmrorl/SE-bd5ab58f-19da-4c51-8095-49ad750f129f.png?type=w773)    
>`top -b`    
>순간의 정보를 확인하려면 -b 옵션 추가(batch 모드)    
>`top -n`     
>-n 옵션을 사용하여 top 실행 주기 설정(반복 횟수)        

* **top 실행 후 명령어**

|명령어|설명|
|:--|:--|
|h|도움말 표시|
|k|프로세스 강제 종료|
|q|top 명령어 종료|
|r|우선순위 변경|
|s|프로세스 간격 변경|
|f|표시할 항목 선택|
|u|특정 사용자의 프로세스만 보기|
|M|메모리 사용률 순으로 정렬|
|P|CPU 사용률 순으로 정렬|
|T|실행 시간 순으로 정렬|
|a|메모리 사용량에 따라 정렬|
|1|CPU Core별로 사용량 보여줌|
# 2. ps 
### 2-1. **ps 명령어란?**
>  ps는 'process status'의 약자로, 현재 실행중인 프로세스 목록을 확인할 수 있는 유틸리티이다. CPU, 메모리, 실행 시간 등의 정보를 제공한다.
### 2-2. 사용 구문
> `ps[옵션]`
### 2-3. 사용 예시
* **실행결과**
> ![ps 실행결과](https://postfiles.pstatic.net/MjAyMTA2MjNfOTcg/MDAxNjI0Mzc4NDAzNzk4.MwsSfnvkig8gCoFAeVdoxjoRAzVYdm6AITk5NNXF4WYg.hPEi8h1DMPJOzbRqb8Z9GxrFPydq_xXuVa9PSy2OBG8g.PNG.ycpiglet/image.png?type=w773)    
> 
> *TTY는 프로세스가 실행된 터미널 번호를 의미    
> TIME은 프로세스가 사용한 컴퓨터 시간(분초)을 의미   
> CMD는 프로세스의 이름을 의미*

**ps 실행 후 명령어**
* *pid, cmd 등 프로세스의 기본적인 내용만 출력*
> `ps`

* *모든 프로세스를 출력*
> `ps -e`

* *풀 포맷으로 출력 (uid, pid, ppid, TTY 등 정보를 보여줌)*
> `ps -f`

* *긴 포맷으로 출력 (풀 포맷 + F, S, PRI 등 정보를 더 보여줌)*
> `ps -l`

* *프로세스 번호가 1인 프로세스를 출력*
> `ps -p 1`

* *계정이 seek인 프로세스들을 출력*
> `ps -u seek`

* *모든 프로세스를 풀 포맷으로 출력, more 명령어를 이용하여 페이지 단위로 출력*
> `ps -ef | more`

* *모든 프로세스를 풀 포맷으로 출력한 목록에서 grep을 이용해 seek이 포함된 행(Row)을 출력*
> `ps -ef | grep seek`


<hr/>

## ***ps와 top의 차이점***    
> *ps는 ps한 시점에 proc에서 검색한 cpu 사용량*    
> *top은 proc에서 일정 주기로 합산해 cpu 사용율 출력*

<hr/>

# 3. jobs
### 3-1. jobs 명령어란?
> 리눅스 쉘에서 현재 실행 중인 작업(프로세스)의 목록을 보여주는 명령어이다. 주로 쉘에서 백그라운드(background)로 실행한 작업들(진행 중인 작업 상태, 변경 되었지만 보고되지 않은 상태 등)을 확인하고 관리하는 데 사용된다.
### 3-2. 사용 구문
> `jobs [옵션] [job ID]`     
>  `jobs -x command [args]`
### 3-3. 사용 예시
* **jobs 실행 후 명령어**

|옵션|설명|
|:--|:--|
|-l|프로세스 그룹 ID를 state 필드 앞에 출력|
|-n|프로세스 그룹 중에 대표 프로세스 ID를 출력|
|-p|각 프로세스 ID에 대해 한 행씩 출력|
|command|지정한 명령어를 실행|

* **jobs로 알 수 있는 세션의 상태 값**

|상태|설명|
|:--|:--|
|Running|작업이 일시 중단되지 않았고 종료하지 않고 계속 진행 중임|
|Done|작업이 완료되어 0을 반환하고 종료 했음을 의미|
|Done(code)|작업이 정삭적으로 완료되었으며, 0이 아닌 코드를 반환 했음을 의미|
|Stopped|작업이 일시 중단|
|Stopped(SIGTSTP)|SIGTSTP 신호가 작업을 일시 중단|
|Stopped(SIGSTOP)|SIGSTOP 신호가 작업을 일시 중단|
|Stopped(SIGTTIN)|SIGTTIN 신호가 작업을 일시 중단|
|Stopped(SIGTTOU)|SIGTTOU 신호가 작업을 일시 중단|

# 4. kill
### 4-1. kill 명령어란?
> kill 명령어는 실행 중인 프로세스를 종료하는 데 사용되는 유틸리티이다. kill은 프로세스에 시그널을 보내 원하는 작업을 하게 하는 명령어이다.
### 4-2. 사용 구문
> ```kill [옵션] [pid]``` 
>           
      예를 들어 실행중인 특정 프로세스를 죽이고 싶다면 ps 명령어를 통해 해당 프로세스의 pid를 얻고 kill 명령어의 파라미터로 넘겨 실행하면 프로세스를 종료시킬 수 있습니다.
### 4-3. 사용 예시
* *pid가 '12345'인 프로세스를 종료*
> `kill 12345`

* *'SIGTERM' 시그널을 보내어 프로세스를 정상 종료*
> `kill -s SIGTERM <PID>`

* *pid가 '12345'인 프로세스를 강제 종료*
> `kill -9 12345`    
> `kill -SIGKILL 12345`

* *<PID1> <PID2> <PID3>와 같이 여러 개의 프로세스 종료*
> `kill <PID1> <PID2> <PID3>`

* *그룹 ID를 지정하여 특정 그룹의 모든 프로세스 종료*
> `kill -g <그룹 ID>`

* *모든 프로세스 종료*
> `kill -9 -1`

* *kill 명령어에서 지원하는 시그널(Signal) 목록을 출력*
> `kill -l`
