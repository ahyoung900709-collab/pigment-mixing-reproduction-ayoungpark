# 1. 오픈소스 클론
git clone https://github.com/scrtwpns/pigment-mixing.git
cd pigment-mixing/core

# 2. 가상환경 생성 및 활성화
python -m venv venv
source venv/Scripts/activate  # Windows
# source venv/bin/activate    # macOS/Linux

# 3. 필수 라이브러리 설치
pip install numpy scipy matplotlib PyQt5 opencv-python

# 4. LUT(룩업테이블) 생성
python lut_builder.py
