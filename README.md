
# YoloV5 Museum Demo

This demo shows how to use YoloV5 for object detection in a museum. It covers setup, dataset download, and training.

## Features

- Google Colab integration
- YoloV5 setup
- Roboflow dataset management
- Training and inference scripts

## Requirements

- Python 3.x
- Roboflow API Key

## Usage

1. **Clone Repository**:
   ```bash
   git clone https://github.com/John-Wassef/YoloV5-Museum-Demo
   cd YoloV5-Museum-Demo
   ```

2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   pip install roboflow
   ```

3. **Run Notebook**: Open `YoloV5_Museum_Demo.ipynb` in Jupyter or Colab

   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/John-Wassef/YoloV5-Museum-Demo/blob/main/YoloV5_Museum_Demo.ipynb)

## Notebook Steps

1. **Clone YoloV5**:
   ```python
   !git clone https://github.com/ultralytics/yolov5
   %cd yolov5
   %pip install -qr requirements.txt roboflow
   ```

2. **Set Dataset Directory**:
   ```python
   os.environ['DATASET_DIRECTORY']="/content/datasets"
   ```

3. **Download Dataset**:
   ```python
   from roboflow import Roboflow
   rf = Roboflow(api_key="")
   project = rf.workspace("last-demo-nxjxv").project("last-demo-rplws")
   version = project.version(4)
   dataset = version.download("yolov5")
   ```

4. **Train Model**:
   ```python
   !python train.py --img 640 --batch 64 --epochs 30 --data /content/datasets/Last-Demo-4/data.yaml --weights yolov5s.pt --cache --patience 5
   ```

5. **Run Inference**:
   ```python
   !python detect.py --source /content/datasets/Last-Demo-4/images/test
   ```

## Contributing

Submit issues or pull requests for bugs or improvements.

