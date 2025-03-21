import comet_ml  # 먼저 임포트
import torch
import os

# OpenMP 충돌 방지
os.environ["KMP_DUPLICATE_LIB_OK"] = "TRUE"

# 작업 디렉토리 변경
%cd C:/Users/USER/Desktop/yolov8/kdfk-a-mekfjaf.v3i.yolov8

# 학습 명령어 (workers=0으로 설정)
!yolo task=detect mode=train model=yolov8n.pt data=data.yaml epochs=25 imgsz=800 plots=True device=0 half=True workers=0