# Bird_Drone_Detection

# Bird and Drone Detection

 This projects aim is to creat is program that will detect if there are birds or drones in the sky. This could be used for checking if it is safe for planes to takeoff or land, lowering the possibility of plane incidents. 

![add image descrition here](direct image link here)

## The Algorithm

The algorithm takes a large dataset of images of birds and drones as well as the sky in order to train the jetson nano to dectect brids and drones in the sky. Then is it tested using an image that has not been part of the dataset, to check its accuracy. 

## Running this project

1. Connect PuTTY to your computer and VSCode using SSH with your IP. 
2. Download jetson inference using github with link: `https://github.com/dusty-nv/jetson-inference.git`
3. Go to jetson-inference/python/training/classification/data using `cd` command
4. Creat a new directory called "bds" using this command: `mkdir bds`
5. Dowload images and dataset of birds and drones off of `https://www.kaggle.com/datasets/imbikramsaha/drone-bird-classification` and the sky images off of google search.
6. Go back to the jetson-inference directory using `cd ../` command 
7. Activate docker using this command: `./docker/run.sh
8. In docker, go to jetson-inference/python/training/classification using `cd` command
9. In the classificiation file, run this code to start training the program: `python3 train.py --model-dir=models/bds data/bds` (Choose the amount of epochs using `epochs=<the number you want>`

[View a video explanation here](video link)
