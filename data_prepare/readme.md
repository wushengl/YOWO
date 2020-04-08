## Dataset Preparation

The data we got is a few long videos of frame size 1080*720. The annotation is an xml file contains labels and box size and coordinates for all the frames that contain an action. We want our dataset to have a same structure as UCF101-24, so that it's compatible with the YOWO code.

We want a folder called rgb-images that contains all the frames with an action in them, and a folder called labels that contains all the labels(action, box size, box coordinate) txt files. They are both structured as rgb-images/labels >> label_name >> label_group_clip >> frames/label files. Frames/labels of the same group are from the same long video, frames/labels of the same clip means they're in a short continuous action video clip.

**video_processing_functions.py:** this file contains the functions we used to parse the xml file, seperating video into frames, and resizing the frames, etc.

**Video_Preprocessing.py:** this file can be used to transfer a video and annotations into a dataset that has same structure as UCF101-24.

**build_list_v3_.ipynb:** this file is used for generating training and testing data list. They should be a txt file, each line contains a path for the frames/label files.