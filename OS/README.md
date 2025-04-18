# OS

## 목차
- [1. 프로세스와 스레드의 차이](#1-프로세스와-스레드의-차이)
- [2. 멀티스레드](#2-멀티스레드)
- [3. CPU 스케줄러](#4-cpu-스케줄러)

---

## 1. 프로세스와 스레드의 차이
프로세스→프로세스란 실행중인 프로그램을 뜻하며 보조기억장치로부터 메모리에 적재되어 CPU에게 할당받을 수 있는 것을 말한다. 운영체제로부터 주소 공간, 파일, 메모리 등을 할당받으며 이것들을 총칭하여 프로세스라고 한다. 구체적으로 각각의 프로세스는 **독립된 메모리 공간**을 가짐 (코드, 데이터, 힙, 스택 분리됨).

### *PCB
프로제스 제어블록이란 프로세스와 관련된 정보를 저장하는 자료구조이다.

운영체제는 이 PCB를 통해 특정 프로세스를 식별하고 해당 프로세스를 처리하는 데 필요한 정보를 판단한다.

### *PCB에 담기는 정보

1.프로세스 ID (PID):특정 프로세스를 식별하기 위해 부여하는 고유번호

2.레지스터 값:프로세스는 자신의 실행차례가 돌아오면 이전에 진행했던 작업을 이어 나가기 위해 레지스터 의 중간값들을 모두 복원한다.

3.CPU스케줄링 정보:프로세스가 언제,어떤 순서로 CPU를 할당받을지에 대한 정보

4.메모리 관리정보:해당 프로세스가 메모리의 어느 주소에 저장되어있는지에 대한 정보

### *스레드
스레드란 프로세스를 구성하는 실행의 흐름 단위이다. 프로세스 내에서 각기다른 스레드ID.레지스터 값 스택으로 구성된다. 한 프로세스 내에서 실행에 필요한 최소한의 정보(레지스터,스택)만을 유지한 상태에서 프로세스의 자원(코드,데이터,힙영역)을 공유한다

## 2. 멀티스레드
멀티 스레딩이란 하나의 프로세스 안에서 스레드를 여러개 실행시켜 동시에 여러개의 작업을 수행할 수 있는 기법이다. 하나의 프로세스 내에서 메모리의 Stack영역을 제외한 나머지 Data,Code,Heap영역을 공유하기 때문에 메모리자원을 아낄 수 있다.그리고 이러한 특성으로 인해 스레드 간의 빠른 통신이 가능하고 컴퓨터 자원을 효율적으로 사용할 수 있다. 하지만 이러한 특성 때문에 동기화 문제가 발생할 수 있다. 프로세스간에는 자원을 공유하지 않지만 스레드는 메모리 자원을 공유하기 때문에 한 가지 자원에 여러 스레드가 동시에 접근하면 서로 충돌하여 엉뚱한 값을 읽을 수 있기 때문에 동기화(Synchronization) 작업이 필요하다.

### *동기화(Synchronization)
동기화란 공유자원에 여러 스레드가 한 번에 접근하는 것을 막고 순차적으로 접근하게 만드는 것이다.



## 4. CPU 스케줄러
- FCFS, SJF, RR 등 알고리즘 비교

