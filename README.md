# Image Captioning Model Criticism with Similar Images

## Overview 
* Present similar images for image captioning model criticism inspired by Stock and Cisse's 2018 paper "ConvNets and ImageNet Beyond Accuracy: Understanding Mistakes and Uncovering Biases" (ECCV 2018). 
* Apply the methodology introduced to evaluate Hendricks and Burns et al.'s "Women Also Snowboard: Overcoming Bias in Image Captioning Models" (ECCV 2018). 
## Requirements
* Python 3
* pip

To install the required packages run
`pip install -r requirements.txt`

## Related Repositories
* [Women Also Snowboard (Hendricks and Burns et al, 2018)](https://github.com/kayburns/women-snowboard/)
* [Microsoft COCO Caption Evaluation](https://github.com/salaniz/pycocoevalcap)

## Data
The pairs of similar images found for MSCOCO and Flickr, augmented images, and image masks are found in the folder `images`. 

* `images/similar images` contains the 51 pairs of similar found from MSCOCO and Flickr, used to evaluate the Equalizer model
* `images/other images` contains the four other potential similar images we found
* `images/augmented images` contains the augmented versions (e.g. cropped, scaled, sheared, and flipped) of the images in `images/other images`

The file naming convention is as follows: `{0}_{1}_{2}_{3}_{4}.jpg`:
* {0} takes values 'm' or 'f' and denotes whether the image comes from MSCOCO ('m') or Flickr ('f')
* {1} takes values 'm' or 'f' and denotes the gender of the individual in the image (male or female)
* {2} is the object category 
* {3} is the image id of the MSCOCO image or, for Flickr photos, the image id of the corresponding MSCOCO image
* {4} ranges from 1-5 and is only used for Flickr images

## Code
* The code is contained in Jupyter notebooks found under the folder `code`. 
* The adjustments made to the Equalizer code are located in this [fork](https://github.com/dorazhao99/women-snowboard) of the Women Also Snowboard repository. 
* Our final weights for the trained models are available.

## Results
The error rate, ratio Delta, and sentence similarity can be calculated using `Analyze Results.ipynb` and `Semantic Similarity.ipynb`. To calcualte the MSCOCO Evaluation metrics (e.g. BLEU, ROUGE), use [Microsoft COCO Caption Evaluation](https://github.com/salaniz/pycocoevalcap). However, you will need to replace `eval.py` with `eval_special.py` and use `Evaluate Captions.ipynb`. 

Our results along with the Grad-CAM heatmaps for each model are located in the `results` folder.  

## Report
Our paper is accessible in the file `report.pdf`
