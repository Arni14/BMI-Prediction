# BMI-Prediction
Scraping data from reddit r/ProgressPics and using it as training data to learn mappings from 2D human body images to their corresponding BMIs. 
Currently working on doing a few things:

1. Read in images and annotations from Reddit
2. Problem: Images are multi-sectioned, so need to figure out which image corresponds to which weight and then pair them
3. Use the pairs of (image, label) as a training set
4. Implement a deep neural network in PyTorch that learns mappings from image to BMI or weight
5. Run hyperparameter tuning on Tensorboard to actually figure out which HPs are good for this problem
6. Possibly investigate other architectures that are better suited for single variable prediction
