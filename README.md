# Orientation-Matching
Machine Learning model to match CCTV images pointing to the same orientation

Having access to hundreds of thousands CCTV images, there was a need to tell apart the images pointing to the same orientation. Since the cameras can rotate on their axis, there can be multiple orientations to each of them. This machine learning model receives two images and returns a 1 when they indeed are the same orientation and 0 otherwise. Several indexes are computed for the ML model to analyze, they are: eucledian distance (ED) in both RGB and gray scale; wasserstein distance (also included its gray scale equivalent); ED and WD distances but in segments of said images. The segmentation of images is meant to cater the issue of ongoing traffic, visual disturbances, among other things, so there can be segments of the picture that tend to stay the same through time, such as buildings. Ideally, the program receives a picture each minute, comparing the new picture to the last one. When an orientation change is detected, the program will compare this new image to previously known orientations, where the average of several images per orientation is used. This means that this average image will contain a clean view of the orientation without any kind of disturbance, improving upon the accuracy of the model.
