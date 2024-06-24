# 112-2-DL_Final_project

## 數據配置文件
  
有關模型的配置文件  
/cfg/training/PRB-FPN-CSP.yaml  
/cfg/training/yolov7_.yaml  
/cfg/training/yolov7x_.yaml  
  
數據集的配置文件  
/data/coco_.yaml  
  
  
## Training
Single GPU training  
  
``` shell
# train yolov7 models
python train.py --weights weights/yolov7.pt --cfg cfg/training/yolov7_.yaml --data data/coco_.yaml --device 0 --batch-size 32 --epoch 10

# train yolov7x models
python train.py --weights weights/yolov7x.pt --cfg cfg/training/yolov7x_.yaml --data data/coco_.yaml --device 0 --batch-size 32 --epoch 10

# train PRB-FPN-CSP models
python train.py --weights weights/prb.pt --cfg cfg/training/PRB-FPN-CSP.yaml --data data/coco_.yaml --device 0 --batch-size 24 --epoch 5
```

訓練結果會在:  
/runs/train/

## 相關參數

``` shell
--weights weights/yolov7.pt           # 預訓練權重
--cfg cfg/training/yolov7_.yaml       # 模型配置文件
--data data/coco_.yaml                # 數據配置文件
--device 0                            # GPU/CPU訓練，若2塊GPU，為0,1；若1塊，則0；若CPU，則cpu
--batch-size 32                       # batch size
--epoch 10                            # epoch 
```
更多的參數可以參考train.py文件



## Inference

On video:
``` shell
python detect.py --weights yolov7.pt --conf 0.25 --img-size 640 --source myvideo.mp4
```

On image:
``` shell
python detect.py --weights yolov7.pt --conf 0.25 --img-size 640 --source myimg.jpg
```



## Acknowledgements

<details><summary> <b>Expand</b> </summary>

* [https://github.com/AlexeyAB/darknet](https://github.com/AlexeyAB/darknet)
* [https://github.com/WongKinYiu/yolor](https://github.com/WongKinYiu/yolor)
* [https://github.com/WongKinYiu/PyTorch_YOLOv4](https://github.com/WongKinYiu/PyTorch_YOLOv4)
* [https://github.com/WongKinYiu/ScaledYOLOv4](https://github.com/WongKinYiu/ScaledYOLOv4)
* [https://github.com/Megvii-BaseDetection/YOLOX](https://github.com/Megvii-BaseDetection/YOLOX)
* [https://github.com/ultralytics/yolov3](https://github.com/ultralytics/yolov3)
* [https://github.com/ultralytics/yolov5](https://github.com/ultralytics/yolov5)
* [https://github.com/DingXiaoH/RepVGG](https://github.com/DingXiaoH/RepVGG)
* [https://github.com/JUGGHM/OREPA_CVPR2022](https://github.com/JUGGHM/OREPA_CVPR2022)
* [https://github.com/TexasInstruments/edgeai-yolov5/tree/yolo-pose](https://github.com/TexasInstruments/edgeai-yolov5/tree/yolo-pose)

</details>
