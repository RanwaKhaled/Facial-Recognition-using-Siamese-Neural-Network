# Facial-Recognition-using-Siamese-Neural-Network
This model is an implementation of the proposed Siamese Neural Network in the paper: <a href="chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://www.cs.cmu.edu/~rsalakhu/papers/oneshot1.pdf">Siamese Neural Networks for One-shot Image Recognition</a>
## Dataset used
For **negative** pictures:   
we used the <a href="https://vis-www.cs.umass.edu/lfw/">Labeled Faces in the Wild Dataset</a> which you can download from the link  
For **anchor** and **positive** pictures:  
around `200` pictures were taken of my face for each set - which are not uploaded for privacy reasons - in various positions, backgrounds, expressions, lighting and quality. These pictures can be replaced by the pictures of the person you want the model to identify
## Preprocessing
### Face detection
To give the model a better dataset, face detection and cropping were performed using the `OpenCV` face detector model to identify the face, crop it and save it in the intended directory `/data/folder`
### Image preprocessing
* **Normalization**: pixel values were normalized to a range of `0:255`
* **Resizing**: images were resized to `100x100x3` pixels
## Model structure
All layers are the same except the input layer which is *100x100* instead of *105x105*  
<img src="https://github.com/user-attachments/assets/75b91a10-0aa9-4d33-8184-755f55666bce">
## Training
The model was trained on 200 pictures of anchor, positive and negative images each and produced a **precision** of around **48%** and recall of **98%** 
## Live feed
According to the prediction speed, if it's too slow we'll need to take a frame using the webcam, close it and then perform the prediction. However is the model predicts quickly we can perform verification using live feed
