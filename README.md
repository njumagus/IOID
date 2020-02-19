# Instance of Interest Detection

## Download
Our code and pre-trained model can be downloaded at http://114.55.28.227:2443/yuf/mm19-yuf-code

## Requirements
opencv_python==3.4.3.18  
numpy==1.16.2  
scikit_image==0.14.2  
torchvision==0.2.1  
torch==0.4.1  
scipy==1.1.0  
matplotlib==3.0.0  
Pillow==7.0.0  
skimage==0.0  
tensorboardX==2.0  

## Dataset
We construct the first dataset for IOID based on the training set of MSCOCO 2017, which contains 123,287 images with manually labelled captions and panoptic segmentation. We construct our dataset by representing each IOI with its category and its region in the panoptic segmentation. There are 133 categories of IOIs in total, the same as those provided by the panoptic segmentation in MSCOCO 2017, containing 80 thing categories, such as person, ball and cow, and 53 stuff categories, such as wall, tree and mountain. We further divide the datasets into the training set and the test set, which contain 36,000 images with 165,094 IOIs and 9,000 images with 40,617 IOIs, respectively.  
The dataset consists of the following sections:
1. The original images which can be downloaded at https://drive.google.com/open?id=1yRyduTD58_lL1GI4oGoUdhpi3gnjzvgO.
2. The panoptic segmentation images which can be downloaded at https://drive.google.com/open?id=1nxvSLhNkk7Vc2HEEXquG51tESwEHK07T.
3. Dataset annotations in json format which can be downloaded at https://drive.google.com/open?id=1dWZZf5PPokmWvAgT0_Cel5QTnocc1T2t.

In order to verify the effectiveness of the method, we compare the results of our method with some of the other methods. The data of the instance extraction experiment can be downloaded at https://drive.google.com/open?id=1wFupKzYt0sabBw_UjMc6AWLDwnbidLsj. And the data of the interest estimation experiment can be downloaded at https://drive.google.com/open?id=1dU_YF6p3cwXR2Kq51O2y-Gft5WiRvKb_.
## Quick Start
To visualize the result of the instance of interest detection, we provide a demo and it can be performed in the following script:
```python
python demo.py −−img <image path> −−config <configuration file path>
```
You can train you own model by running the following script:
```python
python train.py −−setting <setting list> −−config <configuration file path>
```
Based on the pretrained model, you can predict all the images in the dataset by running the following script:
```python
python predict.py −−mode <mode> −−config <configuration file path>
```
To validate the performance of the CIN model, the validate.py file can be performed in the following script:
```python
python validate.py −−config < configuration file path>
```
In order to verify the effectiveness of the method, the component_analysis.py file can be performed in the following script:
```python
python component_analysis.py −−ins_ext <panoptic segmentation path> −−sem_ext <semantic segmentation path> −−p_intr <interest estimation path> −−config <configuration file path>
```