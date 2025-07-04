# Toilet Rim Segmentation Model

This project features a deep learning model for toilet rim detection and measurement. It is designed for applications in smart bathrooms, robotic cleaning, home automation, and object-aware sanitation devices.

## How to run the code

To Train your own model on your own set of images, you need to follow these steps:

download and run the file named: [Internship_Toilet_detection.ipynb](Internship_Toilet_detection.ipynb) (NOTE: make sure to put the correct image path.)

It will create your very own model to predict the mask on the given toilet image and print the masked image to visualize the rim created.

## Features

The model offers the following key functionalities:

* **Rim Detection (Open Toilet)**: Segments both the inner and outer toilet rims as distinct ring-like structures.
* **Lid Detection (Closed Toilet)**: Identifies the full lid as a single object when the toilet is closed.
* **Distance Measurements**: Computes distances from the center of the toilet to the midpoint of the bottom edge and the midpoint of the right edge, for both the inner and outer rims.
* **Robustness**: Handles various toilet shapes (round, oval, square) and different lighting conditions effectively.
* **Fine-tuning**: Can be fine-tuned using images with red markings.

## Model Overview

This is a semantic segmentation model built using deep learning techniques (e.g., UNet or Segmentation Models). It has been fine-tuned on toilet datasets that were manually marked with red overlays.

## Visual Examples

### Open Toilet – Inner and Outer Rim Segmentation

**Raw Image and Predicted Mask**

![Output](Output.png)

### Distance Measurement Output

**Measured Distances:**
* **Center:** (522, 511)
* **Angle:** 88.50306701660156
* **First Bottom Point:** (942, 522)
* **Last Bottom Point:** (1037, 524)
* **First Right Point:** (530, 211)
* **Last Right Point:** (533, 91) 

## Technical Details

* **Framework**: PyTorch 
* **Model Type**: UNet / DeepLabV3+ / Custom Encoder 
* **Input Size**: 256x256 (internally resized) 
* **Output**: Binary mask 
* **Inference Speed**: Approximately 20ms per image (on GPU) 

## Training Notes

The model was initially trained on a combination of synthetic and real toilet image datasets. These datasets featured clear rim/lid boundaries and red elliptical markings for fine-tuning. The final fine-tuning process involved manually annotated red-marked masks.

Strict HSV thresholds are employed for red mask extraction:
```python
lower_red2 = np.array([0, 100, 100])
upper_red2 = np.array([10, 255, 255])
```

## Author

**Heet Savaliya**
B.Tech Computer Engineering
Pandit Deendayal Energy University

  * **LinkedIn**: [https://www.linkedin.com/in/heet-savaliya-03b863252/](https://www.google.com/search?q=https://www.linkedin.com/in/heet-savaliya-03b863252/)
  * **Email**: savaliyaheet19@gmail.com

## License

This project is released under the [MIT License](https://opensource.org/licenses/MIT). You are free to use, modify, and build upon this work.
