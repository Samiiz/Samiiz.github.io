---
layout: post
title: Hardware_Structure
subtitle:
author: Samiiz
categories: [OS]
banner:
  image: "posting_images/OS/OS.jpeg"
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
  subheading_style: "color: gold"
tags: [CPU]
---

## hardware_structure

시작하기 전에 프로그램의 실행 과정을 먼저 이해하고 넘어가자.

프로그램의 실행 과정은 크게 세 가지로 나뉜다.

우리가 프로그래밍 언어로 코드를 짜고 컴파일하면,  
컴파일러에 의해 기계 친화적인 어셈블리 코드로 변환된다.  
또한 여기서 다시 한 번 컴파일러를 거쳐 바이너리 코드로 변경되어 실행된다.

실행 파일을 실행하면 메인 메모리에 순차적으로 명령어가 저장되고,  
또한 차례대로 CPU로 이동된 후 명령어들이 실행된다.

여기서 명령어를 실행할 때  
Fetch -> 레지스터를 이용해 명령어를 저장하고,  
Decode -> CU를 통해 명령어를 해석하고,  
Execution -> 해석된 명령어를 토대로 ALU가 명령어에 대한 연산을 한다.

### CPU

<img src="https://github.com/Samiiz/Samiiz.github.io/blob/master/posting_images/OS/hardware_structure.gif?raw=true">

#### 1. ALU (Arithmetic and Logical Unit)

CU에게 전달받은 바이너리 코드를 기준으로,  
기본적인 연산을 담당하며,  
산술 연산과 논리 연산을 수행한다.

ALU는 산술 논리 연산 장치라고도 한다.

#### 2. CU (Control Unit)

레지스터를 통해 명령어가 전달되면 명령어를 해석한다.  
해석된 결과를 ALU에게 전달한다.

CU는 명령 해석 장치라고도 한다.

#### 3. Register Set

ALU가 연산 중일 때 다음 작업을 임시로 저장한다.

주요 레지스터

- 프로그램 카운터 (Program Counter)
  - 메모리에 실행될 다음 명령의 주소를 저장
- 인스트럭션 레지스터 (Instruction Register)
  - 이제 해석해야 하는 명령어를 저장
- 어드레스 레지스터 (Address Register)
  - 메모리의 주소를 저장
- 버퍼 레지스터 (Buffer Register)
  - 읽거나 쓰려는 명령어를 저장
- 플래그 레지스터 (Flag Register)
  - 연산 결과나 CPU 상태의 부가 정보 저장
- 스택 포인터 (Stack Pointer)
  - 스택에 마지막으로 저장한 값의 위치를 저장

Register는 임시 저장 장치라고도 한다.

### Main Memory

메모리는 CPU가 연산을 하거나 명령을 실행하는 데 필요한 정보를 저장하는 공간을 말한다.

그 중 메인 메모리는 RAM과 ROM 같은 휘발성 및 비휘발성 메모리이며,  
CPU가 데이터 버스를 통해 엑세스할 수 있다.

속도는 빠르지만 전원이 꺼지면 데이터가 지워지기 때문에,  
현재 실행 중인 프로그램 또는 처리 중인 데이터에 대한 결과를 저장하고,  
보조 메모리로부터 일정 데이터를 받아 저장하여,  
CPU가 필요로 할 때 바로 정보를 전달한다.

#### Main Memory와 Auxiliary Memory의 차이

- Main Memory
  - 데이터 버스를 통해 액세스 가능
  - 휘발성 및 비휘발성 메모리이다.
  - ROM, RAM이 그에 해당한다.
- Auxiliary Memory
  - 프로세스에 바로 접속 불가능 기본 메모리로 복사되고, 입출력 채널을 통해 액세스 가능
  - 항상 비휘발성 메모리이다.
  - HDD, SSD 등이 그에 해당한다.

### Bus System

데이터를 이동하는 데 사용되는 전송 경로이다.

구성 요소로는  
데이터 버스: 데이터 이동을 위해 필요한 버스(경로)  
컨트롤 버스: CPU가 원하는 바를 메모리에 전달하기 위한 버스(경로)  
어드레스 버스: 주소값을 이동하기 위해 필요한 버스(경로)

### Interrupt

인터럽트란 CPU가 작업을 수행하고 있을 때 작업을 방해하는 신호를 말한다.  
인터럽트는 크게 두 가지로 나뉜다.  
CPU 인터럽트와 Hardware 인터럽트이다.

CPU 인터럽트는 정상적으로 수행할 수 없는 명령어가 입력되면,  
CPU는 인터럽트를 발생시킨다 -> 예외

하드웨어(비동기) 인터럽트는 입출력 장치(하드웨어)로부터 발생하는 인터럽트이다.

이러한 인터럽트를 처리하기 위해 특정 인터럽트 신호에 대해 미리 정의된 프로그램 또는 함수를 인터럽트 서비스 루틴(인터럽트 핸들러)라고 한다.

하드웨어 인터럽트의 예시를 들자면

```python
import time, signal

def handler(signum, frame):
    print("키보드 인터럽트 감지!!")
    print("신호 번호: ", signum)
    print("스택 프레임: ", frame)
    exit()

signal.signal(signal.SIGINT, handler)

while True:
    print("===5초마다 출력!!===")
    time.sleep(5)
```

이러한 코드를 작성하고 실행했을 때,  

<img src="https://github.com/Samiiz/Samiiz.github.io/blob/master/posting_images/OS/hardware_interrupt_test.gif?raw=true">

while문 실행 중간에 control + C로  
하드웨어 인터럽트를 확인할 수 있습니다.  

## 마치며

저는 OS에 대한 이해를 하려고 공부하면서,  
지금까지 당연하다고 생각되었던 내용들이  
전부 이러한 기초 과정들을 통해 이루어진다는 것을 알게 되어  
신기하면서도 재미가 있었습니다.

다음 포스팅에서는 프로세스에 대하여 알아보도록 하겠습니다.

> <u>배움은 젊음의 샘이다.
> 아무리 나이가 많이 들었더라도 배움을 멈추지 마라. -도교</u>
