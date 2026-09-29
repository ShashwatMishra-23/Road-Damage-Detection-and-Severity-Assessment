# Road Damage Detection and Severity Assessment

This project detects road damage from images and marks the damaged areas using a YOLO-based computer vision model.

## What it detects

The model is trained for four road damage classes:

- D00 - Longitudinal Crack
- D10 - Transverse Crack
- D20 - Alligator Crack
- D40 - Pothole

The project also gives an estimated severity level for detected damage.

## Files

`road_damage_detection.ipynb`  
Main notebook used for dataset preparation, training and evaluation.

`road_damage_image_test.ipynb`  
Testing notebook that lets you upload or drag and drop an image and displays the prediction directly in the notebook output.

`road_damage_yolo11n.pt`  
Trained YOLO model.

## Dataset

The project uses the RDD2022 India dataset and keeps the four damage categories required for this project.

[Link To Dataset](https://universe.roboflow.com/prakhar-kpb1v/rdd2022-india-il8ju/dataset/6)

## Setup

### 1. Create a virtual environment

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

### 2. Install PyTorch with CUDA support

For GPU training and inference:

```bash
python -m pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu130
```

### 3. Install the required packages

```bash
python -m pip install ultralytics pandas matplotlib pillow pyyaml jupyter ipykernel ipywidgets
```

### 4. Create the Jupyter kernel

Create the `Road Damage GPU` kernel so the notebook uses the virtual environment:

```bash
python -m ipykernel install --user --name road_damage_gpu --display-name "Road Damage GPU"
```

Open Jupyter Notebook and select:

**Kernel → Change Kernel → Road Damage GPU**

The kernel only needs to be created once.

### Using CPU instead of GPU

If you do not have an NVIDIA GPU, install the regular PyTorch version:

```bash
python -m pip install torch torchvision torchaudio
```

You can then run the notebooks using CPU.

## Running the model

### Training

Open `road_damage_detection.ipynb` and run the cells in order.

The notebook prepares the dataset, keeps the four required classes, trains the YOLO11n model and performs validation.

A CUDA-enabled GPU is recommended for training.

### Testing an image

Open `road_damage_image_test.ipynb`.

Select the `Road Damage GPU` kernel and run the notebook.

The notebook provides an upload box where an image can be uploaded or dragged and dropped.

The notebook will:

1. Run the trained model on the image.
2. Draw bounding boxes around detected damage.
3. Show the damage class and confidence.
4. Display the result directly in the notebook output.

Make sure `road_damage_yolo11n.pt` is placed in the project folder.

## Python packages

The main packages used in the project are:

```text
ultralytics
torch
torchvision
torchaudio
pandas
matplotlib
pillow
pyyaml
jupyter
ipykernel
ipywidgets
```

## Model

The trained model is based on YOLO11n and is saved as:

```text
road_damage_yolo11n.pt
```
