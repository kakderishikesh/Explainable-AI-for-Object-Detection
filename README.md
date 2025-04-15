# Explainable AI for Object Detection in Autonomous Driving

A project exploring object detection models for autonomous driving with a focus on explainability using Grad-CAM and Saliency Maps.

## Project Overview

This project aims to compare state-of-the-art object detection models used in autonomous vehicles and apply **Explainable AI (XAI)** techniques to understand their decision-making processes. We evaluate each model’s performance using metrics like **Mean Average Precision (mAP)** and **Intersection over Union (IoU)**, while also analyzing their visual explanations.

📁 Dataset: [Udacity Self-Driving Car Dataset (COCO Format)](https://public.roboflow.com/object-detection/self-driving-car/3)  
📊 Number of Classes: 12  
🖼️ Input Size: 512x512 images

---

## Object Detection Models

We implemented and trained the following models:

1. **Faster R-CNN**  
   - Two-stage detector  
   - High accuracy (mAP: 0.78, IoU: 0.84)  
   - Best suited for precision-critical applications  

2. **YOLOv8**  
   - Real-time single-stage detector  
   - Efficient and balanced (mAP: 0.688, IoU: 0.69)  
   - Best tradeoff between speed and accuracy  

3. **RetinaNet**  
   - One-stage detector with Focal Loss  
   - Handles class imbalance well (mAP: 0.65, IoU: 0.56)  

4. **Single Shot Detector (SSD)**  
   - Fastest but least accurate (mAP: 0.09, IoU: 0.07)  
   - Demonstrated limitations in precision

---

## 🧪 Evaluation Metrics

- **Mean Average Precision (mAP)**: Measures detection precision across IoU thresholds  
- **Intersection over Union (IoU)**: Evaluates overlap between predicted and ground truth bounding boxes

---

## 🔍 Explainability Techniques

1. **Grad-CAM**: Generates heatmaps showing which parts of the image influence decisions  
2. **Saliency Maps**: Highlights input pixels most critical to the model’s prediction

Each model was visualized using both techniques, revealing differences in focus and interpretability:
- *Faster R-CNN*: High precision and narrow focus on objects
- *YOLOv8*: Broader context awareness
- *SSD*: Scattered and noisy attention patterns

---

## Results Summary

| Model         | mAP   | IoU   | Training Time | Params (Trainable) | Architecture      |
|---------------|-------|-------|----------------|---------------------|-------------------|
| Faster R-CNN  | 0.78  | 0.84  | 10 hrs (12 ep) | 41M                 | Two-Stage         |
| YOLOv8        | 0.688 | 0.69  | 5 hrs (20 ep)  | 30M                 | Single-Stage      |
| RetinaNet     | 0.65  | 0.56  | 16 hrs (12 ep) | 35M                 | Single-Stage      |
| SSD           | 0.09  | 0.07  | 1.2 hrs (12 ep)| 25M                 | Single-Stage      |

---

## Challenges Faced

- Adapting pre-trained models to custom datasets
- Compatibility issues in visualizing XAI outputs (especially for YOLOv8 and RetinaNet)
- SSD and DETR struggled with convergence and accuracy
- Conversion and preprocessing of dataset annotations into COCO-compatible formats

---

## Team

- **Rishikesh Kakde**
- **Ritika Shrivastava**  
- **Saransh Singh**  

> [Read the full final report here.](https://github.com/kakderishikesh/Explainable-AI-for-Object-Detection/blob/main/Final%20Report.pdf)

---

## Conclusion

This project highlights the importance of **model interpretability** in critical domains like autonomous driving. We demonstrate how explainable AI tools help identify model weaknesses, improve debugging, and build trust in AI systems. For safety-critical systems, a hybrid architecture combining YOLOv8 for real-time detection and Faster R-CNN for sensitive cases could be a practical solution.
