# iiith_internship


# Internship Assignment 1

- In this assignment, I used a YOLO model to perform object detection on an image.  
- The model was able to identify objects like bus and people, and displayed bounding boxes with confidence scores.  
- This confirms that the detection setup and environment are working correctly.  
- This completes my first task of the internship.

# Internship Assignment2 
- Performed object detection on multiple images.
- Also performed segmentation on the same images.
- Stored outputs in day2 folders.


# Internship Assignment 3

In this task, I used a video for object detection.
- I converted the video into image frames at 30 frames per second using FFmpeg, then processed all frames with the YOLO model to detect and segment objects.
- Finally, I combined the processed images back into a video at 30 fps.
- This helped me understand how to apply YOLO on video data and work with the complete frame-to-video workflow.


# Internship Assignment 4

In this task, I selected a real-life computer vision problem and created a custom dataset to train a YOLO model from scratch.
The chosen application was Milk Level Detection, where the system identifies the milk level during boiling and classifies it into three stages:

- Milk_Low

- Milk_High

- Milk_Overflow

✔ Dataset Preparation

I collected my own 2-minute video showing different milk levels, backgrounds, and lighting conditions.

To increase variety, I also took a few milk overflow clips from YouTube.

Using Label Studio, I manually annotated around 300 images with the three classes.

Later, I split the dataset into train (70%), validation (20%), and test (10%) sets.

✔ Model Selection and Training

I used YOLOv8s for this task because it is fast, accurate, and performs well on small custom datasets.

The model was trained locally on my NVIDIA RTX 3050 Laptop GPU.

Training was done for 40 epochs with these hyperparameters:

imgsz = 640

batch = 8

augmentations = default YOLO augment

device = 0 (GPU)

✔ Performance and Metrics

After training, the model achieved the following results:

Precision: 87.4%

Recall: 93.2%

mAP50: 93.2%

mAP50–95: 75.3%

Class-wise performance:

Milk_Low: 98%

Milk_High: 82%

Milk_Overflow: 99%

✔ Observations and Issues

The model performed extremely well for Low and Overflow classes.

However, it sometimes misclassified Milk_High as Milk_Low, and vice-versa.

This happened because:

Both classes look visually very similar

The difference in the milk level is small

Fewer images were available for the “High” class

Some frames were between Low and High, creating ambiguity

✔ Improvements Required

To solve the confusion between Low and High:

Add more images specifically for Milk_High

Use slightly larger bounding boxes during annotation

Increase training to 60–80 epochs

Use stronger image augmentations

Optionally switch to YOLOv8m for better class separation

✔ Learning Experience

This assignment helped me understand:

How to build a dataset from scratch

The importance of annotation accuracy

How model performance depends heavily on data quality

How to analyze mAP, precision, recall, and class-wise metrics

How YOLO behaves when classes look very similar

Overall, this task gave me practical experience in dataset creation, model fine-tuning, and performance evaluation using YOLOv8.
