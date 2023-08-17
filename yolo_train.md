## Train yolov5 with sample dataset
    train.py --img-size 640 --batch-size 16 --epochs 50 --data data/coco128.yaml --cfg models/yolov5s.yaml --weights yolov5s.pt

## my crack detection labeling and training 
    python train.py --img 640 --batch 16 --epochs 50 --data data/data.yaml --cfg models/yolov5s.yaml --weights yolov5s.pt
