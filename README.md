 ## 프로그램 명칭(국문)
   랜덤 모빌리티를 가지는 애드혹 네트워크 구현

 ## 프로그램 명칭(영문)
   Ad-hoc network formation with random mobility

 ## 발명자 리스트
   이현희, 박서연, 박지현, 김나영, 박형곤, 권민혜
   
## 프로그램 전반적인 목적

본 연구는 사물인터넷과 같은 네트워크 시스템에 존재하는 사물(Things) 개체(Agents)들이 분산적 무선 네트워크(애드혹 네트워크)를 형성한 연구이다. 사물들이 스스로 네트워크를 잘 구축하고 유지하기 위해서는 주변에 있는 다른 개체들을 모니터링하고 서로간의 상호관계성을 잘 파악할 필요가 있다. 본 연구에서는 개체의 이동성 시스템(랜덤 모빌리티)을 적용하여 실제 지능형 네트워크(애드혹 네트워크) 성능을 확인한다.
데이터를 보내는 방식은 총 두가지로 1)multicast 방식 과 2)broadcast 방식으로 설정하였다. 

## 프로그램 실행 방법
 
- 실험 장비 및 도구: Xbee S2C 8개, 라즈베리파이 6개, rc카 6개, 노트북, python, XCTU 
- 실험 장소 : 장애물이 없고 경사도 없는 넓은 공간, 만약 장애물이 아예 없는 장소가 불가능 하다면 장애 요인이 각 거리마다 비슷한 확률로 나타나는 장소도 가능
![image](https://user-images.githubusercontent.com/67427006/93089940-075a9580-f6d7-11ea-9cb2-ad965ce99962.png)

- 실험 전 세팅 (multicast 방식)
1. 실험에 사용되는 모든 8개의 xbee를 XCTU라는 프로그램을 이용하여 채널을 통일시킨다
2. 노트북에 source node에 해당하는 xbee 1개를 포트에 꽂고, source_node_multicast.py를 Pycharm에서 실행시킨다.
3. relay node에 해당하는 xbee를 각각의 rc카와 연결한 라즈베리파이 포트에 꽂고, 라즈베리파이에서 각각 xbee 넘버(n)에 해당하는 relay_node_multicast_mobility.py를 auto-running.
4. 각 relay node 마다 예제 코드에서 topology. png 파일을 참고하여 다음과 같이 수정하면 된다.
line 13에서 ID_LIST 수정
line 86에서 node_num 수정
ex) relay node 01 에서 ID_LIST는 "03, 04"로 수정
ex) relay node 01 에서 node_num은 "01"로 수정


- 실험 전 세팅 (broadcast 방식)
1. 실험에 사용되는 모든 8개의 xbee를 XCTU 프로그램을 이용하여 채널을 통일시킨다
2. 노트북에 source node에 해당하는 xbee 1개를 포트에 꽂고, source_node_broadcast.py를 Pycharm에서 실행시킨다.
3. relay node에 해당하는 xbee를 각각의 rc카와 연결한 라즈베리파이 포트에 꽂고, 라즈베리파이에서 각각 xbee 넘버(n)에 해당하는 relay_node_broadcast_mobility.py를 auto-running.


- 야외 실험 방법(multicast 방식과 broadcast 방식 모두 동일)
1. 미리 세팅한 xbee와 라즈베리파이에 전원을 연결한 후, xctu를 통해 결과를 확인한다.
2. coordinator 노드와 relay node에서 각각의 소프트웨어 로직을 실행시킨 후, 실험결과가 나올 때까지 기다린다.
3. 실험이 끝난 후에, destination node 코드 파일이 저장된 동일 위치에 생긴 ‘text.xlsx’ 파일을 통해 실험 결과를 확인한다.

## 프로그램 결과에 대한 설명
'text.xlsx'에 source node, destination node, history, hops, message data 가 차례로 기록된다.
![image](https://user-images.githubusercontent.com/67427006/93090534-d890ef00-f6d7-11ea-895b-a62f9ec31151.png)
