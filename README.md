# Pretrained-models-Multi-image-classification
Multiple images classification on Cifar10 dataset using fine tuned pre trained models VGG16, ResNet50, DenseNet121, EfficientNetB0

Environment: Google Colab

# Problem statement:
  I wanted to learn the usage of pre-trained models on image datasets for a multi class classification task. 

# Dataset 
  I have choosen CIFAR 10 dataset because of ease of access of a 10 classes dataset within tensorflow.
  The dataset has the following classes the model needs to classify:
    [Airplane, Automobile, Bird, Cat, Deer, Dog, Frog, Horse, Ship, Truck].
    
# Method and Parameters choosen
  I've used the pre trained models VGG16, ResNet50, DenseNet121, EfficientNetB0 and fine tuned them on the dataset.

  Initially i wanted to fine tune 20 layers with images resolution of (224,224) since that is the pixels the above pre trained models have been trained on.

  To just check if my code was working i set the images resolution be (32x32) which produced poor results for all models except for VGG16
  ![image](https://github.com/user-attachments/assets/51d424c3-4cd8-432f-b820-266cbe3c9724)

  With this i decided not to compromise of images resolution too much since all the models have been trained on high resolution images.

    
# Challenges faced and Fixes

  But when resizing the training and testing images to 224x224, my ram used to crash.

  Now i had 3 solutions for this problem:
    1. **Resize in batches **
        (Tried it, didnt work)
    2. **Resize images on-the-fly**
    3. **Use smaller input size**
      (sugeested 112x112, i did it using 160x160)

  I've implemented all 3 solutions

  ![image](https://github.com/user-attachments/assets/f36e429a-9103-4677-8963-f84d0aca03bf)

  I had to further tune my hyperparameters such as reducing batch size to from 32 to 16, and then to 8 for smooth execution of code.
  With the reduced images quality (160 x 160) and reduced number of fine tuned layers, there's a trade off with model performance.

# Results
![image](https://github.com/user-attachments/assets/54ac5b6c-d839-4a57-98a2-bea0645519c7)
![image](https://github.com/user-attachments/assets/121369d2-00e7-48bf-bdb5-f78f5ba71d04)
![image](https://github.com/user-attachments/assets/79029181-e165-464c-870b-9a586cfd72be)
![image](https://github.com/user-attachments/assets/ff086664-11a5-46fd-9468-8c057596e932)
