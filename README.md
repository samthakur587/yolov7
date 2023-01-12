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

# 4x4 grid image in README.md

<table>
  <tr>
    <td>
      <img src="https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2371_jpeg_jpg.rf.12162e15de98f7727a6eb73959ccadbf.jpg" width="256" height="256">
    </td>
    <td>
      <img src="https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2379_jpeg_jpg.rf.7323190d638f08476c5de9cb833cab05.jpg" width="256" height="256">
    </td>
    <td>
      <img src="https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2380_jpeg_jpg.rf.d443c2adf80f2ed4fc631a397187f1f2.jpg" width="256" height="256">
    </td>
    <td>
      <img src="https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2387_jpeg_jpg.rf.49c671cc255041888c34bb0f0c3d4018.jpg" width="256" height="256">
    </td>
  </tr>
  <tr>
    <td>
      <img src="https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2395_jpeg_jpg.rf.51fc3cbc72408d1d85eac556b2be6643.jpg" width="256" height="256">
    </td>
    <td>
      <img src="https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2423_jpeg_jpg.rf.39aca9cd118509b10f192b87e7ce9692.jpg" width="256" height="256">
    </td>
    <td>
      <img src="https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2434_jpeg_jpg.rf.91884b7faef7b7ef2f6d1b4a9f5156dc.jpg" width="256" height="256">
    </td>
    <td>
      <img src="https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2446_jpeg_jpg.rf.3aca192d35cd5a89a443c4f6932d9842.jpg" width="256" height="256">
    </td>
  </tr>
  <tr>
    <td>
      <img src="https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2448_jpeg_jpg.rf.d64214bb530655f321dde92529475458.jpg" width="256" height="256">
    </td>
    <td>
      <img src="https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2450_jpeg_jpg.rf.f4281c6909578c3d8042ac580f9c006d.jpg" width="256" height="256">
    </td>
    <td>
      <img src="https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2465_jpeg_jpg.rf.ffc005c4b0cc5ecae8e5b06fda23bdbb.jpg" width="256" height="256">
    </td>
    <td>
      <img src="https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2466_jpeg_jpg.rf.f199a14fb75e6d61214de954d3ad55e6.jpg" width="256" height="256">
    </td>
  </tr>
  <tr>
    <td>
      <img src="https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2468_jpeg_jpg.rf.c6cd976633535d0af9d098accc6a13e0.jpg" width="256" height="256">
    </td>
    <td>
      <img src="https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2470_jpeg_jpg.rf.2b5a5216a02ed3f818b04553de4fb7aa.jpg" width="256" height="256">
    </td>
    <td>
      <img src="https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2473_jpeg_jpg.rf.97405e1e2aee76cf48b99ed0a8d7b743.jpg" width="256" height="256">
    </td>
    <td>
      <img src="https://github.com/samthakur587/yolov7/blob/main/exp/IMG_2477_jpeg_jpg.rf.bb99d0a91aa3334482b50eb2466b50cd.jpg" width="256" height="256">
    </td>
  </tr>
</table>


# here the ![link](https://universe.roboflow.com/roboflow-100/aquarium-qlnqy) for dataset

# Use API to download dataset from roboflow

>!pip install roboflow

>from roboflow import Roboflow

>rf = Roboflow(api_key="FO51sqPkzf1OEgMmcptR")

>project = rf.workspace("roboflow-100").project("aquarium-qlnqy")

>dataset = project.version(2).download("yolov7")

![License]()

# ![LinkedIN](https://www.linkedin.com/in/samunder-singh-265508202/)
