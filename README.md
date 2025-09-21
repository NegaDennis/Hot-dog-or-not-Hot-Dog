# Hot-dog-or-not-Hot-Dog
![ball-park-brand-Lntnns1YBEY-unsplash](https://github.com/user-attachments/assets/464d7f39-ad37-4fb0-9e08-e280db75b83d)

Hot dog or not hot dog? That is the question. One that probably no one ever ask but we are asking here anyway. :)

It is inspired by the popular sitcom series "Silicon Valley", one of the favourite sitcoms ever. One of the most comedic moments in the series was when a character decided to make a 'Seefood' app that tell what food was in a picture but ended up with Hot Dog or Not Dog app. His app was useless beyond words but pivotted to classify a "similar-looking object" and got rich for it :)

To practice skills with image recognition, I decided to follow his footstep and started this project.

As the project is still in progress, I will not be spending too much time on this README. Only the very essential will be included.

## Use Case

Similar to what was portrayed in the show, the use case is that the user will take a picture of their food, the model process the image and classify if it is hot dog or not.

## Approach

To handle this task, I will be using the tensorflow/kera library with Python, a classic approach to image recognition problems.

## Data

At the moment, I have 2 different data sources:
1. Kaggle (link): This Kaggle dataset was inspired by the same source. It contain 2000+ training images and 200+ testing images for the two classes in our context, hot dog and not hot dog.
2. Food-101 (link): Food-101 is a major project that collected a massive database of food images for AI training purposes. Luckily, hot dog was included in the collection process. This source contain an additional 1000 images of hot dogs. Since we have images of other food as well, it is possible to extend the scope to actually make 'Seefood' :)

For the current version, I am only using the Kaggle data source.

## Folder Structure

(TBD)
