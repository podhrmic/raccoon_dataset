# Raccoon Detector Dataset

This is a dataset that I collected to train my own Raccoon detector with [TensorFlow's Object Detection API](https://github.com/tensorflow/models/tree/master/research/object_detection). Images are from Google and Pixabay. In total, there are 200 images (160 are used for training and 40 for validation).

## Getting Started

##### Folder Structure:
```
+ annotations: contains the xml files in PASCAL VOC format
+ data: contains the input file for the TF object detection API and the label files (csv)
+ images: contains the image data in jpg format
+ training: contains the pipeline configuration file, frozen model and labelmap
- a few handy scripts: generate_tfrecord.py is used to generate the input files
for the TF API and xml_to_csv.py is used to convert the xml files into one csv
- a few jupyter notebooks: draw boxes is used to plot some of the data and
split labels is used to split the full labels into train and test labels
```

## Running
Go to your `tensorflow/models/research` directory and run:

```
python object_detection/train.py --logtostderr --pipeline_config_path=/PATH_TO_RACOON_DATASET/raccoon_dataset/training/ssd_mobilenet_v1_pets.config --train_dir=/PATH_TO_RACOON_DATASET/raccoon_dataset/training
```

Also don't forget to get the checkpoint file first:

```
wget http://download.tensorflow.org/models/object_detection/ssd_mobilenet_v1_coco_11_06_2017.tar.gz
tar -xvzf ssd_mobilenet_v1_coco_11_06_2017.tar.gz
cp ssd_mobilenet_v1_coco_11_06_2017/model.ckpt.data-00000-of-00001 /PATH_TO_RACOON_DATASET/raccoon_dataset/training/.
```

## Copyright

See [LICENSE](LICENSE) for details.
Copyright (c) 2017 [Dat Tran](http://www.dat-tran.com/).
