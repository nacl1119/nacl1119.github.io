# Overair Interview 1st Round
## 지원
### 지원 사유
미국에서 경력을 쌓는 것이 다시 한국을 들어오더라도 큰 도움이 될 것이라고 생각한다. 근데 그러려면 최소 2년은 근무해야겠단 생각이 든다. 아내랑 프랑스 신혼여행 중에 프랑스 이민에 대한 생각도 해봤는데 뭐 어디가 됐든 나중에 다른 나라에 가서 일할 때 미국 회사에서 일한 경력은 분명히 도움이 될 것이다. 그리고 최소한 미국 영주권을 취득하면 한국, 미국 다 거주 할 수 있으니 젊어서 직장있을때 취득해두는게 큰 도움이 될 것이다.  
### 지원 분야
Embedded Software, Flight Software 두 분야를 지원했다. 결과는 Embedded 만 답장이 왔다. 한화시스템에서 UA(Unmanned Aircraft) 관련 프로젝트를 진행했고, Flight Control 쪽이 더 흥미로워 보여서 지원했는데 아무래도 Embedded Software 전공한 것도 그렇고, 경력 자체도 C 응용프로그램 쪽이어서 응답이 그쪽에서만 온 것 같다. 

## 준비
### JD 연구
당연한 애기지만 JD(Job Description, 직무 설명)에 해당 포지션으로 채용됐을 때 할 일이 적혀 있으므로 거기에 필요한 지식을 준비했다. JD에는 보통 아래와 같이 3가지 내용이 적혀 있다.  

1) Roles and Responsibilities
2) Required Qualifications  
3) Desired Qualifications  

저기에 모든 내용을 자세히 알 필요가 없다고 생각하지만 모든 내용에 대해서 교과서에 나올 법한 수준으로 2~3문장의 설명은 할 수 있을정도로 준비는 되어야 생각해서 키워드들을 발췌하여 구글링하여 공부하였다.

### Resume 연구

### Embedded System & C programming 연구

## 인터뷰 진행
면접관은 자신의 이름과 가벼운 인사로 면접을 시작하였다. 그리고 Overair가 무슨 일을 하는 회사이고 자신이 속한 팀이 무슨 일을 하는지 소개하면서 왜 회사에 대한 관심을 왜 가졌는지, 관련된 경험은 뭐가 있는지 물어봤다. 총 1시간의 면접시간동안 꼬리에 꼬리를 무는 질문과 대답으로 15~20분 정도씩 대답했고, 면접관이 자신의 궁금증이 어느정도 해결 되었을때 이력서 들여다 보면서 다른 질문을 만들어서 했다. 대화의 큰 주제는 이정도가 나왔다.  
 - 회사에 대한 관심 및 직무에 대한 관심과 이해도
 - 가진 경력 중 직무와 밀접한 내용과 해당 경력에서 쌓은 기술에 대한 이해의 깊이
 - 내가 가진 경력에서 면접관의 개인적인 호기심 질문  

### 인터뷰 질문과 대답
 **Q1. 지금 소개한 내용 중에서 본인이 흥미로운 분야는 무엇이고 이유는 무엇인가**  
 A. 비행 제어에 관련된 부분을 좋아한다. 현재 다니고 있는 회사나 이전 회사도 모두 방위산업에 관련된 회사인데 직접 움직이는 실물을 볼 수 있는 SW를 개발하는 것을 좋아한다. UA라는 분야에서 Overair가 도전하고 있는 Air taxi라는 사업이 재밌어보인다. (Embedded 흥미를 강조해야겠구나 생각하면서 화두 전환) 내가 지원한 Embedded Software 분야가 Motor 제어쪽 업무가 JD에 많이 써있어서 무인기 쪽 모터제어가 어떤 일을 하는지 찾아봤다.  
 
 **Q2. 모터 제어에 대해 아는만큼 설명해봐라**  
 Motor는 크게 두가지로 Brushed Motor와 Brushless Motor로 구분된다. 지금 JD는 Brushless Motor Contorl이라서 MATLAB에서 제공하는 Motor cotrol 관련 튜토리얼을 찾아서 들었다. Motor는 rotor, stator로 구성된다. (Sensor를 언급했어야 했는데 까먹었다...ㅠ) 이때 sator의 전류 흐름을 제어하여 rotor의 움직임을 만들어낸다. 해당 전류 흐름을 실시간으로 제어하는 SW제작이 내 업무가 될 것이다.

 **Q3. 모터 제어에 필요한 물리 이론을 아무거나 말해봐라**  
 기억나는 물리이론이 오른손 법칙밖에 없다. 엄지가 전류(Current), 검지가 자기장(Magnetic), 중지가 힘(Force)의 방향인 것 같다.   
-> 완전 틀렸다 ㅠㅠ 엄지가 힘, 검지가 자기장, 중지가 유도 전류(Indeced crurrent) 방향이다... 게다가 모터의 움직임은 왼손 법칙과 관련이 있는 것 같다. -_-;; 

 시작했다. 면접관이 자신의 회사를 소개하는 부분이나 내 경력에 대한 인지상태를 봤을때 우리 회사측에서 따로 언급 받은 것은 없어보였다. 우리 인사팀에게 들었을 때에도 현지 채용하는 것과 같은 프로세스를 밟게 될 것이고 합격시 근무 조건만 주재원 대우를 받는다고 했는데 진짜 그런 것 같다. 주재원 인터뷰니까 그래도 현지 채용 보단 쉽지 않을까 하는 약간의 기대감이 있었는데 전혀 아니었다.  
면접관이 자기 회사에 대한 소개를 자세히 하는 건 새로웠다. 아무래도 내가 대기업 취업 경험만 있다보니 기존에 면접 본 회사들은 자기들이 하는 일을 따로 소개하지 않았던 것 같다. 아, 팀단위로 무슨일을 하는지는 말을 했었던 것 같다.  
면접관의 회사 소개가 끝내고 
