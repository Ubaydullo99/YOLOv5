# For Windows
## Train yolov5 with sample dataset
    train.py --img-size 640 --batch-size 16 --epochs 50 --data data/coco128.yaml --cfg models/yolov5s.yaml --weights yolov5s.pt

## my crack detection labeling and training 
    python train.py --img 640 --batch 16 --epochs 50 --data data/data.yaml --cfg models/yolov5s.yaml --weights yolov5s.pt
    python train.py --img-size 1280 --batch 16 --epochs 50 --data data/data.yaml --cfg models/yolov5s.yaml --weights yolov5s.p


    # data.yaml: bash
    train: dataset/images  # Path to your training images
    val: dataset/images  # Path to your validation images
    test: dataset/images  # Path to your test images
    nc: 1  # Number of classes (assuming you are detecting one class, "crack")
    names:
      0: crack  # Class names

    # in yolov5s.yaml
    nc: 1 # number of classes

    


## detect using my created best.pt weights
    python detect.py --weights ./runs/train/exp3/weights/best.pt --img-size 640 --conf 0.25 --source ../datasets/coco128/images/train2017/000000000404.jpg
    
    # for fixing issues:
    pip install -r requirements.txt coremltools onnx onnx-simplifier onnxruntime openvino-dev tensorflow-cpu
    
    # detect with onnx format 
    python detect.py --weights ./runs/train/exp3/weights/best.onnx --img-size 640 --conf 0.25 --source ../datasets/coco128/images/train2017/000000000064.jpg
    



## Changing onnx file to dlc with snpe

    # Sample
    snpe-onnx-to-dlc -i input_model.onnx -o output_model.dlc

- opt/qcom/aistack

