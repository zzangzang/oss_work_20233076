# 리눅스 명령어
## **1 .top** 
### 1-1. top 명령어란?
> 실시간으로 CPU 사용률을 체크해주는 유틸리티로, 작업관리자와 비슷한 성격을 가지고 있다. top 명령어를 사용하여 CPU, 메모리, 디스크, 네트워크 등의 시스템 성능 지표와 실행 중인 프로세스 목록을 볼 수 있다. 
### 1-2. 사용 구문
> ```top[옵션]```
### 1-3. 사용 예시
* **실행결과**
> ![top 실행결과](https://postfiles.pstatic.net/MjAyMjAxMzFfMjAx/MDAxNjQzNjA4MzIxMjk0.g0Mi1bBv0QNNVYycebt8sFDgOi2SnwYIy-0el8mzNdQg.REMOZJ03m8Vopg4sJvL_1iCcGIhgBafDiutsda0k9hcg.PNG.dktmrorl/SE-bd5ab58f-19da-4c51-8095-49ad750f129f.png?type=w773)
* **top 실행 후 명령어**

|명령어|설명|
|:--:|:--:|
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
## 2. ps 
### 2-1. **ps 명령어란?**
>  ps는 'process status'의 약자로, 현재 실행중인 프로세스 목록을 확인할 수 있는 유틸리티이다. CPU, 메모리, 실행 시간 등의 정보를 제공한다.
### 2-2. 사용 구문
> ```ps[옵션]```
### 2-3. 사용 예시
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

## **3. jobs**
## **4. kill**
### 4-1. kill 명령어란?
> kill 명령어는 실행 중인 프로세스를 종료하는 데 사용되는 유틸리티이다. kill은 프로세스에 시그널을 보내 원하는 작업을 하게 하는 명령어이다.
### 4-2. 사용 구문
> ```kill [옵션] [pid]```
### 4-3. 사용 예시
* **실행결과**
> ![top 실행결과](https://postfiles.pstatic.net/MjAyMjAxMzFfMjAx/MDAxNjQzNjA4MzIxMjk0.g0Mi1bBv0QNNVYycebt8sFDgOi2SnwYIy-0el8mzNdQg.REMOZJ03m8Vopg4sJvL_1iCcGIhgBafDiutsda0k9hcg.PNG.dktmrorl/SE-bd5ab58f-19da-4c51-8095-49ad750f129f.png?type=w773)
* **top 실행 후 명령어**

|명령어|설명|
|:--:|:--:|
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

