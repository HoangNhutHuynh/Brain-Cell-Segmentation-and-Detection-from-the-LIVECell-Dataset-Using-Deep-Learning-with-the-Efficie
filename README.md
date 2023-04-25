# Brain-Cell-Segmentation-and-Detection-from-the-LIVECell-Dataset-Using-Deep-Learning-with-the-EfficientDet-Model
https://ieeexplore.ieee.org/document/9945050

Abstract:
Neurological disorders are a common cause of death and disability in the world. One of the difficulties is that the response to treatment is hard to evaluate and quantify. Neuronal cells could be reviewed using light microscopy modality. However, it is challenging and time-consumption for detecting and segmenting even with experts. Therefore, accurate instance segmentation of cells is crucial. With the advancement of computer vision and deep learning, the detection and segmentation of cells with the aid of computers might lead to the resolution of these issues. This article presents methodological segmentation and brain cell markers derived from the LIVECell dataset. LIVECell dataset is a huge, high-quality, hand-annotated, skillfully constructed dataset including 1,686,352 individual cells in a variety of cell formats and density cultures. The proposed training model using the EfficientDet model is a model that can perform segmentation training and mark individual cell units by setting bounding boxes, which makes optimal use of LIVECell data without the need to use the single modeling two for two tasks. As a result, the intersection over union (IoU) is between 50.0% and 80.0%, with a mean accuracy precision(AP) of 58.824% and an average false-negative ratio (AFNR) of 56.566%, relying on the bounds segment bound box to mark separate objects with IoU values. This result may open up future functional studies on the individual kernel differences in performance and architecture of neural networks for segmentation implementation.

This research is funded by The Murata Science Foundation under grant number 22VH04. We would like to thank Ho Chi Minh City University of Technology (HCMUT), VNU-HCM for the support of time and facilities for this study.

Cite: H. N. Huynh, Q. T. Ha, A. T. Tran, H. D. T. Tran, P. A. Bui and T. N. Tran, "Brain Cell Segmentation and Detection from the LIVECell Dataset Using Deep Learning with the EfficientDet Model," 2022 IEEE 4th Eurasia Conference on Biomedical Engineering, Healthcare and Sustainability (ECBIOS), Tainan, Taiwan, 2022, pp. 12-15, doi: 10.1109/ECBIOS54627.2022.9945050.

# Dataset Description
In this competition we are segmenting neuronal cells in images. The training annotations are provided as run length encoded masks, and the images are in PNG format. The number of images is small, but the number of annotated objects is quite high. The hidden test set is roughly 240 images. Link: https://www.kaggle.com/competitions/sartorius-cell-instance-segmentation/overview

Note: while predictions are not allowed to overlap, the training labels are provided in full (with overlapping portions included). This is to ensure that models are provided the full data for each object. Removing overlap in predictions is a task for the competitor.

Files
train.csv - IDs and masks for all training objects. None of this metadata is provided for the test set.\
id - unique identifier for object.\
annotation - run length encoded pixels for the identified neuronal cell\
width - source image width\
height - source image height\
cell_type - the cell line\
plate_time - time plate was created\
sample_date - date sample was created\
sample_id - sample identifier\
elapsed_timedelta - time since first image taken of sample\
sample_submission.csv - a sample submission file in the correct format\
train - train images in PNG format\
test - test images in PNG format. Only a few test set images are available for download; the remainder can only be accessed by your notebooks when you submit.\
train_semi_supervised - unlabeled images offered in case you want to use additional data for a semi-supervised approach.\

LIVECell_dataset_2021 - A mirror of the data from the LIVECell dataset. LIVECell is the predecessor dataset to this competition. You will find extra data for the SH-SHY5Y cell line, plus several other cell lines not covered in the competition dataset that may be of interest for transfer learning.
