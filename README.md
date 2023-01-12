## yolov7 on custom dataset
The project aims to train the YOLOv7 object detection model on a custom dataset of aquarium images
. The dataset includes a diverse set of images of different aquarium setups, fish, and other aquatic creatures

>this project i trained yolov7 on 100 epochs and used the yolov7.pt pretrained weights and got the following mAPs:

![image](https://github.com/samthakur587/yolov7/blob/main/Results_100_b45d3073555eec4687ee.png)

## Performance 

MS COCO

| Model | Test Size | AP<sup>test</sup> | AP<sub>50</sub><sup>test</sup> | AP<sub>75</sub><sup>test</sup> | batch 1 fps | batch 32 average time |
| :-- | :-: | :-: | :-: | :-: | :-: | :-: |
| [**YOLOv7**](https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7.pt) | 640 | **51.4%** | **69.7%** | **55.9%** | 161 *fps* | 2.8 *ms* |
| [**YOLOv7-X**](https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7x.pt) | 640 | **53.1%** | **71.2%** | **57.8%** | 114 *fps* | 4.3 *ms* |
|  |  |  |  |  |  |  |
| [**YOLOv7-W6**](https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7-w6.pt) | 1280 | **54.9%** | **72.6%** | **60.1%** | 84 *fps* | 7.6 *ms* |
| [**YOLOv7-E6**](https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7-e6.pt) | 1280 | **56.0%** | **73.5%** | **61.2%** | 56 *fps* | 12.3 *ms* |
| [**YOLOv7-D6**](https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7-d6.pt) | 1280 | **56.6%** | **74.0%** | **61.8%** | 44 *fps* | 15.0 *ms* |
| [**YOLOv7-E6E**](https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7-e6e.pt) | 1280 | **56.8%** | **74.4%** | **62.1%** | 36 *fps* | 18.7 *ms* |

#for traing in shell

>!python train.py --workers 1 --device 0 --batch-size 16 --epochs 100 --img 640 640 --data /content/drive/MyDrive/aquarium_dataset/data.yaml --hyp data/hyp.scratch.custom.yaml --name yolov7-custom --weights yolov7.pt

#for detecting 

>!python detect.py --weights /content/drive/MyDrive/yolov7/runs/train/yolov7-custom2/weights/best.pt --conf 0.2 --img-size 640 --source /content/drive/MyDrive/aquarium_dataset/test/images/ 

#detection results :

![image](https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2289_jpeg_jpg.rf.e512a8d7e72d4a33c5667d2a0685ef7f.jpg)  
![image](https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2301_jpeg_jpg.rf.822c0a62daa53448f5e66fadb2b15b85.jpg)
![image](https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2319_jpeg_jpg.rf.69bba80dec0a0d4866c4037b3a12dcff.jpg)
![image](https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2347_jpeg_jpg.rf.cc26b11c425d65a90061fabb993cabab.jpg)
![image](https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2380_jpeg_jpg.rf.d443c2adf80f2ed4fc631a397187f1f2.jpg)

here the ![link](https://universe.roboflow.com/roboflow-100/aquarium-qlnqy)

![License]()

![LinkedIN](https://www.linkedin.com/in/samunder-singh-265508202/)
