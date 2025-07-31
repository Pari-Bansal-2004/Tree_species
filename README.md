🌳 Tree Species Classification -
This AI-powered app helps students and nature enthusiasts identify and explore tree species based on image, location, and tree attributes.

🔍 Project Overview - 
The goal of this project is to build a machine learning model that classifies tree species using leaf and tree images. This model can assist botanists, environmentalists, or nature lovers in identifying tree species quickly and accurately.

🧠 Features

🌲 Recommend Trees by Location

- Input GPS coordinates (latitude, longitude)
- Specify tree diameter, native status, city, and state
- Returns the top 5 tree species likely found in that area

📍 Find Locations for a Tree

- Choose a tree species from a dropdown
- Displays cities and states where the species is most commonly found

📷 Identify Tree from Image

- Upload an image of a tree
- CNN model predicts the species
- If found in the dataset, shows common locations for that species

📂 Dataset Details

- Source: Kaggle – Tree Species Identification Dataset
- Classes: 30 Tree species
- Images: 1,596 total images
- Data Structure: Each class has its own folder containing respective images.

* Here are some of the species in the dataset :-
  ['shirish', 'pilikaren', 'pipal', 'simlo', 'vad', 'sugarcane', 'sitafal', 'sonmahor', 'saptaparni', 'other', 'kanchan', 'jamun', 'kesudo', 'motichanoti', 'mango', 'gulmohor', 'nilgiri', 'neem', 'khajur', 'gunda', 'cactus', 'coconut', 'bamboo', 'bili', 'amla', 'garmalo', 'asopalav', 'champa', 'banyan', 'babul']

   📌 Note: The other category contains 150 images, likely representing miscellaneous or unidentified trees.

📊 Dataset Description

🗂️ Tree Metadata

- Source: Open tree surveys from multiple cities (e.g., Louisville, Chicago)
- Total records: ~1.38 million
- Key columns:
  - common_name: Tree species (e.g., Bur Oak)
  - scientific_name: Botanical name (e.g., Quercus macrocarpa)
  - latitude_coordinate, longitude_coordinate
  - city, state, address
  - native: Whether the tree is native to the area
  - diameter_breast_height_CM: Tree height/width measure

🖼️ Tree Image Dataset

- Structure: Folder-based, each folder named after a tree species
- Use: Used to train the CNN for species recognition
- Preprocessing:
  - Images resized to 224x224
  - Normalized pixel values
  - Augmented with flips, zoom, and rotation

🧪 Algorithms Used

🔍 Recommender System
-  Algorithm: K-Nearest Neighbors (KNN)
- Library: sklearn.neighbors.NearestNeighbors
-  Inputs: location, diameter, native status, city/state
-  Output: Most common tree species nearby

🧠 CNN Classifier
- Model: Sequential CNN (Conv2D + MaxPooling + Dense layers)
- Library: tensorflow.keras
- Input: 224x224 image
- utput: Predicted tree species with probability
- Loss: Categorical Crossentropy
- Optimizer: Adam

📊 Preprocessing & Encoding
- Categorical Encoding: LabelEncoder
- Scaling: StandardScaler for lat/lon/diameter \* Data Splits: 80% training, 20% validation

🧰 Tools & Environment

📓 Google Colab (used for writing and executing the code)

🐍 Python Libraries: 
* cv2 (OpenCV) 
* numpy 
* matplotlib 
* collections 
* os

🗓️ Week 1 Report -
we focused on:
- Setting up the project environment in Google Colab
- Loading and inspecting the dataset

🗓️ Week 2 Report - 
we focused on:
- Understanding class distributions
- Checking image dimensions and formats
- Displaying sample images from the dataset
- Preprocess and resize all images to a uniform shape
- Split the dataset into training, validation, and test sets
- Build and train a CNN-based classification model
- Evaluate model accuracy and tune hyperparameters

📊 Dataset Exploration -

🔍 Class Distribution
We analyzed the number of images available per class to ensure data balance. Here’s a summary:
- Most classes have 49–50 images
- The other class has 150 images
- Total classes: 30
- Total images: 1596

🖼️ Image Properties
Using OpenCV and NumPy, we examined 10 images from each class:
- Min resolution: 135 x 146
- Max resolution: 1699 x 1300
- Average resolution: ~254 x 290
- Channels: RGB (3 channels)
