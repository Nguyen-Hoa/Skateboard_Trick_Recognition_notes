# Skateboard Trick Detector/Classifier/Estimator/Predictor/Identifier

On creating a neural network based approach for identifying skateboard tricks from video. Classifying the different ways a skateboard rotates is a difficult task for anyone not familiar with the activity. Skateboard tricks happen quickly, which means the implementation needs to capture the fine details over a few hundred milliseconds to distinguish a trick. This requires a reasonably efficient model for higher resolution and longer length (amount of frames per second) clips.

## Dataset

-UCF-101, only recognizes skateboarding, not individual tricks

## Architectures

-[R2plus1D, 2018](literature/pdfs/R2plus1D.pdf)
-[FASTER, 2019](literature/pdfs/FASTER.pdf)
-[CSN, 2019](literature/pdfs/CSN.pdf)

## Approaches

Since there does not seem to be a dataset for skateboard tricks, this is a good place to start. The vast amount of skateboard clips on social media and youtube make finding them less of a problem. The first challenge we run into is how to structure the data:
1. Cut the clips for the duration of the trick
2. Cut then crop so that only the skateboard is visible for the duration of the trick
3. 

To decide, we will start by collecting clips for a couple tricks, namely the 

1. Ollie
2. Kickflip
3. Pop Shove-it

Since the stance of a skater will affect the data (the same trick for opposing stances rotate the opposite direction), we will separate skaters from goofy and regular stance.
