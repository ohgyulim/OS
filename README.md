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
 
* Interrupt의 두 가지 방식
  - Polling : CPU가 하드웨어의 변화를 지속적으로 읽어 들이며 이벤트의 수행 여부를 주기적으로 검사하여 해당 신호를 받았을때 이벤트를 실행시키는 방식 (오버헤드가 큼)
  - Hardware interrupt : 하드웨어의 변화를 감지하여 외부로부터의 입력을 CPU가 알아채는 방법
 
* I/O device에서 interrupt 발생했을 때, 과정
  - CPU는 현재 작업을 중단하고, 커널모드로 들어가고, 현재 PC값을 저장한다.
  - interrupt가 발생한 핸들러로 점프하여 그곳에 있는 코드들을 수행한다.
  - 저장한 PC로 다시 돌아와서 진행중이었던 작업을 이어서 한다.

* Hardware Protection (하드웨어 독점을 막아줌)
  - I/O Protection : 어떤 프로그램이 I/O 장치를 망가뜨리거나 여러 사용자가 공유하고 있는 I/O장치 독점 방지
  - Memory Protection : 운영체제에서 실행하고 있는 프로세스가 실행에 할당되지 않은 메모리에 접근하는 것을 막음 -> 프로세스 내에 버그가 다른 프로세스의 동작에 영향을 끼치는 것을 예방, 악성 소프트웨어가 시스템에서 허가되지 않은 접근권한을 갖고 시스템에 영향을 끼치는 것을 막음
  - CPU Protection : 한 개의 프로그램이 CPU를 독점하고 계속 사용하는 것을 막음.

* Dual-Mode Operation (운영체제를 보호하기 위해 만들어짐)
  - 역할 :  예상치 못한 에러나 이벤트 요청이 왔을 때 운영체제를 보호해주는 역할
  - 핵심 : privileged instruction(I/O장치를 조종할 수 있는 명령어)는 monitor mode(kernel mode)에서만 사용할 수 있음.
  - User mode
    + user application이 실행되는 mode
    + system data 및 memory에 제한된 접근
    + system call을 통해 kernel mode로 전환 가능
  - Monitor mode( = kernel mode or system mode)
    + OS가 실행될 때의 mode
    + 모든 내부 system data 및 memory에 접근 가능
    + 모든 CPU 명령에 대한 실행 가능
    + 보안 / 자원관리 / 추상화 같은 역할
    + -> 사용자 모드에서 I/O장치에 대한 요청이 올때 kernel mode에 interrupt를 주고, 이것을 운영체제가 해결하고 나면, 다시 사용자 모드로 돌아옴.

* History of computer systems
  - batch system
  - multiprogramming systems : 메모리에 여러개 프로세스
  - time-sharing systems : 하나의 컴퓨터를 여러사람이 사용 (한 사람이 프로그램 사용할 때 멈추는 것을 보완하기위해)
  - desktop systems
  - parallel(하나의 컴퓨터 여러 CPU) / distributed(네트워크로 연결) / clustered(여러개 PC 네트워크로 연결. storage공유) / cloud systems
  - real-time(제한시간내 수행) / embedded(자판기, 리모콘 등 운영체제 필요x시스템) / handheld systems(스마트폰 시스템)

### 2. 
..
..
..



  

