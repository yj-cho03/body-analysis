## 프로젝트명
AI 기반 체형 분석 의류 추천 시스템

## 프로젝트 설명
본 프로젝트는 Raspberry Pi 카메라를 활용하여 사용자의 전신 이미지를 촬영하고,
OpenCV와 MediaPipe Pose를 이용하여 신체 관절 좌표를 자동으로 추출하는 체형 분석 시스템이다.

추출된 좌표 데이터는 JSON 형태로 변환되어 서버로 전송되며,
이를 기반으로 신체 길이 및 비율을 계산하여 체형 분석에 활용되도록 구현하였다.

---

## 담당 역할
- Raspberry Pi 카메라를 이용한 전신 이미지 촬영 기능 구현
- OpenCV + MediaPipe Pose 기반 33개 관절 좌표 추출
- 정면(front.json) 및 측면(side.json) 좌표 데이터 생성
- 상체·하체 길이 및 어깨·허리 비율 계산 로직 구현
- 분석 결과를 body_result.json 형태로 구조화
- 촬영 → 서버 전송 → 좌표 추출 → JSON 생성까지 전체 파이프라인 자동화 구현

---

## 기술 적용 방식
1. Raspberry Pi 카메라를 이용하여 사용자 전신 이미지 촬영 (정면, 측면)
2. 촬영된 이미지를 서버로 전송하여 분석 처리 수행
3. MediaPipe Pose를 활용하여 33개 신체 관절 좌표(x, y, z, visibility) 추출
4. 추출된 좌표 데이터를 JSON 형태(front.json, side.json)로 변환
5. 어깨 너비, 허리 너비, 상체 길이, 하체 길이 계산
6. 상체/하체 비율 및 어깨/허리 비율 계산
7. 결과 데이터를 body_result.json 형태로 생성
8. 분석 결과를 서버에 저장하여 추천 시스템에 활용

---

## 폴더 구조 설명
- backend: 서버 및 분석 처리 코드
- raspberry_pi: 이미지 촬영 및 서버 전송 코드
- body_data: 좌표 추출 및 신체 비율 계산 코드

---

## 주요 코드 설명
- pose.py: MediaPipe를 활용한 신체 관절 좌표 추출
- body_measure.py: 신체 길이 및 비율 계산
- capture_and_send.py: 이미지 촬영 및 서버 전송 처리

---

## 사용 기술
- Python
- OpenCV
- MediaPipe Pose
- Raspberry Pi
- JSON 데이터 처리
