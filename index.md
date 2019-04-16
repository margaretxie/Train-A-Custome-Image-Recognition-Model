### This is a walk through tutorial for using Caltech256 dataset and APPLE Create ML to train a image cognitition model. 
It is for myself for reviewing what I learned and practiced. Also could be a tutorial for who is interested in it. 

The targeted model will be used to recognized five classes of plant. 

### Step 1. Prepare dataset for training
 For people who already have their own dataset, or already know how to create their dataset, please skip this step.
 For practicing purpose, I recommend using Caltech256, which is a object category dataset collection of 256 object categories, at least 80 images per category. 
1)	Click here to access Caltech256, click the download link at the lower part of the page
2)	After the download(1.2G) finishes, save it in your preferred folder location. 
3)	Choose folders of categories we need as shown in the below diagram. Delete all others.  
4)	We need two folders for each category. One for training, one for testing. Let’s make the existing folder as “plants – for training”, and copy it , named “plants – for testing”.
5)	In the Training folder, for each sub-folder, keep the first 80 images, delete the others.
6)	In the Testing folder, for each sub-folder, delete the first 80 images, delete the others. 
So for now we have two dataset folders as below:
 
### Step 2: Get MacBook and XCode ready
     A MacBook with macOS Mojave version 10.14.4 or above is required, and XCode upgraded 
     to version 10 or above. 

### Step 3: Create a new XCode playground 
         In XCode, click File – New – Playground, choose macOS – Blank template. Save the new playground. 

### Step 4: Open the Classifier Builder 
In the playgroup editor, type in below codes to import CreateMLUI, and make the classifier builder show up:
 
After executing the above code by clicking the blue arrow button, the “ImageClassifier” builder should show up in the right as below diagram shows:
 

### Step 5: Train the model
        Simply drag and drop the training folder that with the 5 sub-folders, 400 images, into the ImageClassifier. It takes about two minutes to train. And then gives the training result. For example, as below shows:
 
     If you want to adjust the model accuracy, could execute the last line of code  “builder.showInLiveView()” again to have a new instance of image classifier. Then click the display dropdown list symbol as below orange circle highlighted. Enter value “Max iterations” (e.g. 15, 18, 20). Drag and drop the train folder again.
     

### Step 6: Test the model
Drag and drop the testing folder into the image classifier. It takes around one minute to test. 
 

### Step 7: Save the trained model
When you are satisfied with the training result. Click the display dropdown list symbol  again, choose where you want to save the model, and then click the Save button to save it. 
Then we have the trained model. It looks like this: 
 
This model is ready to be used for any Apple application that supports Core ML. If you already have an app that uses Core ML to classify images, you could simply replace the trained ML with this new one you just trained. 

### Reference
[1] PowerPoint Presentation - Introduction to Caltech-256. (2019). Retrieved from http://www.vision.caltech.edu/Image_Datasets/Caltech256/intro

[2] Creating an Image Classifier Model | Apple Developer Documentation. (2019). Retrieved from https://developer.apple.com/documentation/createml/creating_an_image_classifier_model

[3] Nayak, S. (2019). Train a Deep Learning Image Classifier using CreateML | Learn OpenCV. Retrieved from https://www.learnopencv.com/how-to-train-a-deep-learning-based-image-classifier-in-macos

[4] Kambampati, S. (2019). Introduction to Create ML: How to Train Your Own Machine Learning Model in Xcode 10. Retrieved from https://www.appcoda.com/create-ml/
