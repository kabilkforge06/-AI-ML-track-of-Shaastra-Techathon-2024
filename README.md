![Shaastra Certificate](assets/shastra-certificate.png)

<!-- Rest of your README content below -->

# 🚦 AI/ML Challenge - Shaastra Techathon 2024
🚦 This project is a cutting-edge solution developed for Shaastra Techathon 2024, hosted by IIT Madras. It leverages Artificial Intelligence and Computer Vision techniques to automate traffic violation detection using CCTV feeds in real-time.

![Shaastra Techathon](https://img.shields.io/badge/Shaastra%20Techathon-2024-blue?style=flat-square)
![AI/ML](https://img.shields.io/badge/Domain-AI%2FML-green?style=flat-square)

## 📜 Certificate of Participation

I participated in the **AI/ML challenge track** at **Shaastra Techathon 2024**, organized by **IIT Madras**, where I explored real-world problem solving using AI technologies. This repository serves as a reflection of my journey, learning, and experimentation during the hackathon.

---

## 🎯 Challenge Theme

**Smart Traffic Violation Detection System**

> Design an AI-based system that can detect traffic violations like signal jumping, wrong-way driving, and lane-crossing using CCTV footage.

---

## 🧠 My Role & Learning Outcome

During the challenge, I:

- Explored the use of **YOLOv8** for real-time object detection.
- Experimented with **OpenCV** to process video frames from CCTV footage.
- Studied **license plate detection** using OCR (EasyOCR).
- Understood how to build a basic **AI pipeline** for surveillance systems.
- Learned how to structure a real-world AI/ML project under time constraints.

Even though this was not a final product submission, I gained valuable experience working with computer vision tools and frameworks. I also collaborated with mentors and peers to understand practical use cases of AI.

---
🏆 About the Hackathon
Event: Shaastra Techathon 2024

Track: AI/ML Challenge

Organized by: IIT Madras

Duration: 36 hours

Mode: Online/Hybrid

🙌 Acknowledgements
Thanks to the Shaastra Techathon 2024 team for hosting an engaging challenge.

Grateful to mentors and volunteers for insights and support.

## 🧪 Project Experiments (Prototype Code)

```python
import cv2
import easyocr
import torch

# Load a pre-trained YOLOv8 model
model = torch.hub.load('ultralytics/yolov5', 'yolov5s')  # Placeholder for yolov8

# Read video
cap = cv2.VideoCapture('sample_video.mp4')

while cap.isOpened():
    ret, frame = cap.read()
    if not ret:
        break

    # Inference
    results = model(frame)

    # Display
    results.render()
    cv2.imshow('YOLOv5 Inference', frame)

    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()

