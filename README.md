# Unity의 ML-Agents 툴킷을 사용,  자율주차에 중점을 둔 강화 학습 프로젝트

이 프로젝트는  **"간단하고, 확실한 자동주차 AI"** 를 모티브로 삼고 임 하였습니다.


**본 프로젝트에 참여 한 팀원**

 <a href = "https://github.com/LDH0094"><img alt="GitHub" src ="https://img.shields.io/badge/GitHub-181717.svg?&style=for-the-badge&logo=GitHub&logoColor=white"/> 이 덕현 (리더, 기획 및 Python API & SAC 알고리즘 구성 )
  
 <a href = "https://github.com/MarigoldTea"><img alt="GitHub" src ="https://img.shields.io/badge/GitHub-181717.svg?&style=for-the-badge&logo=GitHub&logoColor=white"/> 조 재웅 (팀원, 환경 구조 및 설계) 


### 프로젝트 개요

아직 초기 단계지만 자율주행이 점점 우리 일상 속으로 빠르게 녹아들고있습니다, 우리가 차량을 이용하면 어쩔수없이 마주치는 **주차** 는 어쩔때는 굉장히 피곤한 상황을 만들고는 합니다
그래서 저희는 빠르게 발전하는 기술에 힘 입어 이런 프로젝트를 계획해서  만들어보면 좋지 않을까? 라는 호기심에서부터 시작되었습니다

  
  

## 자율 주차 진행 및 결과 

Episode: 0 ~ 500    |  Episode: 500 ~ 1500 
:-------------------------:|:-------------------------:
 <img src="/screenshots/1.gif"> |  <img src="/screenshots/2.gif"> 

훈련 데이터가 충분히 저장되지 않으면 올바른 주차를 하지못합니다
 
 Episode: 1500 ~ 2000  |  Episode: 20000 ~ 30000 
:-------------------------:|:-------------------------:
 <img src="/screenshots/3.gif">  | <img src="/screenshots/4.gif"> 

 학습하면 학습할수록 차랑(Agent) 이 ,  지정한 구역으로 주차를 하는 모습을 보실수 있습니다 


  
## 감지 센서

<img src="/screenshots/Ray_perception_sensor.png" height="350"/> 


환경내 물체와 충돌을 감지하고 피하기 위해 감지 센서 를 Agent 에 사용합니다 이 센서는 충돌과 , Agent 가 목표를 향해 조작할때 매우 도움이됩니다 훈련이 계속 될수록 자율주행 자동차의 Light Detection and Ranging(Lidar) 와 매우 유사해짐을 볼수있습니다


  

**훈련 도중 3가지의 특성이 관찰 되었습니다**

* Agent 는 센서를 통해 주변의 상황을 고려하기 시작합니다.
* Agent 는 센서를 사용하여 움직임을 조작하기 시작합니다.
* 센서는 목표물인 주차 장소가 가까워 질 때 복잡한 주차 제어를 가능하게 하였습니다 



  


## 결과 및 분석 

<img src="/screenshots/result.png" height="350" width="400"/>

 **_Policy loss, 낮으면 낮을수록 좋은결과._**

그래프에서 알수 있듯이, 약간의 진동이 있습니다.첫 번째 빨간색 화살표는 Agent가 주어진 환경을 빠르게 이해할 수 있다는것을 보여줍니다.

두번째 화살표는 주어진 환경에서 훈련된 Agent 가 어떻게 행동하는지 보여줍니다. 만약 훈련 데이터가 잘못된 Reward 설정으로 저장되어버리면  Agent는 처음 에피소드 동안 작동한것처럼 완전히손실되어버립니다.

 이 문제는 Reward 시스템을 다시 정의하면 해결 할수있습니다.
## 시작하기

**프로젝트를 시작하려면 다음 내용을 설치하여야 합니다**
```sh
pip install --upgrade pip
pip install tensorflow
# install the latest tensorflow-probality version
pip install --upgrade tensorflow-probability
python -m pip install mlagents==0.28.0
```

**이 프로젝트를 동작시키려면?**
* 이 파일을 열고 실행합니다 [agent.ipynb](/Soft_Actor_Critic/agent.ipynb) 훈련이 자동으로 시작되고 완료되면 각 NN(신경망) 에 저장되어 저장된 파라미터가 로드 됩니다.
