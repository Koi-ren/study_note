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
```결과
Results saved to runs\detect\train2
COMET INFO: ---------------------------------------------------------------------------------------
COMET INFO: Comet.ml Experiment Summary
COMET INFO: ---------------------------------------------------------------------------------------
COMET INFO:   Data:
COMET INFO:     display_summary_level : 1
COMET INFO:     name                  : usual_quokka_9193
COMET INFO:     url                   : https://www.comet.com/koi-ren/general/41336b4a53da4910b1611e63e48dea4f
COMET INFO:   Metrics [count] (min, max):
COMET INFO:     lr/pg0 [201]               : (1.463903699249797e-05, 0.0014258607334718116)
COMET INFO:     lr/pg1 [201]               : (1.463903699249797e-05, 0.0014258607334718116)
COMET INFO:     lr/pg2 [201]               : (1.463903699249797e-05, 0.0014258607334718116)
COMET INFO:     metrics/mAP50(B) [202]     : (0.9417, 0.98299)
COMET INFO:     metrics/mAP50-95(B) [202]  : (0.65176, 0.7609516864894117)
COMET INFO:     metrics/precision(B) [202] : (0.82733, 0.9613)
COMET INFO:     metrics/recall(B) [202]    : (0.87708, 0.99221)
COMET INFO:     model/GFLOPs               : 8.196
COMET INFO:     model/parameters           : 3011433
COMET INFO:     model/speed_PyTorch(ms)    : 2.277
COMET INFO:     train/box_loss [200]       : (0.73167, 1.21286)
COMET INFO:     train/cls_loss [200]       : (0.34671, 1.01378)
COMET INFO:     train/dfl_loss [200]       : (1.01523, 1.40688)
COMET INFO:     val/box_loss [200]         : (0.87668, 1.03711)
COMET INFO:     val/cls_loss [200]         : (0.36618, 0.66481)
COMET INFO:     val/dfl_loss [200]         : (1.042, 1.16293)
COMET INFO:   Others:
COMET INFO:     eval_batch_logging_interval  : 1
COMET INFO:     log_confusion_matrix_on_eval : False
COMET INFO:     log_image_predictions        : True
COMET INFO:     max_image_predictions        : 100
COMET INFO:   Parameters:
COMET INFO:     agnostic_nms    : False
COMET INFO:     amp             : True
COMET INFO:     augment         : False
COMET INFO:     auto_augment    : randaugment
COMET INFO:     batch           : 16
COMET INFO:     bgr             : 0.0
COMET INFO:     box             : 7.5
COMET INFO:     cache           : False
COMET INFO:     cfg             : None
COMET INFO:     classes         : None
COMET INFO:     close_mosaic    : 10
COMET INFO:     cls             : 0.5
COMET INFO:     conf            : None
COMET INFO:     copy_paste      : 0.0
COMET INFO:     copy_paste_mode : flip
COMET INFO:     cos_lr          : True
COMET INFO:     crop_fraction   : 1.0
COMET INFO:     data            : data.yaml
COMET INFO:     degrees         : 0.0
COMET INFO:     deterministic   : True
COMET INFO:     device          : None
COMET INFO:     dfl             : 1.5
COMET INFO:     dnn             : False
COMET INFO:     dropout         : 0.0
COMET INFO:     dynamic         : False
COMET INFO:     embed           : None
COMET INFO:     epochs          : 100
COMET INFO:     erasing         : 0.4
COMET INFO:     exist_ok        : False
COMET INFO:     fliplr          : 0.5
COMET INFO:     flipud          : 0.0
COMET INFO:     format          : torchscript
COMET INFO:     fraction        : 1.0
COMET INFO:     freeze          : 10
COMET INFO:     half            : False
COMET INFO:     hsv_h           : 0.015
COMET INFO:     hsv_s           : 0.7
COMET INFO:     hsv_v           : 0.4
COMET INFO:     imgsz           : 640
COMET INFO:     int8            : False
COMET INFO:     iou             : 0.7
COMET INFO:     keras           : False
COMET INFO:     kobj            : 1.0
COMET INFO:     line_width      : None
COMET INFO:     lr0             : 0.01
COMET INFO:     lrf             : 0.01
COMET INFO:     mask_ratio      : 4
COMET INFO:     max_det         : 300
COMET INFO:     mixup           : 0.0
COMET INFO:     mode            : train
COMET INFO:     model           : sajeon_haksup2.pt
COMET INFO:     momentum        : 0.937
COMET INFO:     mosaic          : 1.0
COMET INFO:     multi_scale     : False
COMET INFO:     name            : train2
COMET INFO:     nbs             : 64
COMET INFO:     nms             : False
COMET INFO:     opset           : None
COMET INFO:     optimize        : False
COMET INFO:     optimizer       : auto
COMET INFO:     overlap_mask    : True
COMET INFO:     patience        : 100
COMET INFO:     perspective     : 0.0
COMET INFO:     plots           : True
COMET INFO:     pose            : 12.0
COMET INFO:     pretrained      : True
COMET INFO:     profile         : False
COMET INFO:     project         : None
COMET INFO:     rect            : False
COMET INFO:     resume          : False
COMET INFO:     retina_masks    : False
COMET INFO:     save            : True
COMET INFO:     save_conf       : False
COMET INFO:     save_crop       : False
COMET INFO:     save_dir        : runs\detect\train2
COMET INFO:     save_frames     : False
COMET INFO:     save_hybrid     : False
COMET INFO:     save_json       : False
COMET INFO:     save_period     : -1
COMET INFO:     save_txt        : False
COMET INFO:     scale           : 0.5
COMET INFO:     seed            : 0
COMET INFO:     shear           : 0.0
COMET INFO:     show            : False
COMET INFO:     show_boxes      : True
COMET INFO:     show_conf       : True
COMET INFO:     show_labels     : True
COMET INFO:     simplify        : True
COMET INFO:     single_cls      : False
COMET INFO:     source          : None
COMET INFO:     split           : val
COMET INFO:     stream_buffer   : False
COMET INFO:     task            : detect
COMET INFO:     time            : None
COMET INFO:     tracker         : botsort.yaml
COMET INFO:     translate       : 0.1
COMET INFO:     val             : True
COMET INFO:     verbose         : True
COMET INFO:     vid_stride      : 1
COMET INFO:     visualize       : False
COMET INFO:     warmup_bias_lr  : 0.1
COMET INFO:     warmup_epochs   : 3.0
COMET INFO:     warmup_momentum : 0.8
COMET INFO:     weight_decay    : 0.0005
COMET INFO:     workers         : 8
COMET INFO:     workspace       : None
COMET INFO:   Uploads:
COMET INFO:     conda-environment-definition : 1
COMET INFO:     conda-info                   : 1
COMET INFO:     conda-specification          : 1
COMET INFO:     confusion-matrix             : 1
COMET INFO:     environment details          : 1
COMET INFO:     filename                     : 1
COMET INFO:     images                       : 20
COMET INFO:     installed packages           : 1
COMET INFO:     model-element                : 1 (5.97 MB)
COMET INFO:     source_code                  : 1 (17.63 KB)
COMET INFO:
COMET WARNING: To get all data logged automatically, import comet_ml before the following modules: torch.
COMET INFO: Please wait for assets to finish uploading (timeout is 10800 seconds)
COMET INFO: Still uploading 1 file(s), remaining 5.36 MB/5.97 MB
COMET INFO: Still uploading 1 asset(s), remaining 893.05 KB/5.97 MB, Throughput 305.81 KB/s, ETA ~3s
```

## 다섯 번쨰 하이퍼 파라미터 튜닝 (예정)

