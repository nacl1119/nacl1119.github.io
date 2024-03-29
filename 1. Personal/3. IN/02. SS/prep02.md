# Prep

## 프로젝트에서 어려운 부분
### 표준 프로토콜 및 개발에 대한 설명
* 각 장비담당자들에 대한 프로토콜 교육
* 장비담당자간 인터페이스 정의에 대한 설명, 구현방법론 설명, 서로 주고 받을 데이터에 대한설명 부족
* 오실로스코프, HW모니터링장비 레벨의 디버깅 필요 설명
* 장비간 불필요한 대역폭 낭비를 막기 위한 최소 데이터 설명
* 주요 코딩룰에 대한 숙지
### 인터페이스 연결 문제
* AFDX를 처음 써보면서 스터디 부족으로 일어난 문제들 
  * 참고자료
    * https://koreascience.kr/article/JAKO201634347491676.pdf
    * https://koreascience.kr/article/JAKO202209858365235.pdf
    * AIM사 교육자료 https://www.aim-online.com/wp-content/uploads/2019/06/aim-afdx-training-10-10-01-u.pdf
    * 인텔릭스 AFDX 보고서 https://scienceon.kisti.re.kr/commons/util/originalView.do?cn=TRKO201600018144&dbt=TRKO&rn=
  * AFDX End system과 Switch에 대한 양쪽 설정을 맞춰줘야 하는 부분
  * 큐잉은 송/수신시 저장된
  * Virtual Link와 BAG 타임으로 대역폭이 제한되므로 End System 을 사용하는 프로그램에서도 최대한 맞춰서 보내야 하는 상황임
  * Full spec을 공부하고 시작할수 없는 상황에서 이더넷 스위치 같이 사용하다보니 스위치의 대역폭 스케줄링으로 인한 프레임 드랍율 증가
  * 문제가 일어난 상황에 대한 기록을 남기지 않는 담당자의 태도
* 1553B 구현방식
  * 1553B 표준이 있으나 현업을 통해 경험한 지식으로만 개발중인 두 팀간 커뮤니케이션을 돕기 위한 1553B 세미나 진행
  * 서로 다른 용어를 사용하거나 같은 용어를 다른 의미로 사용중으로 인한 커뮤니케이션 오류 발생
  * 상대 장비의 불명확한 디버깅으로 인한 책임 미루기 

## 이론 지식

### What is reliable software

# ARM Exception Level
ARM에서 제공하는 7가지 모드가 있는데 그 중 5가지가 Exception Mode에 해당합니다. Abort, Undefiend, FIQ, IRQ, supervisor 가 그 5가지 입니다. 모드가 바뀌는 경우 사용하는 레지스터가 변경되는 특징이 있습니다.
  * THUMB 모드는 16bit 동작상태를 나타내는 모드로 다른 동작모드와 의미가 다른다.
  * 

