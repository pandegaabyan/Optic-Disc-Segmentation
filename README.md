# Exploration and Comparative Study of Optic Disc Segmentation on Fundus Images

---

Imam Syahrizal, Izzun Nafis Ibadik, Pandega Abyan Zumarsyah

imamsyahrizal@mail.ugm.ac.id, izzunnafis2018@mail.ugm.ac.id, pandegaabyan@mail.ugm.ac.id

Department of Electrical Engineering and Information Technology, Universitas Gadjah Mada

---

Fundus image analysis is valuable for detecting various eye diseases such as glaucoma and retinopathy. This study explores several methods to achieve optimal segmentation results: region segmentation with GrowCut, dynamic thresholding and GrabCut, Random Forest, and UNet-MobileNetV2. These methods were evaluated using three datasets: ORIGA, DRIONS-DB, and RIM-ONE v3.

The UNet-MobileNetV2 model delivered excellent results across all three datasets. The Random Forest model also performed segmentation on all datasets but did not yield satisfactory results on the RIM-ONE v3 dataset. In contrast, methods 1 and 2 produced good results only when applied to the local dataset. Without parameter adjustments, these methods struggled to match the performance of the UNet-MobileNetV2 model.

---

This program segments the optic disc in fundus images using various datasets and methods.

### Dataset
- **Dataset 1 (ORIGA: [source](https://drive.google.com/drive/u/1/folders/1Y2HpGf74_K5NYS0Fn4zMSMhOzLA7K0_l))**: Contains 100 fundus images with a resolution of 3072x2048 pixels. Ground truth is provided as .mat files containing optic disc and optic cup region information.
- **Dataset 2 (DRIONS-DB)**: Contains 110 fundus images with a resolution of 600x400 pixels. 23% of the images are from glaucoma patients, while the remaining 77% are from ocular hypertension patients.
- **Dataset 3 (RIM-ONE r3)**: Contains 159 fundus images. These images are represented as horizontally arranged stereo images with annotations for the left optic disc.

### Methods
- **Method 1**: Preprocessing => Blood Vessel Removal => Circular Hough Transform => GrowCut
- **Method 2**: Four interrelated methods utilizing Thresholding, Grabcut, and Fit-Ellipse
- **Method 3**: Machine Learning with a Random Forest model for segmentation
- **Method 4**: Deep Learning based on UNet architecture with a MobileNetV2 model implemented using PyTorch

### Video Explanation

https://youtu.be/0XucamfgYRE
