# UFMDet
UFMDet is a Fourier series-based object detection model, designed to detect objects of arbitrary shapes in complex environments. Unlike traditional object detection, UFMDet outputs a semantic equation constructed from the Fourier series of the target, providing a more precise and detailed description of the object. UFMDet is a unified Fourier-based framework that formulates arbitrary-shaped object detection as continuous curve regression in a shared frequency-domain space.

The key idea is to represent closed-shape and line-like objects within a single model, where line-like structures are treated as a constrained degenerate case of closed Fourier curves. As a result, UFMDet can simultaneously detect blob-like and line-like objects within a single image using a unified representation and prediction pipeline. To address parameterization ambiguity, we introduce an equivalence-aware alignment strategy that resolves traversal direction, phase shifts, and endpoint ordering, enabling supervision in the equivalence space and improving optimization stability.

Paper submition information:
```bibtex
@article{UFMDetbyLiujin,
    author  = "Jin Liu; Huan Li*, etc",
    title   = "UFMDet: Unified Fourier Multi-shape Detection for Blobs and Lines in Natural Scenes",
    year    = "January 9, 2026",
    journal = "IEEE Transactions on Pattern Analysis and Machine Intelligence",
}
```
You can contact us through:
- Tel,WeChat:13397188592
- QQEmail:41038331@qq.com

Thanks for everyone's contributions.

Project Start Date: October 2024.9
Repository Upload Date: January 2026.5.11

UFMDet Object Detection Demos
<div align="center">
  <img src="demos/coco2017/000000013729.jpg" width="32%" />
  <img src="demos/coco2017/000000014226.jpg" width="32%" />
  <img src="demos/coco2017/000000016451.jpg" width="25%" />

  <img src="demos/river-road/4lF7x2pBMz2NppLSRS8hzvwa7.jpg" width="32%" />
  <img src="demos/river-road/5ad136356a524126bd7eb5e93c34881c.png" width="32%" />
  <img src="demos/river-road/true (1).jpg" width="32%" />
  <img src="demos/river-road/validation_11.jpg" width="32%" />
  <img src="demos/river-road/9b2dd37e8c404baa94f50db87049719b.jpeg" width="32%" />
  <img src="demos/river-road/3923.jpg_wh860.jpg" width="32%" />

  <img src="demos/dota1.5-10terms/patches_P0000_84_0.jpg" width="32%" />
  <img src="demos/dota1.5-10terms/patches_P1067_1_0.jpg" width="32%" />
  <img src="demos/dota1.5-10terms/patches_P0064_116_0.jpg" width="32%" />
</div>
<div align="center">
  <img src="demos/cityscapes/4.4ld.png" width="48%" />
  <img src="demos/cityscapes/4.4ru.png" width="48%" />
</div>
snake from 2nd to 16-th fourior order
<div align="center">
  <img src="demos/snake/0c4d7639d4d9e53667390b10b1136fd1_ftn.png" width="48%" />
  <img src="demos/snake/0d6756b1e72bd55b3133f0eee3dfe401_ftn.png" width="48%" />
</div>

Dynamic Operation Demonstration of Object Fourier Harmonic Circles
<div align="center">
  <img src="demos/fourior-circles/harbor.gif" width="26%" />
  <img src="demos/fourior-circles/plane.gif" width="32%" />
</div>

### Inference Visualization
Below is a video demonstration of the model inference on the COCO 2017 dataset:
<video width="640" height="360" controls>
  <source src="https://liujin1975060601.github.io/yolov5-ft/demos/videos/road_person-cars-dog_20250206_00295546.mp4" type="video/mp4">
点击链接播放演示视频，请<a href="https://liujin1975060601.github.io/yolov5-ft/demos/videos/road_person-cars-dog_20250206_00295546.mp4">点击这里播放视频</a>。
</video>
<video width="640" height="360" controls>
  <source src="https://liujin1975060601.github.io/yolov5-ft/demos/videos/road-cars-s_20250205_23160389_20250205_23205007.mp4" type="video/mp4">
点击链接播放演示视频，请<a href="https://liujin1975060601.github.io/yolov5-ft/demos/videos/road-cars-s_20250205_23160389_20250205_23205007.mp4">点击这里播放视频</a>。
</video>

The UFMDet model supports more than 20 datasets, including:
coco2017,cityscapes,isAID,mstar,Chikusei,Landslide,dota1.5,hrsc2016,UCAS,infared,
snake,road+river,road_lines,remote_curves,TuSimple

### Instructions
- `train.py` starts training  
  (specify the training dataset `data`, model architecture `cfg`, and pre-trained weights `weights`).

- `val.py` starts validation  
  (specify model weights `weights` and dataset `data`).

- `detect.py` starts image or video detection  
  (specify model weights `weights` and the source folder path to be detected `source`).

