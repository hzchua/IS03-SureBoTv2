# Capstone-IS03_PT-SureBoTv2

This project is an extension of SureBotv1 (https://github.com/hzchua/ISY5001-SureBoT)

## SECTION 1: PROJECT TITLE

## SureBoTv2 - Combating Multimodel Misinformation and Disinformation

![surebot](https://github.com/powlook/Capstone-IS03_PT-SureBoTv2/blob/master/Code/static/logo.png?raw=true)

## SECTION 2: OBJECTIVES

With the rapid advancement in technology and the proliferation of the usage of smart devices, news media outlets have gradually moved away from traditional print media to digital online news offerings. However, within the massive amount information on the Internet, not only are there genuine news, but there also exist a sizeable amount of fake news or misinformation shared for the purpose of deceiving and misguidance. With the combination of image, text and audio information, fake news has become a major issue of concern with increasing difficulty in distinguishing between what is real and what is fake on these platforms. These misinformation in social media are manifested in various forms, such as inaccurate claims, doctored images or real but irrelevant images that are reposted in an out-of-context scenario.

In this project, the team aims to explore and tackle the problem of wide-spread proliferation of multimodal misinformation and disinformation of social media images through the creation of an intelligent fact verification system named SureBoTv2. The system possess a multimodal reasoning framework injecting a joint visual-text reasoning together with the injection of external knowledge regarding current contextual information, a sentimental analysis of the messages and an analysis of the visual image to check for doctoring and therefore may have been altered. All these multi-modal inputs comes together to given an ensembled system where the final results rests on the feedback from all these components. The final answer will either be SUPPORTS or REFUTES or if there are insufficient information or if there is a deadlock, 'CANNOT BE DETERMINED'

Our application consists of a simple-to-use web application where one only needs to upload an image to fact-check and the web-app makes an inference if it SUPPORTS or REFUTES what the social media is implying. There is also a command line input for organisations who want to upload a series of images to check if their messages are true or false. Our system has shown a 80 percent accuracy rate on when tested on unseen images by the modal. The accuracy of the web-app can certainly be improved with better training and also more access to web resources (quite a few of the web-sites have pay-walls which makes it difficult to access the information)

## SECTION 3: CREDITS / PROJECT CONTRIBUTION

| Official Full Name | Student ID (MTech Applicable) | Work Items (Who Did What) | Email (Optional)
| ---- | ---- | ---- | ---- |
| CHUA HAO ZI | A0229960W | 1. Market Research <br /> 2. CAT-NET Research  <br /> 3. Joint Visual_Linguistics Reasoning Research  <br /> 4. VisualBert Implementation <br /> 5. Text Classification Research <br /> 6. Text Classifier Implementation <br /> 7. Website UI Implementation <br /> 8. System Integration <br /> 9. System Testing  <br /> 10. Project Report Writing | e0687368@u.nus.edu |
| YAP POW LOOK  | A0163450M | 1. Market Research <br /> 2. External Knowledge Retrieval, Summarisation and Abstraction Review  <br /> 3. External Knowledge Retrieval Implementation <br /> 4. System Integration  <br /> 5. System Testing  <br /> 6. Project Report Writing | e0147014@u.nus.edu |
| Kenneth Lee | AXXXXXX | 1. Market Research <br /> 2. CAT-NET Research <br /> 3. CAT-NET Implementation | exxxxxx@u.nus.edu |


## SECTION 4: USER GUIDE

### Installation
Reccomend to use python 3.7 or higher. Requires Pytorch and Transformers from Huggingface

**Step 1: Get the repository**

Using git clone 
```
git clone <Github Repo URL>
```
**Step 2: Create a Virtual Environment**

Enter folder and create a new environment to sandbox your developmental workspace (with Command Prompt)
```
cd Code
py -3.7 -m venv "YOUR_ENV_NAME"
"YOUT_ENV_NAME"\Scripts\activate
```
**Step 3: Install torch dependencies**

Install requirements using `pip`
```
pip install -r torch.txt
```
**Step 4: Download the Models**

**Download pretrained & trained models and replace the pipeline_models folder**: <br/>https://drive.google.com/file/d/1FeBgqDi4ktVVu5x1CgsF63K3lKkSGTYZ/view?usp=sharing

The folder structure will look like this:
```
pipeline_models/pretrained_models/BERT-Pair/
    	pytorch_model.bin
    	vocab.txt
    	bert_config.json
    	
pipeline_models/models/bart-large-cnn
	msmarco-distilroberta-base-v2
	pegasus-cnn_dailymail
	stsb-distilbert-base
	1layerbest.pth
	2layerbest.pth
	3layerbest.pth
	4layerbest.pth
	
pipeline_models/trained_models
	finalized_model.pkl
	model_roberta_base.pth
```

**Step 5: Download Detectron2 Model**

**Download model and replace the detectron2 folder:** <br/>https://drive.google.com/file/d/1hNJz9ZUT3sAzwgBjklNAS9dDFdY1pxS7/view?usp=sharing

```
folder: detectron2
```

**Step 6: Install Detectron2 Model**

Install detectron2 based on the download models via the following command
```
python -m pip install -e detectron2
```

**Step 7: Install Remaining Dependencies**

Install remaining dependencies via the following command
```
pip install -r requirements.txt
```

**Note**
To use the CloudVisionAPI, you can apply for the keys at this google website
https://cloud.google.com/vision/docs/setup. Follow the instructions in the setup.
Create a sub-folder in Code and store the key there.

### System Usage - Flask Based Web App
System implementation by Flask Based Web App (for single image processing).

**Step 1: Run**
```
python main.py
```
**Step 2: Open Website**
```
Access "http://localhost:5000/" on Google Chrome
```
**Step 3: Upload Image for Verification**
```
Click on "Choose File" to select the image to upload. Click "Submit"
```
**Step 4: Wait for SureBoTv2 to finish processing**

**Step 5: Review the results**


### System Usage - Command Line Interface
System implementation by Command Line Interface (for multiple image processing)

**Step 1: Upload images into folder**

```
Place the image files in the "images" folder
```

**Step 2: Run**
```
python SureBoT_v2.py
```

**Step 3: Check if correct image is extracted for processing**
```
Extracted Image will be shown. Proceed to close the window after verification
```
**Step 4: Wait for SureBoTv2 to finish processing**

**Step 5: Review the results**

```
Results can be viewed in the Command Line Interface or 
via an excel output file named "img_output.xlsx"
```


**Step 6: Repeat Steps (3) to (5) until all images are processed**


## SECTION 5: Separate Guide for Image Doctoring Detection (CAT-NET)

Note: CAT-NET works separately from SureBoTv2 system as this was not fully integrated with the architecture yet.

For the setup of CAT_Net please refer to the README in the CAT_Net subfolder

