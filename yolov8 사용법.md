# OMP 충돌 발생 시

정석은 OMP 충돌을 해결하는 것
- 환경 재구축 등

아래의 방법은 OMP 충돌을 무시 + 멀티프로세싱 비활성화 하는 것임

```bash
>>> set KMP_DUPLICATE_LIB_OK=TRUE
>>> set OMP_NUM_THREADS=1
>>> set MKL_NUM_THREADS=1
>>> yolo train model=yolov8n.pt data=data.yaml epochs=50 imgsz=640 batch=16 workers=0
```

# 환경 구축법
마지막 세번째 명령문은 requirments.txt가 있을 때 사용
```bash
>>> conda create -n yolov8_new python=3.9(해당하는 파이썬 버전 입력)
>>> conda activate yolov8_new
>>> pip install -r requirements.txt
```


# 모델 테스트 예시
```bash
yolo predict model=C:/Users/USER/Desktop/yolov8-main/yolov8-main/gkrltlfgdmsrj.v1i.yolov8.copy/runs/detect/train3/weights/best.pt source="C:/Users/USER/Desktop/yolov8/test_video.mp4" imgsz=640 save=True conf=0.5 show=True
```

첫 번째 파인튜닝
```bash
(yolov8_env) C:\Users\USER\Desktop\yolov8-main\yolov8-main\gkrltlfgdmsrj.v1i.yolov8.copy

>>> yolo train model=sajeon_haksup.pt data=data.yaml epochs=50 imgsz=640 batch=16 pretrained=True lr0=0.001
```

두 번째 파인튜닝
```bash
>>> yolo train model=sajeon_haksup.pt data=data.yaml epochs=50 imgsz=640 batch=16 pretrained=True lr0=0.001 freeze=10
```

세 번째 파인튜닝
```bash
(yolov8_env) C:\Users\USER\Desktop\yolov8-main\yolov8-main\gkrltlfgdmsrj.v1i.yolov8.copy1>

>>> yolo train model=sajeon_haksup2.pt data=data.yaml epochs=100 imgsz=640 batch=16 pretrained=True lr0=0.001 freeze=10
```