# SAFE-X ML – Industrial Worker Safety Detection

This repository contains the trained YOLOv8 model developed for the SAFE-X project, an AI-powered industrial worker safety monitoring system.

## Model Information

- Model: YOLOv8
- Framework: Ultralytics
- Model weights: `best.pt`
- Model size: Approximately 6 MB

The trained weights are provided directly. Team members do not need to download the training dataset or retrain the model.

## Requirements

- Windows 10 or Windows 11
- Python 3.11 or 3.12
- Webcam (for live detection)
- Internet connection for initial package installation

## Windows Installation Guide

### 1. Install Python

Download Python from:

https://www.python.org/downloads/

During installation, enable **Add Python to PATH**.

Verify installation:

```powershell
python --version
pip --version
```

### 2. Download the Repository

Option A – Download ZIP:

1. Visit https://github.com/saintadamitrr-web/SAFE-X-ML
2. Click the green Code button.
3. Select Download ZIP.
4. Extract the downloaded ZIP file.
5. Open PowerShell inside the extracted SAFE-X-ML folder.

Option B – Clone using Git:

```powershell
git clone https://github.com/saintadamitrr-web/SAFE-X-ML.git
cd SAFE-X-ML
```

### 3. Create a Virtual Environment

```powershell
py -3.11 -m venv .venv
```

Activate it:

```powershell
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks script execution:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\.venv\Scripts\Activate.ps1
```

### 4. Install Dependencies

```powershell
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 5. Run the Trained Model

Live webcam detection:

```powershell
yolo predict model=best.pt source=0 show=True
```

Image detection:

```powershell
yolo predict model=best.pt source="image.jpg" show=True
```

Video detection:

```powershell
yolo predict model=best.pt source="video.mp4" show=True
```

Press Q to close the live detection window.

### 6. Verify Model Classes

To check whether the model loads and display its trained class names:

```powershell
python -c "from ultralytics import YOLO; model=YOLO('best.pt'); print(model.names)"
```

## Troubleshooting

**Error: 'yolo' is not recognized**

Make sure the virtual environment is activated and run:

```powershell
python -m pip install ultralytics
```

Then try the detection command again.

**Error: Python is not recognized**

Reinstall Python and enable Add Python to PATH.

**Webcam not detected**

Check that your webcam is connected and close other applications using it.

## Project Structure

```text
SAFE-X-ML/
├── best.pt
├── requirements.txt
└── README.md
```

## Notes

- No training dataset is required to run inference.
- CPU inference is supported.
- NVIDIA GPU acceleration can be configured separately using a compatible PyTorch CUDA installation.
- Actual detection performance depends on the hardware and environment.
- This project is intended for academic and research purposes and is not a certified industrial safety system.

## Repository

https://github.com/saintadamitrr-web/SAFE-X-ML
