# Lucas-Kanade-tracking-and-Correlation-Filters
This repository contains implementation of **sparse optical flow algorithm** proposed by Lucas and Kanade. LK Sparse Optical Flow can be used for motion estimation and object tracking. A more comprehensive implementation can be found on OpenCV [cv2.calcOpticalFlowPyrLK()](https://docs.opencv.org/3.4/dc/d6b/group__video__track.html#ga473e4b886d0bcc6b65831eb88ed93323).Please unzip data.zip and then follow the instructions below.
## Lucas Kanade Tracking with one single template  
The "vanilla" algorithm for tracking. Detailed derivation can be referred to [Lucas-Kanade 20 Years On: A Unifying Framework](https://www.ri.cmu.edu/pub_files/pub3/baker_simon_2002_3/baker_simon_2002_3.pdf)   
**Files included:**     
/data/carseq.npy  
/src/LucasKanade.py  
/src/testCarSequence.py  
**Run**
```
python testCarSequence.py
```
**Sample results**  
<img src="https://github.com/ziliHarvey/Lucas-Kanade-tracking-and-Correlation-Filters/raw/master/result/tracking_with_one_single_template/Figure_1.png" width=30% height=30%>
<img src="https://github.com/ziliHarvey/Lucas-Kanade-tracking-and-Correlation-Filters/raw/master/result/tracking_with_one_single_template/Figure_2.png" width=30% height=30%>
<img src="https://github.com/ziliHarvey/Lucas-Kanade-tracking-and-Correlation-Filters/raw/master/result/tracking_with_one_single_template/Figure_3.png" width=30% height=30%>  
/src/carseqrects.npy stores the vertices coordinates of bounding box in each frame.  
## Lucas Kanade Tracking with template correction  
The upgraded version of the first algorithm, which mitigates template drifting problem. Detailed derivation can be referred to [The Template Update Problem](https://www.ri.cmu.edu/publications/the-template-update-problem/)  
**FIles included:**  
/data/carseq.npy  
/src/LucasKanade.py  
/src/TemplateCorrection.py  
/src/testCarSequenceWithTemplateCorrection.py  
**Run**
```
python testCarSequenceWithTemplateCorrection.py
```
**Sample results**  
Blue bbox: with template correction | Red bbox: without template correction  
<img src="https://github.com/ziliHarvey/Lucas-Kanade-tracking-and-Correlation-Filters/raw/master/result/tracking_with_template_correction/Figure_1.png" width=30% height=30%>
<img src="https://github.com/ziliHarvey/Lucas-Kanade-tracking-and-Correlation-Filters/raw/master/result/tracking_with_template_correction/Figure_2.png" width=30% height=30%>
<img src="https://github.com/ziliHarvey/Lucas-Kanade-tracking-and-Correlation-Filters/raw/master/result/tracking_with_template_correction/Figure_3.png" width=30% height=30%>
## Lucas Kanade Tracking with appearance basis  
The former 2 algorithms may not suffice for real life challenges with drastic appearance variance. Through analyzing historical data collected, we can use an eigen-space approach to produce a principal template at each frame.  
**Files included:**  
/data/sylvseq.npy  
/data/sylvbbases.npy  
/src/LucasKanade.py
/src/TemplateCorrection.py  
/src/LucasKanadeBasis.py  
/src/testSylvSequence.py  
**Run**
```
python testSylvSequence.py
```
**Sample results**  
Blue bbox: with appearance bases | Red bbox: without appearance bases  
<img src="https://github.com/ziliHarvey/Lucas-Kanade-tracking-and-Correlation-Filters/raw/master/result/tracking_with_appearance_basis/Figure_1.png" width=30% height=30%>
<img src="https://github.com/ziliHarvey/Lucas-Kanade-tracking-and-Correlation-Filters/raw/master/result/tracking_with_appearance_basis/Figure_3.png" width=30% height=30%>
<img src="https://github.com/ziliHarvey/Lucas-Kanade-tracking-and-Correlation-Filters/raw/master/result/tracking_with_appearance_basis/Figure_5.png" width=30% height=30%>
## Lucas Kanade Tracking with dominant affine motion  
This algorithm works on non-stationary camera video  
**Files included**  
/data/aerialseq.npy  
/src/LucasKanadeAffine.py  
/src/SubtractDominantMotion.py  
/src/InverseCompositionAffine.py  
/src/testAerialSequence.py  
**Run**
```
python testAerialSequence.py
```
**Sample results**  
<img src="https://github.com/ziliHarvey/Lucas-Kanade-tracking-and-Correlation-Filters/raw/master/result/tracking_with_dorminant_affine_motion/Figure_1.png" width=30% height=30%>
<img src="https://github.com/ziliHarvey/Lucas-Kanade-tracking-and-Correlation-Filters/raw/master/result/tracking_with_dorminant_affine_motion/Figure_3.png" width=30% height=30%>
<img src="https://github.com/ziliHarvey/Lucas-Kanade-tracking-and-Correlation-Filters/raw/master/result/tracking_with_dorminant_affine_motion/Figure_4.png" width=30% height=30%>
## Correlation Filters  
The paper of correlation filters can be found here[Visual Object Tracking using Adaptive Correlation Filters](http://www.cs.colostate.edu/~vision/publications/bolme_cvpr10.pdf)  
**Files included**   
/src/Corr-Filters/lena.npy  
/src/Corr-FIlters/example.py  
**Run**  
```
python example.py
```
**Sample results**  
<img src="https://github.com/ziliHarvey/Lucas-Kanade-tracking-and-Correlation-Filters/raw/master/result/tracking_with_correlation_filters/Figure_1.png" width=40% height=40%>
<img src="https://github.com/ziliHarvey/Lucas-Kanade-tracking-and-Correlation-Filters/raw/master/result/tracking_with_correlation_filters/Figure_9.png" width=40% height=40%>
