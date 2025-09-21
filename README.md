# Hot-dog-or-not-Hot-Dog
![ball-park-brand-Lntnns1YBEY-unsplash](https://github.com/user-attachments/assets/464d7f39-ad37-4fb0-9e08-e280db75b83d)

*(Photo by <a href="https://unsplash.com/@ballparkbrand?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Ball Park Brand</a> on <a href="https://unsplash.com/photos/two-brown-bread-on-blue-textile-Lntnns1YBEY?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>)*
      
Hot dog or not hot dog? That is the question. One that probably no one ever ask but we are asking here anyway. :)

It is inspired by the popular sitcom series "Silicon Valley", one of the favourite sitcoms ever. One of the most comedic moments in the series was when a character decided to make a 'Seefood' app that tell what food was in a picture but ended up with Hot Dog or Not Dog app. His app was useless beyond words but pivotted to classify a "similar-looking object" and got rich for it :)

To practice skills with image recognition, I decided to follow his footstep and started this project.

The end goal would be a complete mobile app that let people determine if there is indeed hot dog or not :D

## Patch notes
### What's new
- Uploaded the very first complete project folder, set up for continuous training and easy orchestration with config.
### What's next
- Refactor some scripts to remove unnecessary codes and make it leaner.
- Fine-tune model to improve accuracy. (right now, it's at 0.63 against testset)
- Try out some pre-trained models (EfficientNet and ResNet are top of the list at the moment)
## Use Case

Similar to what was portrayed in the show, the use case is that the user will take a picture of their food, the model process the image and classify if it is hot dog or not.

## Approach

To handle this task, I will be using the tensorflow/kera library with Python, a classic approach to image recognition problems.
For platform, I will be using Google Colab for easier set-up and scaling.

## Data

At the moment, I have 2 different data sources:
1. Kaggle [link](https://www.kaggle.com/datasets/dansbecker/hot-dog-not-hot-dog): This Kaggle dataset was inspired by the same source. It contain 2000+ training images and 200+ testing images for the two classes in our context, hot dog and not hot dog.
2. Food-101 [link](https://data.vision.ee.ethz.ch/cvl/datasets_extra/food-101): Food-101 is a major project that collected a massive database of food images for data mining. Luckily, hot dog was included in the collection process. This source contain an additional 1000 images of hot dogs. Since we have images of other food as well, it is possible to extend the scope to actually make 'Seefood' :)

For the current version, I am only using the Kaggle data source.

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
   
