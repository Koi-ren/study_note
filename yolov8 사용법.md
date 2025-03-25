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
yolo predict model=C:/Users/USER/Desktop/yolov8-main/yolov8-main/gkrltlfgdmsrj.v1i.yolov8.copy1/runs/detect/train/weights/best.pt source="C:/Users/USER/Desktop/yolov8-main/yolov8-main/gkrltlfgdmsrj.v1i.yolov8.copy1/test_video_0.mp4" imgsz=640 save=True conf=0.5 show=True
```

## 첫 번째 모델
```bash
(yolov8_env) C:\Users\USER\Desktop\yolov8-main\yolov8-main\gkrltlfgdmsrj.v1i.yolov8.copy

>>> yolo train model=sajeon_haksup.pt data=data.yaml epochs=50 imgsz=640 batch=16 pretrained=True lr0=0.001
```

##  두 번째 모델
```bash
>>> yolo train model=sajeon_haksup.pt data=data.yaml epochs=50 imgsz=640 batch=16 pretrained=True lr0=0.001 freeze=10
```

## 세 번째 파인튜닝
- 소요시간 : 30m 21s
- 정확도 현저히 떨어짐
- - 시도 방안 : 기존 data 와 merge 를 통해 fine tuning
- 학습 결과 : 기존 대비 성능 30% 증가
```bash
(yolov8_env) C:\Users\USER\Desktop\yolov8-main\yolov8-main\gkrltlfgdmsrj.v1i.yolov8.copy1>

>>> yolo train model=sajeon_haksup2.pt data=data.yaml epochs=100 imgsz=640 batch=16 pretrained=True lr0=0.001 freeze=10
```

## 네 번째 하이퍼 파라미터 튜닝
- 정확도 범위 : 70 ~ 90%
- 정확도 자체의 정밀도는 증가했으나 학교 출석에 사용될 정도로 정밀하지는 않음
- 따라서 하이퍼 파라미터 튜닝 진행 : 
	- lr0=0.001 $\rightarrow$ 0.01 (학습률을 높여 혹시 모를 경사 하강시 발생할 최소 오차 방지)
	- cor_lr=False $\rightarrow$ cor_lr=True (코사인 학습률 스켈쥴러 활성화 통해 학습률을 부드럽게 감소)
```bash
yolo train model=sajeon_haksup2.pt data=data.yaml epochs=100 imgsz=640 batch=16 pretrained=True lr0=0.01 freeze=10 cos_lr=True
```

## 다섯 번쨰 하이퍼 파라미터 튜닝 (예정)

