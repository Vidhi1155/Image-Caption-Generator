
# **Image Caption Generator**
## **Introduction**
Image captioning teaches computers to describe visuals in human language. It’s like giving AI the ability to "see" a photo and "tell" you what’s happening—just as you might glance at this street scene and say:

**"People walking down a busy city street, surrounded by tall buildings and afternoon sunlight."**






![App Screenshot](https://github.com/Vidhi1155/Image-Caption-Generator/blob/master/Images/3286822339_5535af6b93.jpg?raw=true)

This technology merges computer vision (to understand pixels) with natural language processing (to craft sentences), creating AI that bridges visuals and words.

#### **1)The Computer’s "Eyes" (CNN)**
* A Convolutional Neural Network (ResNet50) scans the image.

* Detects key features: pedestrians, sidewalks, glass facades, shadows.

* Encodes them into a 2048-dimension feature vector (like a fingerprint for the scene).

#### **2) The Computer’s "Voice" (LSTM)**
* An LSTM network decodes the features into words.

* Uses context: "people" → often "walking" → often "street".

* Generates word-by-word, like autocomplete:
"People" → "walking" → "down" → "a" → "city" → "street"


## **Project Overview**
This project implements an Image Caption Generator using deep learning techniques. Given an input image, the model generates a natural language description (caption) of the image contents. The system uses:

* ResNet50 for image feature extraction

* LSTM network for sequence generation

* GloVe embeddings for word representations

* BLEU score for evaluation


## **Model Architecture**
1) **Image Encoder**: Pretrained ResNet50 (without final layer)

2) **Sequence Decoder**: LSTM with attention mechanism

3) **Embedding Layer**: GloVe 50-dimensional vectors

![App Screenshot](https://raw.githubusercontent.com/yunjey/pytorch-tutorial/master/tutorials/03-advanced/image_captioning/png/model.png)

### **Key Features**
* Custom data generator for efficient training

* Early stopping and model checkpointing

* BLEU score evaluation metrics

* Clean visualization of predictions

## **File Structure**

```bash
  project-root/
├── saved/                    # Saved model weights and features
├── Images/                   # Flickr8k images
├── Flickr8k.token.txt        # Image captions
├── Flickr_8k.trainImages.txt # Training set
├── Flickr_8k.testImages.txt  # Test set
├── glove.6B.50d.txt          # GloVe embeddings
├── Image_Caption_Generator.ipynb  # Main notebook
└── README.md                 # This file
```

## **How to Use**
### **Prerequisites**

* Python 3.10.12

* TensorFlow/Keras

* OpenCV

* NLTK (for BLEU scoring)

* GloVe embeddings file

### **Installations**
```bash
pip install -r requirements.txt
```

Download GloVe embeddings ->
[Goggle Drive Link](https://drive.google.com/file/d/12DzIDq9gpkt4rdGqiDZSlrHVqLVqKqeH/view?usp=sharing)

### **Running the Project**

1) Place all dataset files in correct directories

2) Run the Jupyter notebook cells sequentially

3) To generate new captions:
```bash
predict_caption('image_filename', encoding_test, test_descriptions)
```





## **Key Results**
* Achieved **BLEU-1 score** of **0.5064** on test set

* Model generates coherent and relevant captions

* Example predictions match human descriptions well
## **Sample Examples**
### **1) Example 1**

![App Screenshot](https://github.com/Vidhi1155/Image-Caption-Generator/blob/master/Images/2207244634_1db1a1890b.jpg?raw=true)

**Predicted Caption**: boy in red shirt is riding skateboard down ramp

### **2) Example 2**

![App Screenshot](https://github.com/Vidhi1155/Image-Caption-Generator/blob/master/Images/3458211052_bb73084398.jpg?raw=true)

**Predicted Caption**: group of people are walking down the road

### **3) Example 3**

![App Screenshot](https://github.com/Vidhi1155/Image-Caption-Generator/blob/master/Images/2723477522_d89f5ac62b.jpg?raw=true)

**Predicted Caption**: two dogs running through field


## **Acknowledgements**

* Flickr8k dataset providers

* Stanford NLP for GloVe embeddings

* Keras/TensorFlow developers
