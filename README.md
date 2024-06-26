## installation  
`pip install -r requirements.txt`  
 git bush place you need!
## Achievement  
By replacing the processing from the start to the middle of recognition training with resnet-50, we reduced the GPU usage rate for the entire training to less than 12GB. As a result of the benchmark, I finished learning in a total of just under 6 minutes.

## Preparation  
put two training folders in same directory. At least 10 images.

## what is this?  
"version resnet-50" is a fine-tuned implementation of a deep learning model for image file classification using Mask_RCNN. I am using Resnet-50 as a pretrained model. Learning using Resnet-50 allows it to operate even on middle-class GPUs and achieves high discrimination performance. Batch size appropriately according to the VRAM of your GPU.

# Purpose  
As image generation speeds up, the number of images that can be generated in a short period of time has increased significantly, and it has often been difficult to process them. Therefore, we developed a model that pre-classifies images that you want to create and images that you do not want to create, or images that are rarely generated and are of low quality. Images that users personally want and those that they don't want can be classified based on certain characteristics. Furthermore, the fine tuning process is divided into two stages. CI_model_pre.py will cull the ones with extremely poor quality. CI_model_fine.py characterizes and further classifies the remaining images. This allows it to learn a diverse repertoire of classifications.

# Getting started  
Run CI_model_pre.py and CI_model_fine.py or resnet,py for learning. Run the prediction with CI_predict.py. For reference, normal operation has been confirmed with python  3.9 or more.

# Training  
The "features" that serve as discrimination criteria are determined from the image data used for learning. Manual selection of image data used for learning is done in the same way as creating LoRA. For example, if you choose something as random as possible for undesirable images and narrow down the features for desirable images, it will work fine.