* ARM v6, v7 까지는 User > Supervisor > IRQ > FIQ 모드로 유사하게 동작  
  * [User, System, FIQ, IRQ, Supervisor, Abort, Undef](http://recipes.egloos.com/4985227)
* ARM v8부터 EL(Exception Level) 개념 등장 EL0~EL3 으로 구분됨  
* EL0
  * ARMv7 의 User mode와 동일, SVC(SuperVisor Call)을 통해 SW Exception발생, 익셉션벡터
* 


## ARM의 Interrupt 핸들링 방식
https://developer.arm.com/documentation/ihi0048/b/Interrupt-Handling-and-Prioritization/General-handling-of-interrupts
https://developer.arm.com/documentation/ihi0048/b/Interrupt-Handling-and-Prioritization/General-handling-of-interrupts/Interrupt-handling-state-machine?lang=en

## Interrupt Handler 구현 주의사항

## Linux 부팅, Xen 부팅

## ARM Trustzone 부팅

## u/cos 부팅

## uboot 부팅

## IRQ, FIQ 구분 방식
외부 장치와 연결된 GIC에 Interrupt input이 연결되어있고, 해당 인터럽트들을 IRQ, FIQ 어느 것으로 처리할 것인지 GIC register설정을 통해 구분한다.  
https://www.realdigital.org/doc/87be521204ed2c4447d567b666961ce8  

GIC를 통해 구별되어 발생하는 인터럽터는 ARM core의 exception 처리모드에 따라 ARM vector table에 접근하여 처리 함수를 불러오게 된다.


## Xen의 Interrupt 핸들링 방식

## Trustzone Interrupt 핸들링 방식

## top half bottom half
## Device driver 동작방식


### TOP Half Bottom Half

### Xen이 Type1 가상화인 이유

## 프로젝트 수행내용
## 요구사항분석부터 개발, 시험 등 과제 전반적인 내용에서 맡은 역할이 무엇인지

## 프로토콜에 대한 상세한 설명

## 표준프로토콜에서 네트워크 프로토콜이 있는지

## 프로토콜 인증 방식은 어떻게 되는지

## ASPICE 등 국제 인증 관련 업무가 있는지

## 설계시 모델링 도구, 방법론을 사용한 것이 있는지

## 어셈블리 코딩경험 있는지
## 시간 동기화 GPS, Linux, Windows, RTST 
어떤 시스템에서 시간을 계산할때는 epoch 라는 기준시간대가 존재한다.
대표적으로 Linux와 같은 Unix 기반 시스템에서는 1970년 1월 1일 0시 0분 0초를 기준으로 시간집계를 시작한다.
https://en.wikipedia.org/wiki/Epoch_(computing)

그런데 각 시스템 혹은 운영체제마다 epoch 가 달라지게 된다. 이 것은 해당 시스템이나 OS 설계시 각자의 이유로 결정된 부분이다.
단일 시스템은 하나의 시간시스템 기반으로 동작하기때문에 문제가 되지않는다. 문제가 되는 것은 여러 시스템의 네트워크를 통해 동작하고 있는 환경에서 동일한 시각에 특정 기능을 수행해야 하는 경우 문제가 일어난다. 이럴 때 필요한 것이 시간동기화 방법이다. 기본적으로 리눅스, 윈도우즈, VxWorks등은 NTP(Network Time Protocol), SNTP(Simple NTP), PTP(Precision Time Protocol) 라는 UTC 시간을 기준으로한 시간동기화 서비스를 OS 차원에서 지원하기 때문에 해당 서비스를 활성화 하는 것만으로 시스템간 시간동기화를 맞출 수 있습니다.
그렇다면 NTP, SNTP를 지원하지 않는 경우 어떻게 해야할까요? 일반적으로 GPS시간을 받아서 시스템시간에 동기화를 맞추게 되는데 GPS의 경우 epoch 값이 2019년 4월 7일 0시 0분 0 초입니다. 그럼 GPS로에서 수신한 데이터가 GPS Week = 203, GPS Time = 313278값인경우 2019년 4월7일에서 203주가 지났으며 일요일을 기준으로 313278 초가 지난것입니다. 이것을 우리가 쓰는 시간 단위로 변환하면 2023년 3월 21일 3시 1분이 됩니다.
그럼 이 시간 값을 운영체제에서 지원하는 시스템 시간 변경 API를 사용하여 입력해주면 시스템의 시간이 GPS와 동기가 맞게 됩니다.
주의할 점은 GPS 시간은 윤초를 반영하지않으므로 GPS 시스템이 시작한 1980년 1월 5일 부터 누적된 윤초 18초를 더해줘야 실제 시간과 맞게 됩니다.

### GPS roll over
GPS의 경우 GPS 시스템이 시작된 1980년 1월 5일부터 week 값을 10bit 크기로 계산하였습니다. 그러다보니 1023주차가 넘어가면서 0으로 roll over가 되게 되었습니다. 0주 부터 1023주 까지는 약 19.7년으로 1차 rollover는 1999년 8월에 일어났고 2차 rollover는 2019년 4월에 일어났습니다.
https://www.gps.gov/support/user/rollover/

### AFDX 메시지 누락사항
AFDX는 이더넷 UDP에 기반한 항공용 이더넷 스위치이다. 항공시스템은 통신에 필요한 장비간 데이터통신 대역폭이 정해져있기 때문에 AFDX 스위치가 각 채널별 스케줄링을 통해 트래픽을 제어할 수 있는 특징을 가지고 있다. AFDX 시스템은 100Mps의 물리적링크를 가지는 End System과 AFDX 스위치로 구성된다. 각 물리적 링크는 여러개의 Virtual Link 설정을 통해 트래픽을 제어하도록 되어있고, ES와 스위치 모두 VLink 설정이 필요하다. Vlink 설정시 하나의 장비에서 다른 장비로 전송하는 메시지 종류까지 설정할 수 있고, 가상링크별 대역폭 조정을 위한 BAG time 을 설정한다. 이때 BAG Time 에서 허용하는 전송량을 넘어서게 되면 다음 BAG Time slot으로 넘어가게 된다.  
우리가 사용한 AFDX 스케줄러는 여러 VLink에서 동일한 시간에 트래픽을 발생시키면 프레임을 드랍시키는 문제가 있었다. 초기에는 AFDX 스위치에서 관리하는 VLink별 입력큐가 충분하여 문제가 되지 않았으나 과제가 진행되면서 통신량이 많아지자 드랍되는 케이스가 발견되기 시작했다. 원인은 스위치였으나 스위치제조사와의 계약관계상 문제로 인해 SW 수정을 할 수 없게 되어 AFDX End system인 비행조종컴퓨터에서 전송 스케줄링을 별도로 구현하여 AFDX 스위치에서 처리 가능한 만큼 패킷을 전송하도록 하였다.  

## 기타 준비
## 리눅스명령어
dmesg를 통해 커널 부팅 로그 및 커널레벨 수행내역 확인이 가능하다. dmesg | grep eth, usb, Linux 조합으로 디바이스 커널동작 메시지 확인가능
https://eehoeskrap.tistory.com/259
syslog 활용해서 stack dump 를 보면 call stack에서 문제가 생겼는지 확인 가능
https://www.kernel.org/doc/html/v4.13/admin-guide/bug-hunting.html

## gcc g++ 버전 확인
gcc  
predefine macro https://gcc.gnu.org/onlinedocs/gcc-3.2.3/cpp/Standard-Predefined-Macros.html  
g++  
macro: __cplusplus  
https://dulidungsil.tistory.com/entry/GCC-%EB%B2%84%EC%A0%84%EA%B3%BC-C-%EB%B2%84%EC%A0%84-%EB%A7%A4%EC%B9%AD  
https://ndb796.tistory.com/428  
https://qa.apthow.com/archives/1836  
supported functions macro https://gcc.gnu.org/projects/cxx-status.html  
