# 오픈소스sw개론 과제_20212938_김범준
---

## 1) 리눅스 명령어 : top, ps, jobs, kill 명령어 조사하기

* **top** 

top은 CPU, Memory, Process와 같은 시스템의 상태를 전반적으로 빠르게 파악이 가능하다.

옵션 없이 입력하면 interval 간격으로 화면을 갱신하며 정보를 보여준다.

이 기능은 리눅스를 사용하는 디바이스의 성능이나 리눅스의 성능을 체크할 때 매우 유용하다.

* **ps** 

ps 명령어는 현재 실행중인 프로세스 목록과 상태를 보여준다

ps의 옵션은 전통적인 유닉스인 System V, BSD, GNU에 따라 다르게 나타나고 표기법에서도  차이를 보인다. 옵션 사용 시 System V 계열은 대시(dash, -)를 사용하고 BSD계열은 대시를 사용하지 않는다. GNU에서의 옵션 표기는 두 개의 대시(--)를 사용한다. 따라서 원하는 프로세스의 상태를 출력하려면 정확한 옵션 사용이 중요하다.

이 기능은 서버에 다수의 사용자가 접근해서 갑자기 느려졌을때 ps-ef 명령어를 이용해서 사용중인 프로세스를 체크하는 용도로 사용한다.

* **jobs**

jobs명령어는 백그라운드에 실행되고 있는 프로세스나 중지된 프로세스의 목록을 출력해준다.

jobs를 입력하고 결과를 보면 가장 첫 번째 열에 1,2,3,4 와 같은 숫자가 있는데 이숫자는 job 번호를 의미한다. 중지되거나 백그라운드에서 돌고 싶은 작업이 있을 때 이 job 번호를 이용해서 앞단으로 가져와 실행시킨다.

두번째 열에 보면 +,- 기호가 있는 프로세스들을 볼 수 있는데 +는 fg나 bg 명령어를 쳤을 때 디폴트로 가장 먼저 가져와서 수행하게 될 프로세스를 의미한다.(즉 현재 실행 중인 프로세스)
-는 현재 진행중인 job이 끝나면 바로 다음에 수행될 프로세스를 의미한다.

세 번째 열에 stopped같은 것은 job 상태를 의미한다. Stopped는 중지 또는 대기 상태의 프로세스, Running은 실행중인 상태의 프로세스, Done 수행이 완료된 프로세스를 의마한다.

* **kill**

kill명령어는 대개 프로세스를 죽일 때 사용한다. 하지만 내부적으로는 프로세스에 시그널을 보내 원하는 작업을 하게하는 명령어이다.

프로세스를 죽이려면 죽이려는 프로세스의 pid를 얻은 다음 kill 명령어의 인자로 넘기면 된다.

$ kill [pid]

위의 명령어와 같이 사용하면 된다.

---
## 1) vim 에디터에서 매크로 사용방법에 대하여 조사하기 (q , @)

매크로를 실행하는 방법은 명령모드에서 q[Name]을 입력한다.

예를 들어 qt,qg,qq이렇게 입력하면 아래에 기록중이라는 글을 볼 수 있다.

이렇게 하면 매크로가 실행되므로 어떻게 동작할 것인지 정해준다.

그 뒤 q를 다시 입력하면 아까 [Name]에 입력했던 이름의 매크로가 생성된다.

매크로를 실행시키는 방법은 @[Name]을 입력하면 [Name]의 이름을 가진 매크로가 실행된다.

여기서 @[Name] 앞에 [숫자]@[Name]을 하면 숫자에 들어간 만큼 매크로를 실행한다.
