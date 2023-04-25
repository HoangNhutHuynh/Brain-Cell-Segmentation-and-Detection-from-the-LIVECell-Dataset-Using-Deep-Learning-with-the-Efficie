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

# LIVECell_dataset_2021 - A mirror of the data from the LIVECell dataset. LIVECell is the predecessor dataset to this competition. You will find extra data for the SH-SHY5Y cell line, plus several other cell lines not covered in the competition dataset that may be of interest for transfer learning.

##What is it?
LIVECell (Label-free In Vitro image Examples of Cells) is a new dataset of manually annotated, label-free, phase-contrast images of 2D cell culture.\

"Label free" here is used in the medical sense - no fluorescent labels added to the samples. It is labeled in the machine learning sense as there are manual annotations.\

##What is it for?
Introduces the largest high-quality resource for label-free cell segmentation. Presents trained models developed to segment individual cells, for application in new research to enable label-free single-cell studies. Proposes a suite of benchmarks, which will readily facilitate continued development and performance comparison of future models.\

##What's in images?
5239 manually annotated, expert-validated, Incucyte HD phase-contrast microscopy images. There are eight types of cells chosen to maximize diversity of morphologies. All the images were captured by the same equipment, same magnification, resolution and cropped to the same size.
What are the annotations? More than a total of 1.6 million annotated cells. Manually annotated by a managed team of professional annotators, followed by two stages of quality assurance. The first level was performed by the annotation managers and second round by an experienced cell biologist.\

##What were the experiments?
Two architectures were tested using inherently different object detection mechanisms: anchor-based and anchor-free. The anchor-based model was an adapted version of Cascade Mask RCNN using a ResNest-200 backbone. The anchor-free model was based on CenterMask.
Nine models of each architecture were trained on LIVECell, one model on the whole dataset (LIVECell-wide train and evaluate benchmark) and one for each of the eight cell types For normalization, pixel intensity values were centered around zero by subtracting by the global average pixel value for the dataset (128), and then divided by the global standard deviation (11.58). To reduce the risk of overfitting, all training used multi-scale data augmentation meaning that image sizes were randomly changed from the original 520 × 704 pixels to a size with the same ratios, but shortest side set to one of (440, 480, 520, 580, 620) pixels. All models were trained on a NVIDIA DGX-1 server hosting eight NVIDIA Tesla V100 GPUs with 32 Gb of GPU RAM each, dual 20-Core 2.2 GHz Intel Xeon CPUs and 512 Gb system RAM. Microsoft COCO evaluation protocol was used but slightly modified to better reflect cell sizes.

##What were the findings?
When trained and evaluated on all of LIVECell, the two models achieve very similar accuracy. Though anchor based model pulls ahead on smaller subsets of data. Certain cell types in LIVECell, predominately BV-2, BT-474, Huh7 and SH-SY5Y, form densely packed clusters where it is not possible even for an experienced cell biologist to detect boundaries between individual cells
There is a large performance difference across cell types. In particular SH-SY5Y is very sensitive to IoU threshold.
Models perform better on each individual cell-type test set when trained on all cell types compared to training on that single cell type - indicating that a cell-type universal model is preferable to a specific one.

##References
The article: https://www.nature.com/articles/s41592-021-01249-6
The repository: https://github.com/sartorius-research/LIVECell
