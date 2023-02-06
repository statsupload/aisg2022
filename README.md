# Project Overview
- we use CV model to detect LCD readings from health monitoring devices. In this solution, we are detecting readings from blood pressure monitor devices.
- we did custom model training using yolov5 and integrate with AISG's PeekingDuck software framework. 
- The integration is for both batch mode and realtime inference.

# Project directory structure
- pkd_train - custom yolov5 model training using opensource digits detection dataset
- pkd_cli - batch mode inference on images via 'peekingduck run'
- pkd_app - realtime inference on upload images using FastAPI/Streamlit


# Our solution approach
1a. what has been done ? A search on what has been published in reports/journals/papers. 
- https://arxiv.org/abs/2210.01325 - Automated Medical Device Display Reading Using Deep Learning Object Detection
- https://scholarspace.manoa.hawaii.edu/server/api/core/bitstreams/510ad293-7734-4f6c-b4ad-afb5e81aceac/content - The Application of Image Recognition and Machine Learning to Capture Readings of Traditional Blood Pressure Devices
- https://pubmed.ncbi.nlm.nih.gov/31679409/ - Automated method for detecting and reading seven-segment digits from images of blood glucose metres and blood pressure monitors
- https://pubmed.ncbi.nlm.nih.gov/29854226/ - Utilizing Smartphone-Based Machine Learning in Medical Monitor Data Collection: Seven Segment Digit Recognition

1b. are ther datasets that we can use and test ?
- not exactly, there were images, but some of the above methods are convoluted.
- nothing reproducible we can leverage on.

2. use OCR ?
- we made use of HF to check if popular OCRs can detect digits from LCD displays
https://huggingface.co/spaces/Loren/Streamlit_OCR_comparator
- the output clearly showed that OCR cannot detect the digits
![ocr-1](https://user-images.githubusercontent.com/124442719/216889485-7b665590-d45b-4e88-b632-3b255166db5c.jpg)
![ocr-2](https://user-images.githubusercontent.com/124442719/216889502-30b1b783-5638-4c6f-8ad7-ae115ee4efdc.jpg)
- upon further investigation, we found out that these digits are known an 7 segment numbers, used in many LCD displays.


3. dataset
- we reckon we need about 1,000 images for train/test. hence we looked at kaggle, HF
- kaggle - https://www.kaggle.com/datasets/dataclusterlabs/bp-monitor-reading-medical-device-images
- roboflow - https://universe.roboflow.com/phils-workspace/digits-coi4f/dataset/3

- by chance, we look at roboflow and they have a well curated lists of datasets. we came across this digits dataset that the author used to train a model to read
measurements from his fitness/rowing machine. Even though it is not a health measurement device, we speculated that perhaps the model can be used. 
- Indeed, its possible 
![pkd-1](https://user-images.githubusercontent.com/124442719/216892447-9d3ad2b5-669f-4732-afef-08acc620785e.jpg)

# All of the above took 2.5 weeks and we are left with 1.5 weeks to do all the tasks below

4. our solution
- we wanted to have a solution that integrates and leverage on PeekingDuck's software framework. 
- we took time to understand how the software works and read every single inch of the documentation.
- we had to figure out how to train a yolov5 CV model. 
- after getting a trained model, our first stop was to get the it integrated using PKD cli for batch mode inference.
- once we got that sorted out, we had to work on a simple web app for real time inference.
- write the 2 page project overview.
- 1 min youtube video

Thank you AI Singapore for organizing this event ! So much learned ! So much more to learn !
