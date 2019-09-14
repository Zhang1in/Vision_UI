### Visual_UI
Visual UI interface for fastai

[![made-with-python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg)](https://www.python.org/) [![GitHub license](https://img.shields.io/github/license/Naereen/StrapDown.js.svg)](https://github.com/Naereen/StrapDown.js/blob/master/LICENSE)

[![Visual UI Demo](static/visionV2.gif)](https://www.youtube.com/watch?v=I6hTbjUQvPU&feature=youtu.be)



Visual UI adds a graphical interface to fastai allowing the user to quickly load, choose parameters, train and view results without the need to dig deep into the code. 

________________________________________________________________________________________________________________________________________

### Updates

#### 09/12/2019 - Confusion Matrix Upgrades
- Under the Results tab, the confusion matrix tab now includes enhanced viewing features: 

> Option to view images with heatmaps or not
<p align="left">
  <img width="400" height="173" src="static/CM_one.PNG">
</p>

> Option to view images within each section of the matrix
<p align="left">
  <img width="200" height="236" src="static/CM_four.PNG">
</p>

> If heatmap option is 'YES' you can choose colormap, interpolation and alpha parameters
<p align="left">
  <img width="500" height="479" src="static/CM_two.PNG">
</p>

> Examples of using different parameters for viewing images
<p align="center">
  <img width="200" height="189" hspace="10" src="static/CM_five.PNG"/><img width="200" height="189" hspace="10" src="static/CM_six.PNG"><img width="200" height="189" hspace="10" src="static/CM_seven.PNG"><img width="200" height="189" hspace="10" src="static/CM_eight.PNG">
</p>

> Also have the option to view the images without the heatmap feature.  Images within each matrix class display Index, Actual_Class, Predicted_Class, Prediction value, Loss and Image location 
<p align="center">
  <img width="400" height="612" src="static/CM_nine.PNG">
</p>

> Images are stored within the path folder under their respective confusion matrix tags

<p align="center">
  False Positive
  <img width="856" height="100" hspace="10" src="static/CM_FP.PNG"/> 
  True Positive
  <img width="856" height="100" hspace="10" src="static/CM_TP.PNG"> 
  True Negative<img width="856" height="100" hspace="10" src="static/CM_TN.PNG">
</p>



#### 07/09/2019
- after a training run, the model is saved in the models folder with the following name: 'architecture' + 'pretrained' + batchsize + image size eg: resnet50_pretrained_True_batch_32_image_128.pth
- updated tkinter askdirectory code: now after choosing a file the tkinter dialogue box will be destroyed - previously the box would remain open

#### 06/05/2019
- results tab added where you can load your saved model and plot multi_plot_losses, top_losses and Confusion_matrix

#### 06/03/2019  
- path and image_path (for augmentations) is now within vision_ui so no need to have a seperate cell to specify path
- included link to fastai docs and forum in 'info' tab 

________________________________________________________________________________________________________________________________________



All tabs are provided within an accordion design using ipywidgets, this allows for all aspects of choosing and viewing parameters in one line of sight

<p align="center">
  <img width="350" height="181" hspace="20" src="static/data2.PNG"/><img width="350" height="181" src="static/aug_one2.PNG">
</p>

The Augmentation tab utilizes fastai parameters so you can view what different image augmentations look like and compare

<p align="center">
  <img width="350" height="276" hspace="20" src="static/aug_two3.PNG"/><img width="316" height="276" src="static/aug_three3.PNG">
</p>

View batch information

<p align="center">
  <img width="350" height="305" hspace="20" src="static/batch_three.PNG">
</p>

Review model data and choose suitable metrics for training

<p align="center">
  <img width="332" height="198" hspace="20" src="static/model.PNG"/><img width="350" height="198" src="static/metrics.PNG">
</p>

Review parameters get learning rate and train using the one cycle policy

<p align="center">
  <img width="451" height="184" hspace="20" src="static/LR_one.PNG"/><img width="350" height="184" src="static/LR.PNG">
</p>

Can experiment with various learning rates and train

<p align="center">
  <img width=393" height="273" hspace="20" src="static/LR_three.PNG"/><img width="300" height="273" src="static/Lr_four.PNG">
</p>



### Requirements
- fastai

I am using the developer version:

<p align="left">
  <img width="350" height="100" src="static/info.PNG">
</p>


`git clone https://github.com/fastai/fastai`

`cd fastai`

`tools/run-after-git-clone`

`pip install -e ".[dev]"`

for installation instructions visit [Fastai Installation Readme](https://github.com/fastai/fastai/blob/master/README.md#installation) 

- ipywidgets

`pip install ipywidgets
jupyter nbextension enable --py widgetsnbextension`

or 

`conda install -c conda-forge ipywidgets`

for installation instructions visit [Installation docs](https://ipywidgets.readthedocs.io/en/stable/user_install.html)

- psutil

psutil (process and system utilities) is a cross-platform library for retrieving information on running processes and system utilization (CPU, memory, disks, network, sensors) in Python

`pip install psutil`


### Installation

git clone this repository

`git clone https://github.com/asvcode/Vision_UI.git`

run `01_UI_Fastai.ipynb` and run `display_ui(path)`


### Known Issues

##### Google Colab

Colab does not currently support ipywidgets because their output is in its own frame so prevents ipywidets from working.  This is the link to issues thread [Link](https://github.com/googlecolab/colabtools/issues/60)

### Future Work

- Currently on works with images using the `ImageDataBunch.from_folder` option.  Plans to expand to `.from_csv` and `.from_df`
