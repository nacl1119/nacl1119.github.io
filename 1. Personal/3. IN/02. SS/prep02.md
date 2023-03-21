# Prep
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


## ARM의 Interrupt 핸들링 방식

## AFDX 메시지 누락사항
AFDX는 이더넷 UDP에 기반한 항공용 이더넷 스위치이다. 항공시스템은 통신에 필요한 장비간 데이터통신 대역폭이 정해져있기 때문에 AFDX 스위치가 각 채널별 스케줄링을 통해 트래픽을 제어할 수 있는 특징을 가지고 있다. AFDX 시스템은 100Mps의 물리적링크를 가지는 End System과 AFDX 스위치로 구성된다. 각 물리적 링크는 여러개의 Virtual Link 설정을 통해 트래픽을 제어하도록 되어있고, ES와 스위치 모두 VLink 설정이 필요하다. Vlink 설정시 하나의 장비에서 다른 장비로 전송하는 메시지 종류까지 설정할 수 있고, 가상링크별 대역폭 조정을 위한 BAG time 을 설정한다. 이때 BAG Time 에서 허용하는 전송량을 넘어서게 되면 다음 BAG Time slot으로 넘어가게 된다.  
우리가 사용한 AFDX 스케줄러는 여러 VLink에서 동일한 시간에 트래픽을 발생시키면 프레임을 드랍시키는 문제가 있었다. 초기에는 AFDX 스위치에서 관리하는 VLink별 입력큐가 충분하여 문제가 되지 않았으나 과제가 진행되면서 통신량이 많아지자 드랍되는 케이스가 발견되기 시작했다. 원인은 스위치였으나 스위치제조사와의 계약관계상 문제로 인해 SW 수정을 할 수 없게 되어 AFDX End system인 비행조종컴퓨터에서 전송 스케줄링을 별도로 구현하여 AFDX 스위치에서 처리 가능한 만큼 패킷을 전송하도록 하였다.  
## Linux 부팅, Xen 부팅

## ARM Trustzone 부팅

## u/cos 부팅

## uboot 부팅

## IRQ, FIQ 구분 방식


## Xen의 Interrupt 핸들링 방식

## Trustzone Interrupt 핸들링 방식

## top half bottom half
## Device driver 동작방식

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
