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

본 실습에서는 **Mixbox의 Python 버전(pymixbox)**을 이용하여
안료(Pigment) 기반 색상 혼합을 재현하였습니다.
python -m pip install --force-reinstall pymixbox
pip show pymixbox
