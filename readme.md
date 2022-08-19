# ScoliosisDetective

This program uses machine learning to determining and reporting a confidence percentage that a patient may possibly exhibit symptoms of scoliosis after examinaing a picture of their back. If the confidence percentage is greater than or equal to 50%, the program will additionally provide a recommendation to get an official consultation with a doctor as well as a link to a Google search of scoliosis treatment facilities. If the confidence is less than 50%, a recomendation for official consultation will not be provided; however, a link to treatment facilities will also be attached, in case the user still has concerns.

Of course, this program, in its current stage, in no way serves as an official/unofficial diagnosis for scoliosis. However, with more research and advanced code, it could potentially increase the efficiency of scoliosis treatment by providing a way for people to determine if exhibit symptoms of scoliosis at home rather than waiting for a regularly scheduled check-up with a doctor while the condition potentially worsens. Scoliosis is best treated when it is discovered early, so if people have an easier, more accessible way to determine if they have the symptoms, it could potentially lessen the rates of scoliosis surgery and other treatments for more extreme cases.

## Algorithm

Utilizing NVIDIA's train.py model, the program must first train itself to identify and a determine a confidence percentage of scoliosis symptoms by observing numerous pictures of patients that have this condition (compiled in a dataset from Kaggle); once training is complete, the re-trained program will be stored and processed in an ONNX format. At this point, the user can download the image of their back to be classified and interpreted by the scoliosis_detective.py algorithm. The scoliosis_detective.py program not only utilizes imageNet to classify the image, but also produces the confidence percentage that the image falls into the 'catagory' of 'demonstrating scoliosis symptoms' through the employment of the re-trained ONNX model. If this confidience percentage is greater than or equal to 50%, a recommendation for an official consultation will be produced. Considering that no actual research has been conducted to prove the correlation between the percent confidence and liklihood of actually having the disease, the threshold for when to provide a recommendation is quite low; however, as the program is further developed and gains more experience, this threshold may increase.

## Materials Needed Prior to Running

1. Please have a Jetson Nano 2GB (and all of its included materials: e.g. USB power cable, etc.) that is connected to the internet.
2. Also be sure to have Resnet-18 and GoogleNet installed on your nano.
3. Please be sure to download imageNet from the jetson.inference library, loadImage from the jetson.utils library, as well as the argparse library, as the algorithm depends on these to run.
4. Additionally, please be sure to download the train.py model from the jetson-inference reposititory.lease also save this dataset compiled Kaggle in order to train the program: https://www.kaggle.com/datasets/akbotayelemessova/scoliosis-back-images-yes

## Directions

1. Please download the dataset from Kaggle on your nano
2. Then, runzip the file that was just downloaded.
3. Now, it's time to training the program using the train.py training script. (This process can take a very long time, but the long it runs, the more accurate the model should be.)
4. In order to run the re-trained model, please convert it into ONNX format using the onnx export script. (The model should be saved as resent18.onnx)
5. Please be sure to set the NET and DATASET variables depending on where you saved the model and data
6. Now,the user may run images through the model using the scoliosis_detective.py program. For instance, you may test it using this command: (ENTER COMMAND)

## Video Explanation

[View a video explanation here](video link)
