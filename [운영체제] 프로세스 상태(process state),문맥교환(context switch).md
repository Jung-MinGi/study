## 프로세스 상태
<img src="https://user-images.githubusercontent.com/118701129/245680028-9b4363ff-ba2b-4aab-981a-64555a3c3ab0.png" width="700"/>

***
프로세스 상태
* 준비(ready) - 프로세스가 cpu자원을 선점하기 위해 기다리는 상태
* 실행(running) - 프로세스가 cpu를 사용하고 있는 상태
* 봉쇄(blocked, wait, sleep) - cpu를 사용할 수 없는 상태(입출력 요청이 끝나야 ready상태로 바뀐다)
 * new와 terminated는 일시적인 상태이다

 ***
 ### 프로세스 상태 전이 
 * 예를 들어 ready큐에 프로세스B가 대기 중이고 프로세스A가 running일때 이때 타이머 인터럽트가 발생하면 프로세스A는 ready큐에 들어가게 되고 프로세스B가 실행상태로 변경된다
 * 만약 타이머 인터럽트가 아니라 I/O 시스템 호출할 경우 프로세스A는 봉쇄상태로 들어가고(이때는 cpu를 받어도 사용할 수 없는 상태) 입출력이 끝났다는 인터럽트가 발생하면 ready큐에 들어간다. (참고) 입출력이 끝났다는 인터럽트가 발생할 때 직전에 프로세스b는 해당 인터럽트와 상관이 없지만 프로세스b가 커널모드로 들어가게 된다 
***
## 문맥교환(context switch)

* 문맥교환(context switch)이란 프로세스로부터 다른 프로세스로 cpu제어권이 이양되는 과정
* 타이머 인터럽트가 발생하거나 프로세스가 입출력 시스템 콜을 할 때 발생한다
> 사용자 모드에서 커널모드로 들어가는 경우는 문맥교환X
* 프로세스A가 cpu를 이용중 타이머 인터럽트가 발생하면 cpu가 운영체제에게 넘어간다. 운영체제는 프로세스A의 문맥을 프로세스 제어블록(pcb)에 저장하고 다음 cpu를 사용할 프로세스에게 cpu제어권을 넘겨준다.
