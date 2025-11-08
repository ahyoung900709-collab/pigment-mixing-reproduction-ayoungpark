# 🎨 Practical Pigment Mixing for Digital Painting – 실행 재현 및 실습 보고서
**성균관대학교 스마트팩토리융합학과 / 박아영**  
오픈소스 분석 개인과제

---

## 🧩 1️⃣ 오픈소스 클론 및 환경 구성

```bash
# 1. 오픈소스 클론
git clone https://github.com/scrtwpns/pigment-mixing.git
cd pigment-mixing/core

# 2. 가상환경 생성 및 활성화
python -m venv venv
venv\Scripts\activate      # Windows
# source venv/bin/activate # macOS/Linux

# 3. 필수 라이브러리 설치
pip install numpy scipy matplotlib PyQt5 opencv-python

# 4. LUT(룩업테이블) 생성 (Kubelka–Munk 기반 색상 데이터 생성)
python lut_builder.py

본 실습에서는 Mixbox의 Python 버전(pymixbox)을 이용하여
안료(Pigment) 기반 색상 혼합을 재현하였습니다.

python -m pip install --force-reinstall pymixbox
pip show pymixbox

import mixbox

# 두 색상 (파랑, 노랑)
rgb1 = (0, 33, 133)
rgb2 = (252, 211, 0)
t = 0.5  # 혼합 비율

rgb_mix = mixbox.lerp(rgb1, rgb2, t)
print("혼합 결과 RGB:", rgb_mix)


실행 결과

✅ 혼합 결과 RGB: (41, 130, 57)
파랑(0,33,133) + 노랑(252,211,0) → 실제 회화처럼 녹색 계열 혼합
(Kubelka–Munk 이론 기반 Pigment 혼색 재현)

pigment-mixing-reproduction-ayoungpark
├─ images
│  ├─ install_pymixbox.png   # pip 설치 로그
│  └─ mix_result.png         # 혼합 결과 캡처
├─ README.md
└─ mix_test.py               # 실행 코드

환경요약
| 항목     | 내용                                                                                        |
| ------ | ----------------------------------------------------------------------------------------- |
| OS     | Windows 11                                                                                |
| Shell  | PowerShell                                                                                |
| Python | 3.12 (venv)                                                                               |
| 패키지    | pymixbox, numpy, matplotlib 등                                                             |
| 원저작    | Secret Weapons – [https://github.com/scrtwpns/mixbox](https://github.com/scrtwpns/mixbox) |
| 라이선스   | CC BY-NC 4.0 (비상업적 사용 허용)                                                                 |


5️⃣ 분석 요약

Mixbox는 Kubelka–Munk 방정식을 활용하여 색을 빛(RGB)이 아닌 **안료(Pigment)**로 모델링

디지털 회화, 조색, 화장품 컬러 예측 등 **감산 혼색(Subtractive Mixing)**을 정확히 재현 가능

단순 RGB 평균 혼합 대비 실제 물리적 혼색과 유사한 결과를 제공

본 실습에서는 pymixbox를 통해 Python 환경에서 실제 혼합 결과를 수치로 확인


---
📚 참고

원 논문: Practical Pigment Mixing for Digital Painting, ACM TOG (2021)

오픈소스: https://github.com/scrtwpns/mixbox

---

