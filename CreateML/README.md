# ML with CreateML

[Back to home directory](https://github.com/valentinsilvera/ai-basics)

## How to run locally

1. Download or clone the repo
2. Open ai-basics/CreateML/SnacksVision/SnacksVision.xcodeproj on Xcode
3. Go to "Signing and Capabilities"
4. Change "Team" to your own Apple Developer Account (required)
5. Select a device to run (on the top, this project requires a physical device)
6. Run the project (Cmd+R)

## About CreateML
Create ML is a framework from Apple for ML. It allows the creation and training of machine learning models. The trained models can be easily integrated into own apps with Core ML. The models can be used, for example, for image, text or speech recognition.

### Technologies

- Vision: The Vision framework performs face and face landmark detection, text detection, barcode recognition, image registration, and general feature tracking. Vision also allows the use of custom Core ML models for tasks like classification or object detection. Vision comes already integrated in iOS 11+ so the models created using VisionFeaturePrint_Scene are only a few KB in size, as they only include the logistic regressions done on top of the parent model.

## The Model

CreateML(with Vision Feature Print) extracts around 2000 freatures per image.
![](https://github.com/valentinsilvera/ai-basics/blob/main/Assets/ml2.jpeg)

CreateML is extremely easy to use. Here's how I trained the model:

![](https://github.com/valentinsilvera/ai-basics/blob/main/Assets/createml3.png)
First, I loaded the dataset (~5000 images for training, ~1000 for validation and ~1000 for testing), each in directories named after the class they belong (ie: Apple, Oranges, Pretzels). I selected 25 iterations (or epochs), and augmentation. Augmentation allows to make a bigger dataset than the one we have by modifying the images. I selected Crop and Rotate, which applies these filters to copies of the original images.

![](https://github.com/valentinsilvera/ai-basics/blob/main/Assets/createml1.png)
![](https://github.com/valentinsilvera/ai-basics/blob/main/Assets/createml2.png)
The model took a few minutes to train and it came out with: Training accuracy 96,6%. Validation accuracy 89%. Size: 446 KB
It's important to note that this is a process called transfer learning. Vision has already several models trained with hundreds of GBs of data, and then does transfer learning on top of that. This is the most realistic scenario, as we will see, training without a huge dataset is not feasible.

[Back to home directory](https://github.com/valentinsilvera/ai-basics)

[Next: Turi Create](https://github.com/valentinsilvera/ai-basics/tree/main/TuriCreate)
