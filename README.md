# YOLO Football Play Detection

This project utilizes the YOLO (You Only Look Once) model for detecting various football plays in images. The model is trained on a dataset specifically curated for this task and can predict bounding boxes around different objects in the scene.

## Usage

1. **Load the YOLOv8 model**:
   The YOLOv8 model can be loaded using the provided weights (`yolov8n.pt`).

2. **Train the Model**:
   Use the following command to train the model on your dataset. Ensure you have a correct YAML file that specifies the dataset paths and class information.

   ```python
   model.train(data='path/to/data.yaml', epochs=30, imgsz=640)
   ```

3. **Make Predictions**:
   To make predictions on a specific image, use the following command:

   ```python
   results = model.predict(source='path/to/image.jpg', save=True)
   ```

## Training the Model

The model is trained using a YAML configuration file that specifies the training dataset. Modify the `data` parameter in the training function to point to your dataset's YAML file.

```python
model.train(data='/kaggle/input/football-play-detect/data.yaml', epochs=30, imgsz=640)
```

## Displaying Predictions

You can visualize the predictions made by the YOLOv8 model using the provided function. This function reads the output directory and displays the images with bounding boxes around detected objects.

```python
display_images_with_predictions(output_dir)
```

## Plotting Class Distribution

To understand the distribution of predicted classes, use the provided function to plot a histogram.

```python
plot_class_histogram(results)
```

