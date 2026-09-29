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

`road_damage_colab.ipynb`  
Notebook for running the project in Google Colab with GPU.

`road_damage_detection.ipynb`  
Main notebook used for dataset preparation, training and evaluation.

`road_damage_image_test.ipynb`  
Testing notebook that lets you upload or drag and drop an image and displays the prediction directly in the notebook output.

`road_damage_yolo11n.pt`  
Trained YOLO model.

## Dataset

The project uses the RDD2022 India dataset and keeps the four damage categories required for this project.

## Running the model

### Training

Open `road_damage_detection.ipynb` and run the cells in order.

A CUDA-enabled GPU is recommended for training.

### Testing an image

Open `road_damage_image_test.ipynb`.

Select the `Road Damage GPU` kernel, run the notebook, and use the upload box to add a road image.

The notebook will:

1. Run the trained model on the image.
2. Draw bounding boxes around detected damage.
3. Show the damage class and confidence.
4. Display the result directly in the output.

## Python packages

```bash
pip install ultralytics pandas matplotlib pillow pyyaml ipywidgets
