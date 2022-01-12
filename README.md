# BMI-Prediction
Scraping data from reddit r/ProgressPics and using it as training data to learn mappings from 2D human body images to their corresponding BMIs. 
Currently working on doing a few things:

1. Use PRAW and Requests to read in all the images and the corresponding titles. 
2. Use some data cleaning to fix the titles and flair text to extract three things: (1) the height of the individuals in the picture, (2) the weight of their first image, and (3) the weight of their second image. Problem: this process is currently *inconsistent* since new images also break the format in many contexts. 
3. Next, we attempt to use a Histogram of Gradients method to extract images of individuals from multi-grid images. What this means is that each image in our collected raw dataset contains multiple pictures of the same individual at different times. However, we need to extract pairs of image, height/weight/bmi. As such, cropping the right subsection and then using it as training data is the goal here. This is *not complete* as yet.
4. Finally, we aggregate all of this data for the most recent and largest corpus we can extract. 
5. We build our network for predicting weight/bmi/height in the following way
6. a) Use a ResNet or DenseNet trunk and attach to it two or three dense layers of computation.
6. b) Train this with frozen parameters and then run K-fold cross validation across a set of HPs. 
6. c) Investigate more optimized architectures.
7. Build a UI that allows for users to input their images and predict their BMIs. 
8. Deploy this service using MLOps 0 (so no re-training) and measure statistics [Docker, Kubernetes, GCP.]
