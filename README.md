# 생성 모델을 활용한 포트홀 탐지 성능 향상

##  📝 프로젝트 요약
도로 노면의 불량으로 인한 피해보상 신청 건수와 피해보상 금액이 매년 가파르게 증가하고 있음

또한, 포트홀 사고 역시 빈번히 발생하고 있으며 포트홀로 인한 사고 예방의 중요성이 대두되고 있음

도로 노면의 불량을 인식하기 위해서는 **충분한 데이터셋이 필요**하지만 데이터 수집에는 많은 시간과 비용이 소요됨

따라서, 본 연구는 **생성 모델**을 활용한 도로 노면 불량 **데이터 증강**과 **포트홀 탐지 성능 향상**을 목표로 함

포트홀 탐지 성능이 확보되면, 이를 서비스화 하는 것을 향후 연구로 설정함

---

##  📄 연구 계획
➡ 데이터 증강
- Stable Diffusion 활용한 포트홀 이미지 생성

- 라벨링 데이터셋 구축


➡ 포트홀 탐지
- YOLOv8 활용한 포트홀 탐지

- 데이터셋 증강에 따른 탐지 성능 비교

- 실제 도로 노면에서 모델 테스트


➡ 서비스 개발
- 포트홀 탐지 시 포트홀 이미지와 해당 위치 데이터 수집

- 네비게이션 UI 포트홀 정보 지도화 서비스

---

##  🔍 연구 결과
✅ 데이터 증강
- 로드뷰 포트홀 이미지 300장 수집

- Stable Diffusion 이용한 이미지 생성(+8)
<br><br><br>
<p align="center">
  <img src="https://github.com/junhjun/IN-ISP/assets/53384975/1dc31da2-6d7a-46c7-9395-410c186d9a35" width="600">
  <br><br><br>
  <img src="https://github.com/junhjun/IN-ISP/assets/53384975/1a92eda6-9783-4718-a976-6fc998ef0cf3" width="600">
</p>

<br>

<h3 align="center">
  → 이미지 생성을 통한 포트홀 다양성 증강
</h3>

<br><br>

✅ 포트홀 탐지
- 증강 데이터셋 이용한 학습

  - Data : Original 300 + Generated (600, 1200, 1800, 2400)
  - Model : YOLOv8 Object Detection | batch size = 16, epochs = 500, EarlyStopping(patience = 50)
  - Google Colab | GPU NVIDIA A100-SXM4-40GB

<br><br><br>

- 데이터셋에 따른 학습 결과 비교
<br><br><br>
<p align="center">
  <img src="https://github.com/junhjun/IN-ISP/assets/53384975/316d38be-0290-4e76-a569-6d28f60c8a11" width="700">
</p>

<br><br>

- 모델에 따른 테스트 결과 비교

  [Original 300] vs [Original 300 + Generated 2400]
<br><br><br>
<p align="center">
  <img src="https://github.com/junhjun/IN-ISP/assets/53384975/f3699f62-1b42-44f5-b417-25c47664c4bd" width="500">
</p>

<br>

<h3 align="center">
  → 데이터 확보를 통한 객체 탐지 정확도 향상
</h3>

<br><br>

- 비디오 탐지 성능 확인

  - Confidence 정도에 따른 비교 : [confidence.mp4](https://drive.google.com/file/d/116FtQL1Ya-4orasYh3C7JMvhsHe1hAav/view?usp=sharing)
  
  - 주행 속도에 따른 비교 : [drivingspeed.mp4](https://drive.google.com/file/d/1UOOkIs9g7GlItmGO9AnctT4j-BU6mNPA/view?usp=sharing)

<br><br>

❎ 서비스 개발
- ...

<br><br><br><br>

