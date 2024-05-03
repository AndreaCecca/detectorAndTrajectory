Repository of the paper:

**A. Ceccarelli, L. Montecchi: Better and safer trajectories with predicted object criticality, submitted.**

([Download the paper](paper submitted.pdf))

Object detection in autonomous driving consists in perceiving and locating instances of objects in multi-dimensional data, such as images or lidar scans. Very recently, multiple works are proposing to evaluate object detectors by measuring their ability to detect the objects that are most likely to interfere with the driving task. Detectors are then ranked according to their ability to detect the most relevant objects, rather than the highest number of objects. However there is little evidence so far that the relevance of predicted object may contribute to the safety and reliability improvement  of the driving task. This paper elaborates on a strategy, together with partial results, to deploy and configure object detectors that successfully exploit knowledge on object relevance. We show that, given an object detector, filtering objects based on their relevance, in combination with the traditional confidence threshold, reduces the risk of missing relevant objects, decreases the likelihood of dangerous trajectories, and improves the quality of trajectories in general.

**Instructions**

First, you need to install:

- conda environment, using the yaml file we provide. It creates an environment called openmmlab (then you activate with conda activate openmmlab)
- nuscenes-devkit https://github.com/nutonomy/nuscenes-devkit (we are using version 1.1.3) and the whole nuScenes dataset (this last one is optional -- see below GOAL1-GOAL2 data collection). 
- mmdetection3d version 2.x https://mmdetection3d.readthedocs.io/en/latest/
- Planning KL divergence library,  https://github.com/nv-tlabs/planning-centric-metrics , v0.0.8, with pretrained planner and mask (or you can retrain it if you prefer).


Next, you must replace some files from nuScenes devkit and pkl library, with modified versions that we provide. 
It is sufficient to go to the installation folder of nuScenes devkit and of pkl, and replace the files we provide in the github (folders nuscenes and pkl).

At this point, if everything is correct, you should be able to run the jupyter notebooks. Configurations and steps are explained in the jupyter notebook. There is a detailed discussion and comments inside each jupyter notebook.

There is a specific order to run the jupyter notebooks (GOAL 1, 2, 3 correspond to Hypothesis 1, 2, 3 in the paper):

1- GOAL1-GOAL2-data collection: this is to collect all the data related to GOAL 1 and GOAL 2. It may take several days to run, depending on the configuration settings you are using. We recommend to start with very few combinations of parameters.

2- GOAL1-GOAL2-analyze results: this is to extract results from the files that are produced. Essentially, it just reads json files and provides the relevant results.


**Short version.**
After installing the conda environment, the modified nuscenes devkit library, and the modified pkl library, you can directly use our result files.

You can download the results from: https://drive.google.com/drive/folders/1-R_RmjdLCawWTUuPhm2qWliacPMzoomo?usp=sharing . Just unzip there in two folders, named for example REG and FCOS3D, and set the right paths in the jupyter notebook. Essentially, it will allow you to avoid installing the mmdetection3d object detector, avoid running them on nuscenes, and skip "GOAL1-GOAL2 data collection", which is by far the longest jupyter to run.

