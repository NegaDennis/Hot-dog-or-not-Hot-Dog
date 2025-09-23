# Hot-dog-or-not-Hot-Dog
![ball-park-brand-Lntnns1YBEY-unsplash](https://github.com/user-attachments/assets/464d7f39-ad37-4fb0-9e08-e280db75b83d)

*(Photo by <a href="https://unsplash.com/@ballparkbrand?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Ball Park Brand</a> on <a href="https://unsplash.com/photos/two-brown-bread-on-blue-textile-Lntnns1YBEY?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>)*
      
Hot dog or not hot dog? That is the question. One that probably no one ever ask but we are asking here anyway. :)

It is inspired by the popular sitcom series "Silicon Valley", one of my most favourite sitcoms ever. One of the most comedic moments in the series was when a character decided to make a 'Seefood' app that tell what food was in a picture but ended up with Hot Dog or Not Dog app. His app was useless beyond words but after pivoing to classify a "similar-looking object" and he got a multi-million dollars deal for it :)

To practice skills with image recognition, I decided to follow his footstep and started this project.

The end goal would be a complete mobile app that let people determine if their food is indeed hot dog or not :D

## Patch notes
### What's new
- Added food101 dataset to training data (+1000 images for training - hot dog category)
- Tweaked some hyperparameters (learning rate, batch_size,...)
- Accuracy improved significantly:
  + Val_accuracy ~0.8; Val_loss ~0.48
  + Test_accuracy ~0.7; Test_loss ~0.68
### What's next
- Performance is acceptable for now; Move on to building software side (the app).


## Use Case
Similar to what was portrayed in the show, the use case is that the user will take a picture of their food, the model process the image and classify if it is hot dog or not.

## Approach

To handle this task, I will be using the tensorflow/kera library with Python, a classic approach to image recognition problems.
For platform, I will be using Google Colab for easier set-up and scaling.


The current pipeline:


|Data Loading| ---> |Data Preprocessing| ---> |Modelling/Optimize| ---> |Evaluate| ---> |Export|

- Data Loading: A simple loading of images data. It pull images from relevant folders and label appropriately.
- Data Pre-processing: Contain several steps.
  
        Step 1: Resize image
        Step 2: Convert image data to arrays
        Step 3: Normalize arrays
- Modelling/Optimize: Use specified model architecture and layers and optimizing methods to train model. A portion of training data is used for validation.
- Evaluate:
  
        + Evaluate model on test set using standard metrics for classification problems (accuracy, precision, recall, f-1, kappa score).
        + Include training history graphs to study training behaviors.
- Export: Export the following items for each model run:
  
        + model.keras
        + classification report.txt
        + confusion matrix.txt
        + config.json
        + notes (contain context around that specific model run and sometimes for frustration dumping :) )


To retrain or fine-tune, one can edit config or dump data into appropriate folders. very easy.

## Data

At the moment, I have 2 different data sources:
1. [Kaggle](https://www.kaggle.com/datasets/dansbecker/hot-dog-not-hot-dog) : This Kaggle dataset was inspired by the same sitcom (yes, it's very popular and cool). It contain 2000+ training images and 200+ testing images for the two classes in our context, hot dog and not hot dog.
2. [Food-101](https://data.vision.ee.ethz.ch/cvl/datasets_extra/food-101) : Food-101 is a major project that collected a massive database of food images for data mining. Luckily, hot dog was included in the collection process. This source contain an additional 1000 images of hot dogs. Since we have images of other food as well, it is possible to extend the scope to actually make 'Seefood' :)

Used fully Kaggle data set. Used food-101 for only training - hot dog class. Might add randomly some to training - not hot dog class as well.

## Folder Structure

The current set up is like this:

      Hot dog or not Hot Dog/

            │  Notebook.ipynb (this is where i run the scripts, explore training results, and so on.)
      
            │  Config.json
      
            │  Readme.md
      
            └─ input data (small)/
      
               ├─ train
         
               └─ test
         
            └─ input data/
      
               ├─ kaggle_set
         
               └─ food101_set
         
               (it's empty in this repo because I haven't set up .gitignore yet and I don't want to upload all data)
         
            └─ models/
      
               ├─ hot_dog_or_not_hot_dog_v1_....
         
               └─ ....
         
               (basically where I dump all models from previous runs that I think are worth saving)
         
            └─ scr/
      
               ├─ preprocessing.ipynb
         
               └─ models.ipynb
               
               └─ optimizer.ipynb
         
               └─ export.ipynb

## Performance

At the moment, the model is giving accuracy level of 0.7 on the testset.

The confusion matrix is as follow.

<img width="519" height="410" alt="conf matrix" src="https://github.com/user-attachments/assets/2f16e060-415b-4657-acdc-1f4372ab13fa" />


The training process is going well. Stable and steep but not too steep learning curve.

<img width="545" height="470" alt="train vs val accuracy" src="https://github.com/user-attachments/assets/6bb3c663-be68-4279-9e50-4c1eef186a14" />

<img width="536" height="470" alt="train vs val loss" src="https://github.com/user-attachments/assets/55fb87e4-0b67-4ee0-8244-8434d90209f8" />


Okay for now. Move on to building the app side.
