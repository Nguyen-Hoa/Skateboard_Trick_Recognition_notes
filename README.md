# Skateboard Trick Detector/Classifier/Estimator/Predictor/Identifier

On creating a neural network based approach for identifying skateboard tricks from video. Classifying the different ways a skateboard rotates is a difficult task for anyone not familiar with the activity. Skateboard tricks happen quickly, which means the implementation needs to capture the fine details over a few hundred milliseconds to distinguish a trick. This requires a reasonably efficient model for higher resolution and longer length (amount of frames per second) clips.

# Previous Work

### Datasets

- [UCF-50](https://www.crcv.ucf.edu/data/UCF50.php), only recognizes skateboarding, not individual tricks

### Architectures

- [R2plus1D, 2018](literature/pdfs/R2plus1D.pdf)
- [FASTER, 2019](literature/pdfs/FASTER.pdf)
- [CSN, 2019](literature/pdfs/CSN.pdf)

# Method

## Dataset

Since there does not seem to be a dataset for skateboard tricks, this is a good place to start. The vast amount of skateboard clips on social media and youtube make finding them less of a problem. We will structure the data collected like the UCF-50 dataset, which is labeled folders containing the videos.

### Dataset: Challenges
- Cut the clips for the duration of the trick
  - Leave some room before and after?
- Cut then crop so that only the skateboard is visible for the duration of the trick
  - This would fall under detection, we can instead draw a bounding box of the skateboard like in [UCF-Sports-Action dataset](https://www.crcv.ucf.edu/data/UCF_Sports_Action.php).

### Flip Tricks
We will start by collecting clips for a couple tricks.

1. Ollie
2. Kickflip
3. Pop Shove-it

Since the stance of a skater will affect how the trick is performed (the same trick for opposing stances rotate the opposite direction), we can separate skaters from goofy and regular stance. For early testing, we just want to see the model classify rotation of the board (pop shove it) versus flipping the board (kickflip) versus neither (ollie).

### Slides and Grinds
 I think slides and grind tricks will be easier to train than flip tricks because there is more context to work with (the ledge/rail).

1. Boardslide
2. 50-50
3. 5-0

