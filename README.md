# 감정저금통-뇌파를 이용한 기부유도시스템

### 특별학기 신경공학 수강(2019.01.18~2019.01.31)

----------

__주제__: 뇌파를 이용한 기부유도시스템

  - 평소뇌파와 주어진 자극 이후의 P300을 비교하여 기부자의 집중도를 추출하여 개개인에 따른 기부영상, 문구, 기부금액을 시각화 해주어 기부를 유도하는 시스템

__제안배경__: 2019년 기준, 사랑의 온도탑에 쌓인 모금액이 지난 해 같은 기간의 약 80% 수준이라고 보도되었고 이의 배경은  경제적 여유 부족과 당시 여러 사건들로 인한 후원금의 쓰임새에 대한 불신 등이 있었음.             
  _->기부자에게 맞는 기부시스텡을 제공함으로써 이를 해결하고자함_

----------
__프로젝트 내용:__                          
__*참고) emotiv epoc기기없이는 사용이 불가함 + Active license부분에 자신이 설정한 아이디 및 비밀번호를 맞게 입력해야함*__                     

__1. 하드웨어__:                    
<img src="https://user-images.githubusercontent.com/47767202/79405595-da8f3e80-7fcf-11ea-8e63-79c6c278d155.jpeg" width="40%">
> emotiv epoc - 뇌파 측정 센서. 14채널 지원.

-------------

__2. 활용이론__:

<img src="https://user-images.githubusercontent.com/47767202/79638403-fb1deb00-81bf-11ea-9b0a-4e42eecbc1d3.png" width="40%">  

> P300: 특정한 정보를 내포하고 있는 자극을 받은 뒤 일정 시간 동안 일어나는 뇌의 전기적 활동(ERP) 중 하나로 약 300ms 후에 발생하는 뇌파

<img src="https://user-images.githubusercontent.com/47767202/81173727-80383b00-8fdb-11ea-98cb-0066a994e390.jpg" width="40%">

> 10-20 system: 뇌파 신호를 취득하기 위해 전극 부착 위치와 명칭이 표준화된 시스템
>> 시스템의 목적에 따라 집중뇌파와 관련이 있는 채널 중 편의상 두 채널만 사용하였음(F3,F4)

-----------

__3. 시스템 처리과정__:

- Flow Chart                            
  <img src="https://user-images.githubusercontent.com/47767202/79882335-5f91b200-842d-11ea-8776-dfbe6b663bd3.png" width="60%">
  - 이어폰과 emotiv를 착용한 후 10초간 **뇌파**의 **reference측정**
  - 4가지 **카테고리**(옷,건강,애완동물,가족)를 보여주며 사용자가 자신의 **관심사를 생각**하게함
  - 위 4가지 카테고리 사진이 1초씩 랜덤으로 **4세트를 시청**하게함
  - 총 16번 보여지는 동안 **가장 높은 집중도가 높았던 카테고리**를 보여주고 이에 관련한 **기부영상**을 1분간 **시청**하게함
  - 1분가량의 기부영상을 시청하는 동안 사용자의 집중정도(뇌파)를 측정함
  - 영상이 끝난뒤
   1. 영상의 각 구간에는 기부를 유도할 수 있는 맞춤 문구가 설정되어있어, 사용자가 가장 관심있게 시청한(집중도가 높았던) 구간의 문구를 출력함
   2. 맞춤문구와 함께 사용자의 집중력 그래프를 보여줌
  - 결제(기부)유도 yes: 맨 처음 측정한 reference와 영상을 시청하면서 발생한 뇌파를 비교하여 각 사용자에게 맞는 금액을 제시함 -> QR코드 결제 후 시스템종료
  - 결제(기부)유도 no: 시스템종료
  
-----------

__4. 사용 프로그램__:       

Visual Studio: 뇌파 데이터 받아오는 부분부터 윈폼까지 모두 작성(사용 언어: c#)

-----------

__5. 결과__: 

- 뇌파 레퍼런스 측정 화면                                                    
<img src="https://user-images.githubusercontent.com/47767202/82135844-34d72580-9842-11ea-98d9-cbe2dcb61bfb.png" width="50%">

- 관심사 선택 화면(두번째,세번째 사진은 랜덤으로 보여지는 화면의 예시를 나타낸 것임)
  <img src="https://user-images.githubusercontent.com/47767202/82135982-d448e800-9843-11ea-9901-e5958aaca4da.png" width="65%">
