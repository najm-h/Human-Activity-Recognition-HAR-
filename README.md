***A Deep Bidirectional LSTM Model Enhanced by Transfer-Learning-Based Feature Extraction for Dynamic Human Activity Recognition***

# Abstract
Dynamic human activity recognition (HAR) is a domain of study that is currently receiving considerable attention within the fields of computer vision and pattern recognition. The growing need for artificial-intelligence (AI)-driven systems to evaluate human behaviour and bolster security underscores the timeliness of this research. Despite the strides made by numerous researchers in developing dynamic HAR frameworks utilizing diverse pre-trained architectures for feature extraction and classification, persisting challenges include suboptimal performance accuracy and the computational intricacies inherent in existing systems. These challenges arise due to the vast video-based datasets and the inherent similarity in the data. To address these challenges, we propose an innovative, dynamic HAR technique employing a deep-learning-based, deep bidirectional long short-term memory (Deep BiLSTM) model facilitated by a pre-trained transfer-learning-based feature-extraction approach. Our approach begins with the utilization of Convolutional Neural Network (CNN) models, specifically MobileNetV2, for extracting deep-level features from video frames. Subsequently, these features are fed into an optimized deep bidirectional long short-term memory (Deep BiLSTM) network to discern dependencies and process data, enabling optimal predictions. During the testing phase, an iterative fine-tuning procedure is introduced to update the high parameters of the trained model, ensuring adaptability to varying scenarios. The proposed model’s efficacy was rigorously evaluated using three benchmark datasets, namely UCF11, UCF Sport, and JHMDB, achieving notable accuracies of 99.20%, 93.3%, and 76.30%, respectively. This high-performance accuracy substantiates the superiority of our proposed model, signaling a promising advancement in the domain of activity recognition.

# Paper link: https://www.mdpi.com/2076-3417/14/2/603

# Dataset
UCF11 data presented in this study are openly available in: https://www.crcv.ucf.edu/data/UCF_YouTube_Action.php. 
UCFSports data presented in this study are openly available in: https://www.crcv.ucf.edu/data/UCF_YouTube_Action.php. 
JHMDB data presented in this study are openly available in: http://jhmdb.is.tue.mpg.de/.

# Preprocessing:
# Feature Extraction

MobileNet:
model = model_MobileNet
total_classes = number of action
X = []
Y = []
for path, dirs, files in os.walk(MainFolder):
        print(path)
    if re.search(r'datasetpat') is not None:
        continue
    
    if re.search(r'datasetpat', path) is not None:
        p = path.split('//')[2]
        q = path.split('///')[3]
        print("Extracting features from {} in {} folder...".format()
        
        for file in files:
            actual_path = os.path.join(path, file)
            t = vid(actual_path, dim=dim, skipValue=skipValue)
            t = preprocess(t, preProcess_func)
            #print("dimension t:",t.shape)
            t = model.predict(t)
            print(t)
            X.append(t)
            Y.append(classes[p])
            break 

The output of the X is contained the features and y is the label equivalent the features. 


#Classification

We used a padding funaction Which produced trial*30*1024.

This feed into the
several deep learning layer
LSTM Layer
Fully Connected Layer

# if you the instruction and pseudocode is helpful for you please cite below paper:

## word citation formate:
Hassan, Najmul, Abu Saleh Musa Miah, and Jungpil Shin. 2024. "A Deep Bidirectional LSTM Model Enhanced by Transfer-Learning-Based Feature Extraction for Dynamic Human Activity Recognition" Applied Sciences 14, no. 2: 603. https://doi.org/10.3390/app14020603

## latex citation formate
'''
@Article{app14020603,
AUTHOR = {Hassan, Najmul and Miah, Abu Saleh Musa and Shin, Jungpil},
TITLE = {A Deep Bidirectional LSTM Model Enhanced by Transfer-Learning-Based Feature Extraction for Dynamic Human Activity Recognition},
JOURNAL = {Applied Sciences},
VOLUME = {14},
YEAR = {2024},
NUMBER = {2},
ARTICLE-NUMBER = {603},
URL = {https://www.mdpi.com/2076-3417/14/2/603},
ISSN = {2076-3417}}






