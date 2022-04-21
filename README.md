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
  
## 자동차(Agent) 에 사용된 파일들 입니다


  


## Results and Analysis

<img src="/screenshots/result.png" height="350" width="400"/>

 **_Policy loss. The lower the better._**

As it is clear in the graph, there is a slight oscillation. The first red arrow provides an idea that the agent was able to quickly understand its enviornment. 

Nonetheless, the sencond arrow demonstrates how extremely trained agent behave in the settled enviornment. When training data is stored with poor reward setting, the agent is again completely lost just like it behaved during the first few episodes. 

This issue can, however, be fixed with re-defining its reward system. 
## Get Started

**To get started with this project, you must install:**
```sh
pip install --upgrade pip
pip install tensorflow
# install the latest tensorflow-probality version
pip install --upgrade tensorflow-probability
python -m pip install mlagents==0.28.0
```

**To run this project:**
* Open and run [agent.ipynb](/Soft_Actor_Critic/agent.ipynb) file. The training will automatically start and when finished will load the saved parameters for each NN. 
