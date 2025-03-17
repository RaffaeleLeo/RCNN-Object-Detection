# RCNN-Object-Detection
A couple of experiments using faster rcnn, detectron2 and YOLO to detect a variety of objects.

# Experiment 1: Road Object Detection using faster-rcnn and the Udacity dataset

* This is found in the faster_rcnn_road_detection jupyter notebook, I took the Udacity dataset for self-driving cars and fine-tuned a faster-rcnn model on it. 
    * https://public.roboflow.com/object-detection/self-driving-car

* Preprocessing techniques used:
    * random contrast adjustment
    * random brightness adjustment
    * random hflip

* Baseline model results:

* Fine-tuned results:

# Experiment 2: Comparing Detectron2 vs YOLO in detecting climbing holds

* Dataset: https://www.google.com/url?q=https://universe.roboflow.com/blackcreed-xpgxh/climbing-holds-and-volumes&sa=D&source=editors&ust=1742246713329984&usg=AOvVaw3tAfU2g1lePKqpTqcpVHEt

* Baseline
    * Detectron2: average precision of 0.62
    * YOLO: average precision of 0.61

* Fine-Tuning: 
    * Detectron2: one epoc of 2000 data instances
    * YOLO: 25 epocs of 100 iterations each

* Augmentations Used:
    * Random Brightness
        * Scaled the brightness of each image randomly between 80% and 120% of the original brightness.
    * Random Cutout:
        * The cutout augmentation randomly masks out two square regions in the image. Each square has a size of 32x32 pixels 
    * Random Horizontal Flip:
        * Simply flip the image horizontally
    * Random Cropping:
        * This augmentation randomly crops the image. This is used to try and simulate different viewpoints and object sizes

* After Fine-Tuning:
    * Detectron2: 0.75
    * YOLO: 0.72