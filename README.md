# **Real-Time PPE Detection and Verification in Surgical Environments**  
**Using YOLOv8 and Mediapipe**

![Demo](demo.gif)
![output_video](https://github.com/user-attachments/assets/cdc6c944-6c1c-470a-ad7c-d90b96b5539c)


## **Overview**
This project implements a **real-time computer vision system** to enhance safety in surgical environments by automatically detecting Personal Protective Equipment (PPE) and verifying correct placement on surgeons and medical staff.

**Key Features**:
- Detects 5 PPE classes: **Surgical Mask, Gloves, Hairnet/Cap, Protective Goggles, Surgical Suit**
- **YOLOv8n** for fast and accurate object detection
- **Mediapipe Face Mesh & Hands** for precise placement verification (e.g., mask covering nose/mouth)
- Real-time performance: **15–30 FPS** on standard laptops (CPU-only possible)
- Interactive **Streamlit** web demo with live alerts
- Fully open-source, zero-cost development (trained on free Google Colab)

## **Demo**
<img width="2515" height="1536" alt="output1" src="https://github.com/user-attachments/assets/4902fd2d-420d-42d0-8f93-cd0ac07d4a3d" />

[Watch Full Demo Video](https://youtu.be/kSj5AHVVrro) 

## **Quick Start**

### **1. Clone the Repository**
```bash
git clone https://github.com/your-username/ppe-detection-yolov8-mediapipe.git
cd ppe-detection-yolov8-mediapipe
```

### 2. Install Dependencies
```py
python -m venv venv
source venv/bin/activate    # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

**requirements.txt**:
```txt
ultralytics
mediapipe
opencv-python
streamlit
albumentations
torch
torchvision
```
### 3. Run Real-Time Detection (Webcam)
```py
python detect.py
```
- Opens webcam
- Displays bounding boxes, class labels, and compliance status
- Records 40-second video to output_video.mp4

### 4. Launch Streamlit Web Demo
```py
streamlit run app.py
```
- Opens browser with live feed and real-time alerts

### Project Structure
```
ppe-detection-yolov8-mediapipe/
├── detect.py              # Main real-time detection script
├── app.py                 # Streamlit web interface
├── data.yaml              # YOLOv8 dataset configuration
├── best.pt                # Trained YOLOv8n model weights
├── requirements.txt
├── runs/                  # Training logs & checkpoints
├── output_video.mp4       # Sample recorded output
└── README.md
```

### Performance
- mAP@50:95: ~0.85
- Inference Speed:
- Laptop CPU (i7): 15–20 FPS
- Entry-level GPU: 25–30+ FPS
- Jetson Nano: 12–15 FPS

- Model Size: 6.2 MB (highly deployable)

### Dataset
- Based on Roboflow's "health_care-fb23c" dataset
- Cleaned: Removed 550 empty labels → 477 valid images
- Augmented with Albumentations → 2,370 training images

### Future Work
- Add face shield & N95 classes
- Multi-person tracking
- Edge deployment (Raspberry Pi / Jetson)
- Sound + notification alerts
- Clinical validation in real operating rooms

### License
MIT License – Free to use, modify, and deploy.
Star the repo if you find it useful! ⭐


