🍞🥣🍎 Food Image Classification using CNN

A Deep Learning project focused on classifying food images using Convolutional Neural Networks (CNNs). The goal is to automate image categorization and reduce the need for manual labeling.

📌 Project Overview

This project develops and evaluates CNN-based models capable of classifying food images into three categories:

🍞 Bread
🥣 Soup
🍎 Vegetable-Fruit

The study explores different CNN architectures and compares their performance to improve classification accuracy and generalization.

🎯 Objective

Food businesses and image-based platforms often require large numbers of images to be categorized manually. This project aims to build an image classification model that can automatically identify food items and assign them to the correct category.

📂 Dataset

The dataset is organized as follows:

Food_Data/
│
├── Training/
│   ├── Bread/
│   ├── Soup/
│   └── Vegetable-Fruit/
│
└── Testing/
    ├── Bread/
    ├── Soup/
    └── Vegetable-Fruit/

Dataset Information
Total images: 3,203
Image size: 150 × 150 pixels
Color channels: RGB (3 channels)
Training Data Distribution
Class	ImagesSoup	1,500
Bread	994
Vegetable-Fruit	709
🛠️ Technologies Used
Python
TensorFlow
Keras
OpenCV
NumPy
Pandas
Matplotlib
Seaborn
Google Colab
🔄 Data Preprocessing

Before training, the images underwent the following preprocessing steps:

Loaded using OpenCV
Resized to 150 × 150 pixels
Converted into NumPy arrays
Normalized by scaling pixel values to the range [0,1]
One-hot encoded for multiclass classification
🚀 Model 1: Baseline CNN
Architecture
Conv2D (64 filters)
↓
MaxPooling2D
↓
Conv2D (32 filters)
↓
MaxPooling2D
↓
Conv2D (32 filters)
↓
MaxPooling2D
↓
Flatten
↓
Dense (100 neurons)
↓
Softmax (3 outputs)

Training Configuration
Optimizer: SGD
Learning Rate: 0.01
Momentum: 0.9
Loss Function: Categorical Crossentropy
Batch Size: 32
Epochs: 60
Validation Split: 10%
Results
Metric	ValueTest Accuracy	66.91%
Test Loss	1.1101
Best Validation Accuracy	72.90%
Observations
Signs of overfitting were observed during training.
The largest classification errors occurred between the Bread and Soup categories.
🚀 Model 2: Improved CNN

To improve performance and reduce overfitting, a deeper CNN architecture with Dropout layers was implemented.

Architecture
Conv2D (256 filters, 5×5)
↓
MaxPooling2D
↓
Dropout (0.25)
↓
Conv2D (128 filters, 5×5)
↓
MaxPooling2D
↓
Dropout (0.25)
↓
Conv2D (64 filters, 3×3)
↓
MaxPooling2D
↓
Dropout (0.25)
↓
Conv2D (32 filters, 3×3)
↓
MaxPooling2D
↓
Dropout (0.25)
↓
Flatten
↓
Dense (64 neurons)
↓
Dense (32 neurons)
↓
Softmax (3 outputs)

Training Configuration
Optimizer: Adam
Learning Rate: 0.001
Batch Size: 32
Epochs: 60
Early Stopping
Model Checkpointing
📈 Performance Comparison
Metric	Model 1	Model 2Test Accuracy	66.91%	76.60%
Test Loss	1.1101	0.6155
Best Validation Accuracy	72.90%	82.24%
Improvements Achieved

✅ Higher overall accuracy

✅ Lower test loss

✅ Reduced overfitting through Dropout regularization

✅ Better generalization on unseen data

📊 Evaluation Methods

The models were evaluated using:

Accuracy
Classification Report
Confusion Matrix

The confusion matrix showed that Bread and Soup remained the most challenging classes to distinguish due to similarities in color, texture, and image composition.

🔮 Future Improvements

Potential enhancements include:

Data Augmentation
Transfer Learning (VGG16, ResNet50, EfficientNet)
Hyperparameter Tuning
Larger and more balanced datasets
Experimenting with different optimizers and architectures
💡 Applications

This model can be integrated into:

Food recognition systems
Restaurant management applications
Automated image tagging platforms
Food delivery applications
Computer vision projects involving food categorization
▶️ Running the Project
Clone the repository:
git clone https://github.com/your-username/food-image-classification.git
cd food-image-classification

Install dependencies:
pip install -r requirements.txt

Open the notebook:
jupyter notebook Food_Image_Classification.ipynb


or run it directly in Google Colab.

📁 Repository Structure
├── Food_Image_Classification.ipynb
├── README.md
├── requirements.txt
└── Food_Data/
    ├── Training/
    └── Testing/

👨‍💻 Author

Raúl Peralta

Deep Learning and Computer Vision project developed using TensorFlow/Keras and Google Colab for multiclass food image classification.

📜 License

This project is intended for educational and portfolio purposes. Feel free to fork, modify, and build upon it.
