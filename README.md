# Project Overview
- we use CV model to detect LCD readings from health monitoring devices. In this solution, we are detecting readings from blood pressure monitor devices.
- we did custom model training using yolov5 and integrate with AISG's PeekingDuck software framework. 
- The integration is for both batch mode and realtime inference.

# Project directory structure
- pkd_train - custom yolov5 model training using opensource digits detection dataset
- pkd_cli - batch mode inference on images via 'peekingduck run'
- pkd_app - realtime inference on upload images using FastAPI/Streamlit


# Our solution approach
1. Why not OCR ?
https://huggingface.co/spaces/Loren/Streamlit_OCR_comparator



2. recent publications


3. dataset


https://universe.roboflow.com/phils-workspace/digits-coi4f/dataset/3


# Others


