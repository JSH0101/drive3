### 주행-3

***
#### Fullfilment 가상 서비스 환경 실습

<br>
<br>

#### openmanupulator 명령어

```
ros2 launch open_manipulator_x_controller open_manipulator_x_controller.launch.py usb_port:=/dev/ttyACM0
ros2 run open_manipulator_x_teleop teleop_keyboard
```
<br>
<br>

#### 필수 구현 사항 (완료 못한 사항은 bold체)
1. GUI
* log in
* **비상 상황 발생 시 등록된 담당자에게 메일로 내용 알림**
* 글로벌 카메라와 yolo인식 결과 화면 표시
* AuRco 마커 상대 위치와 각도 표시
* conveyor 수동 조작 버튼
2. Conveyor
* 정해진 길이만큼 이동
* 동작 완료시 외부에서 인식
* 동작 중 usb가 뽑혔을 때 인식
3. AuRco
* A,B 마커 사이의 C마커의 상대위치(카메라 위치 이동)
* C마커와 A,B마커 사이의 각도 (C마커 위치 및 각도 조종)
4. Manipulator + YOLO
* 로봇팔로 학습데이터 자동 수집
* YOLO 인식 결과를 이용해 로봇팔을 움직여 박스 잡기
* 컨베이어 벨트 위에 박스 올려놓기
* 바구니에 박스 모두 담기
* 전체 수행시간 체크
* **테이블에 박스 개수가 부족하면 오류로 인식**
* 로봇의 위치를 +-1Cm 앞뒤로 이동
5. Digital Twin
* 현재 코드 수정없이 unity6에서 YOLO 학습에 필요한 data 수집
* **학습된 결과로 로봇팔 동작**
