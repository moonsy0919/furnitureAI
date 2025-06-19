# furnitureAI 앱 프로젝트 소개
---
1. 프로젝트 소개
--
해당 프로젝트는 고성능 AR기기와 파노라마 사진과 같은 준비물이 있어야, 가구 추천 배치 앱을 사용할 수 있는 불편함을 해소하고자 진행하였다.
본 프로젝트는 단일 RBG 이미지만으로도 가구 추천 배치 앱을 구현할 수 있다고 생각하여 프로젝트를 시작하게 되었다.
프로젝트의 기술로는 가구 객체 인식 담당 yolov8, 이미지의 거리감을 구분해주는 MiDas, 가구 추천 알고리즘으로 채택한 GNN을 사용했다.
--
2. 핵심 기능
**
사진 기반 공간 분석 -> 사용자가 찍은 사진에서 가구 / 빈 공간 인식 
![image](https://github.com/user-attachments/assets/ba57c543-9e78-4bae-a15d-21f2aff6ab18) ![image](https://github.com/user-attachments/assets/b2f5fcf0-dd8a-4b0f-825a-b8402f16294e)
직접 배치 기능 -> 사용자가 드래그하여 원하는 위치에 가구 배치 (현재 거의 진행 완료)
AI 가구 추천 -> yolo가 인식한 가구의 속성에 맞게 GNN이 가구를 추천
---
3.개발 환경
---
Mac,React-native
---*
**4. 화면 구성**
**
홈 화면 - 사진 촬영 or 갤러리 선택
사용자 선택 화면 - yolo가 인식한 객체와 빈공간 시각화, 사용자는 빈 공간을 선택하여 어느 빈 공간에 가구를 놔두고 싶은지를 선택 가능함.
RoomEditor 화면 - 선택한 빈 공간만 남긴 나머지 구역(yolo,빈공간) 제외, 아래쪽에 GNN을 통한 가구 추천 리스트 시각화 및 
사용자가 직접 드래그 & 배치 기능 탑재 (거의 완성)
***
5.앱 실행 화면
---
1. 사용자는 카메라 혹은 갤러리 선택
![image](https://github.com/user-attachments/assets/fcfb8d1d-04ba-4a27-912d-674f728ebe8c)
![image](https://github.com/user-attachments/assets/02d59111-3cc1-4171-acfe-8cffdde9af23)
--
2.yolo가 인식한 가구 화면 & 빈 공간 시각화
![image](https://github.com/user-attachments/assets/04c430d2-85e3-49b3-8e0f-e9843a1ceb37)
![image](https://github.com/user-attachments/assets/96d46119-56e1-4c6e-bd4a-4dba8b2aba7d)
![image](https://github.com/user-attachments/assets/426cd8fe-3051-4814-9a18-39c4353363b1)
![image](https://github.com/user-attachments/assets/9d7ea061-f2b5-4ff4-aff7-e93e5652292f)
![image](https://github.com/user-attachments/assets/d40e9115-ac43-4808-9ff8-ac04f5dbab74)
![image](https://github.com/user-attachments/assets/8d77808c-dd02-49e0-bc6e-3e0f7d2a942c)
---
3. 2번의 순서를 합친 최종 UI 및 하단에 가구의 속성으로 GNN 기반 추천 가구들 시각화
![image](https://github.com/user-attachments/assets/aabf2d7a-f505-4bd1-8608-85386dc69d70)
![image](https://github.com/user-attachments/assets/02860a6d-ec93-4e55-bde6-674c62fb5aea)
![image](https://github.com/user-attachments/assets/4e1d243a-65c7-4063-91a4-912b52b1d13a)
---
**6. 현재 개발 진행 상황 및 개선점**
---
현재 5-3의 추천 가구 시각화 후, 드래그 기능은 거의 완성 된 상황
사용자는 추천 가구를 빈 공간에 직접 배치할 수 있도록 적용 가능할 상황
배치 작업 완료 후 결과 이미지를 다운로드 및 저장할 수 있는 기능 추가 개발 중

현재 문제점 및 개선점으로 보는, 빈공간의 중구난방 문제점으로는 현재의 학습된 yolov8은 가구 데이터셋이 생각보다 적어, 다양한 가구 종류가 포함된 학습용 데이터셋 확보는 완료했으며, 이 데이터셋으로 yolo 모델 재학습 예정.
이를 통해 실내 가구 탐지 정확도 향상 및 빈 공간 추청 정확도도 향상될 예정.
이에 따라서 실제 배치 가능한 위치에 최적화된 가구 추천이 가능할 것으로 보임.

향후 개발이 완료되면, 더욱 나아가 기존 가구의 색상, 형태와 조화를 고려해 추천하는 스타일 기반 추천, 채광 및 벽 색상과 여백 등을 반영해 맞춤형 가구를 제안하는 공간 분위기 기반 추천 시스템을 도입하여 더욱 강화할 예정입니다.

---
코드 다운로드 주소 --> https://drive.google.com/file/d/164A-ll-NeXT_1v7wEukhAVvMqQrWk4F2/view?usp=sharing
코드를 깃허브에 원래대로면 파일 형식으로 올리고 싶은데, 용량이 너무 커서 올라가지 않아서, 최대한 git 명령어나 깃허브 데스크탑과 같은 것으로 시도해봤으나, git명령어로 했다가 파일들이 대부분 날라가버리는 대참사를 겪어서, 구글 드라이브에 압축된 형태인 사이트로 넣게 되었습니다..
frontend/src/utils/detet.ts와 같은 파일을 보면 ip주소로 한글로 적었는데 그 부분만, 현재 있는 ip주소를 입력하시고, 핸드폰으로 구동시의 ip와 동일해야함.

[발표 임시 (1).pdf](https://github.com/user-attachments/files/20807088/1.pdf)
