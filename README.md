# ISRMyo-I: A Database for sEMG-based Hand Gesture Recognition

## Introduction
This repository aims to publish a sEMG database for hand gesture recongnition, which is suitable for intra-session, inter-session, inter-day and inter-subject tests. Six subjects were involved in data collection on ten days, and two sessions a day with the interval of half an hour. In each session, one trial (10 secondes) for each geature was conducted. The electrode sleeve did not reweared between two sessions in a day. The utilised sEMG device was customised by the Intelligent System and Biomedical Robotics Group, which was discussed in [1]. 

## Hand Gestures
The sEMG signals of thirty hand gestures were colleced, as listed below:
* Label 0: Hand Rest (HR)
* Label 1: Hand Open (HO) 
* Label 2: Hand Closed (HC)
* Label 3: Wrist Flexion (WF) 
* Label 4: Wrist Extension (WE) 
* Label 5: Wrist Pronation (WP) 
* Label 6: Wrist Supination (WS)  
* Label 7: Ulnar Flexion (UF)  
* Label 8: Radial Flexion (RF) 
* Label 9: Fine Pinch (FP) 
* Label 10: Key Pitch (KP)  
* Label 11: Spherical Grasp (SG)  
* Label 12: Cylindrical Grasp (CG) 

## Database Organisation
* emgData/RawEMG: the folder that contains the raw recorded signal directly from the device without any processing
* emgData/RawEMG/XXXX: the folder named by subjects' name, the data of which is contained 
* emgData/RawEMG/XXXX/EMGDDS.txt: the data file titled by EMG*dds*.txt, where *dd*, *s* indicate the ID of day and the ID of the session, respectively.
* emgData/train_XXXX: the folder that contained the training samples (first 7 days) after segmentation and prcessing from the raw EMG , where XXXX indicates the subject' name
* emgData/test_XXXX: the folder that contained the testing samples (last 3 days) after segmentation and prcessing, where XXXX indicates the subject's name
* emgData/train_XXXX/CXX_train.txt: the segmented training samples of channel XX. Each row in the file contains 256 scale value, indicating an observation from channel XX.  
* emgData/train_XXXX/X.txt: the extracted TDAR feature (128 dimension) extracted from all segmented data from CXX_train.txt, where 16 channels were collected in a line.
* emgData/train_XXXX/y.txt: the lable of training samples, and each row corresponding to each row in CXX_train.txt and X.txt
* emgData/test_XXXX/CXX_train.txt: the segmented testing samples of channel XX. Each row in the file contains 256 scale value, indicating an observation from channel XX.  
* emgData/test_XXXX/X.txt: the extracted TDAR feature (128 dimension) as testing samples extracted from all segmented data from CXX_train.txt, where 16 channels were collected in a line.
* emgData/test_XXXX/y.txt: the lable of testing samples, and each row corresponding to each row in CXX_train.txt and X.txt

## Authors
Dr. Yinfeng Fang 
Dr. Dalin ZHou
Dr. Kairu Li
Prof. Honghai Liu

## References
[1] Y. Fang, H. Liu, G. Li, and X. Zhu, “A multichannel surface emg system for hand motion recognition,” Int. J. Humanoid Robot., vol. 12, no. 2, p. 1550011, 2015. 
