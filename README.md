# OS

### 1.  OS
* 운영체제(OS) : 모든 컴퓨터에 필수적인 요소이며, 하드웨어를 사용해서 사용자가 원하는 프로그램(프로세스)를 실행시켜주는 역할을 함.

* 운영체제의 역할 : 컴퓨터 하드웨어를 효율적으로 관리하여 사용자가 프로그램을 편리하게 수행할 수 있는 환경을 제공 
  - 자원을 관리하고 할당함 (자원 할당자)
    + abstraction(추상화)
    + sharing
    + protection : 허가받지 않은 사용자가 특정작업에 들어올 수 없도록 함.
      + (1) I/O protection : Dual-mode operation
      + (2) Memory protection : MMU
      + (3) CPU protection : Timer interrupt
    + fairness : 운영체제가 자원을 사용할 때 어떤 프로세스가 특정자원을 점유해서 사용하는 것을 막아줌
    + performance : OS는 최고성능을 우선시해서 자원을 관리함.
  - 유저 프로그램의 실행과 I/O 장치들의 동작을 컨트롤함.
  - kernel (운영체제는 kernel + system program)
  

* 컴퓨터 시스템의 구성요소
  - 하드웨어
  - 운영체제
  - 운영프로그램
  - 사용자

* OS 시스템 구성요소
  - 유저모드 : shell
  - 커널모드 : File system management, I/O management, Memory management, Process management, Protection, Hardware Control

* Storage
  - Register (CPU 내부에 존재)
  - SRAM(Cache)
  - DRAM
  - SSD (Secondary Storage)
  - 하드디스크 (Secondary Storage)

* Interrupt (비동기식 인터럽트 / 외부 인터럽트)
: CPU가 프로그램을 실행하고 있을 때, 입출력 하드웨어 등의 장치에 예외상황이 발생하여 처리가 필요할 경우에 CPU에게 알려 처리할 수 있도록 하는 것 (예측 불가하게 이벤트 발생)

* Exception (동기식 인터럽트 / 내부 인터럽트)
: CPU가 자기자신에게 인터럽트를 거는 경우, CPU가 자신이 처리하지 못하는 일이 왔을 때, OS에게 도움을 요청하고 자기자신에게 인터럽트 검. Trap과 Fault가 있음.
  - Trap : 의도적으로 발생시키는 exception (ex. Debug, System call)
  - fault : 의도적으로 발생시키는 것 x, 예외적인 상황에서 예상치 못하게 발생해서 실행중인 명령어를 다 마치지 못한 상황이 오면 fault handler를 사용해서 kernel모드로 접근하는 방식 (ex. 0으로 나누기)



  

