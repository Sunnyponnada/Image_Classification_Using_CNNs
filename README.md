# Image_Classification_Using_CNNs
The basics of Convolutional Neural Networks  (CNNs), their implementation, and evaluation in image classification tasks

Steps to Load CIFAR-10 Dataset:
 1. CIFAR-10 is readily available in libraries such as TensorFlow. Use the following 
instructions to import the data:
 from tensorflow.keras.datasets import cifar10
 Load the dataset
 (x_train, y_train), (x_test, y_test) = cifar10.load_data()
 Verify the shapes
 print("Training data shape:", x_train.shape)
 print("Test data shape:", x_test.shape)
![download](https://github.com/user-attachments/assets/d0255ac6-d9e8-4ec8-9311-faf575b77a45)
**Accuracy Over Epochs (Left Graph)**

 >`Y-axis`: Accuracy (Training & Validation)

 >`X-axis`: Number of Epochs

* Blue Line (Training Accuracy):

 >Starts low (~35%) but steadily increases over epochs, reaching ~72%.

* Orange Line (Validation Accuracy):

 >Rises quickly in early epochs, reaching ~75%, but then stabilizes.

*Higher than training accuracy in early epochs, which suggests better generalization initially.*

**Loss Over Epochs (Right Graph)**

>`Y-axis`: Loss (Training & Validation)

>`X-axis`: Number of Epochs

* Blue Line (Training Loss):

 >Starts high (~1.7) and steadily decreases, indicating that the model is learning.

* Orange Line (Validation Loss):

 >Also decreases but stabilizes around epoch 10, suggesting the model has reached its best performance.

![download](https://github.com/user-attachments/assets/745f3825-d2fb-4775-b313-3370adfe32e2)
### Confusion Matrix Explanation
The confusion matrix shows how well the model classified each of the 10 CIFAR-10 categories.

* Diagonal values (highlighted in dark blue) → Correct classifications for each
category.

  >Example: 915 automobiles were correctly classified as automobiles.

* Off-diagonal values (lighter blue areas) → Misclassifications.

 >Example: 71 birds were misclassified as airplanes.

**Common misclassifications:**

* Birds are confused with cats and deer.

* Dogs are misclassified as cats and deer.

* Ships and trucks have strong predictions, meaning the model distinguishes them well.

### Classification Report Explanation

* Higher `precision` (near 1.0) means fewer false positives.

* **Best precision:** Trucks (0.86), Ships (0.84), and Automobiles (0.85) → Well-classified.

* Best `recall`: Automobiles (0.92) and Frogs (0.91).

* `F1-score`: The balance between precision and recall.

* Highest F1-scores:

 >Automobiles (0.88), Ships (0.86), and Trucks (0.85) → Strongest classes.

* Weakest class: Cats (0.57) → Model struggles to classify cats correctly.

* Overall Accuracy: 76%

 >The model performs well but struggles with animals like cats, dogs, and birds.

* The CNN model trained with Adam optimizer achieved a test accuracy of 75.52%, indicating that it generalizes well to unseen CIFAR-10 images, whereas the model trained with SGD performed worse at 52.42%, likely due to slower convergence and suboptimal learning rate settings.

* The test loss of 1.3189 suggests that while the model makes reasonably accurate predictions, there is room for improvement through techniques like hyperparameter tuning, data augmentation, or using a more advanced architecture.
