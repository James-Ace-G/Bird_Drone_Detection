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
5. In bds, creat four files, lables.txt, test, train val
6. Inside lables.txt, write three words in differnet lines: bird, drone, sky
7. In every test, train and val, creat three more files bird, drone, sky
8. Dowload images and dataset of birds and drones off of `https://www.kaggle.com/datasets/imbikramsaha/drone-bird-classification` and the sky images off of google search, and put them into their files.
9. Make sure that there are 10% images in test, 80% in train, and 10% in val.
10. Go back to the jetson-inference directory using `cd ../` command 
11. Activate docker using this command: `./docker/run.sh
12. In docker, go to jetson-inference/python/training/classification using `cd` command
13. In the classificiation file, run this code to start training the program: `python3 train.py --model-dir=models/bds data/bds` (Choose the amount of epochs using ` --epochs=<the number you want>`
14. Export program on to your computer using this code: `python3 onnx_export.py --model-dir=models/bds`
15. Exit docker using `Ctrl D`
16. Go to jetson-inference/python/training/classification and run these to lines of code: `NET=models/bds' and `DATASET=data/bds`
17. For testing, find and image online and download it to  jetson-inference/python/training/classification on nano.
18. Start testing by using this code: `imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/bds/<Folder Name>/<The File Name>.jpg <The name you want to save>.jpg`
19. In VSCode see the image that was outputed with the accuracy on the top left
[View a video explanation here](video link)
