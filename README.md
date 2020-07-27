# DFDNet
Overview of our proposed method. It mainly contains two parts: (a) the off-line generation of multi-scale component dictionaries from large amounts of high-quality images which have diverse poses and expressions. K-means is adopted to generate K clusters for each component (i.e., left/right eyes, nose and mouth) on different feature scales. (b) The restoration process and dictionary feature transfer (DFT) block that are utilized to provide the reference details in a progressive manner. Here, DFT-i block takes the Scale-i component dictionaries for reference in the same feature level.
    
    

<img src="./Imgs/pipeline_a.png">
<p align="center">(a) Offline generation of multi-scale component dictionaries.</p>
<img src="./Imgs/pipeline_b.png">
<p align="center">(b) Architecture of our DFDNet for dictionary feature transfer.</p>


# Pre-train Models and dictionaries
Downloading from the following url and put them into ./.
- [BaiduNetDisk](https://pan.baidu.com/s/1K4fzjPiezVSMl5NjHoJCGQ) (s9ht)
- GoogleDrive: 
    - [DFDModel](https://drive.google.com/drive/folders/1778nIPPuFaUqiF-02APxhPvURRetN9r2?usp=sharing) 
    - [Vgg](https://drive.google.com/drive/folders/1778nIPPuFaUqiF-02APxhPvURRetN9r2?usp=sharing) 
    - [Dictionaries](https://drive.google.com/drive/folders/1iwQjHx23O1HVWJ0rtwos8OVZ3mIeCe8r?usp=sharing)


# Testing
1. Crop face from the whole image.
```bash
cd ./CropFace
python crop_face_dlib.py
```
(You can change the image path and save path in line 61~62)

2. Compute the facial landmarks.
```bash
cd ./FaceLandmarkDetection
python get_face_landmark.py
```
(You can change the image path and save path in line 17~18. This code is mainly borrowed from [this work](https://github.com/1adrianb/face-alignment))

3. Run the face restoration.
```bash
python test_FaceDict.py
```

# Some plausible restoration results on real low-quality images.
 <table  style="float:center" width=90%>
 <tr>
  <th><B>Input</B></th><th><B>Results</B></th>
 </tr>
 <tr>
  <td>
  <img src='./Imgs/RealLR/n000056_0060_01.png'>
  </td>
  <td>
   <img src='./Imgs/ShowResults/n000056_0060_01.png'>
  </td>
 </tr>
 <tr>
  <td>
  <img src='./Imgs/RealLR/n000067_0228_01.png'>
  </td>
  <td>
   <img src='./Imgs/ShowResults/n000067_0228_01.png'>
  </td>
 </tr>
 <tr>
  <td>
  <img src='./Imgs/RealLR/n000184_0094_01.png'>
  </td>
  <td>
   <img src='./Imgs/ShowResults/n000184_0094_01.png'>
  </td>
 </tr>
 <tr>
  <td>
  <img src='./Imgs/RealLR/n000262_0097_01.png'>
  </td>
  <td>
   <img src='./Imgs/ShowResults/n000262_0097_01.png'>
  </td>
 </tr>
 <tr>
  <td>
  <img src='./Imgs/RealLR/n000241_0132_04.png'>
  </td>
  <td>
   <img src='./Imgs/ShowResults/n000241_0132_04.png'>
  </td>
 </tr>
  
 </table>

# Citation

```
@InProceedings{Li_2020_ECCV,
author = {Li, Xiaoming and Chen, Chaofeng and Zhou, Shangchen and Lin, Xianhui, Zuo, Wangmeng and Zhang, Lei},
title = {Blind Face Restoration via Deep Multi-scale Component Dictionaries},
booktitle = {ECCV},
year = {2020}
}
```
```
This code is released only for educational usage (commercial usage please contact me).
```
