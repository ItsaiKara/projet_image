# Mask detection using Yolov5
Final Project of the Image analysis course, Østfold University College \
Tyfenn Eloy & Guillaume Prébot
# Usage
You can either run the two .ipy files or run the jupyter notebook. \
Alternatively, here's our google colab that we used for the project : \
https://colab.research.google.com/drive/136P4Rw4B2a_SBRZLVr9JO4dg8N9bNyhc?usp=sharing \
If you want to execute the two script, you'll need to have ipython, for both scripts use line and cell magic. \
We did not try to run those on Windows, but due to the fact that the scripts use bash commands, we assumed that they're not functionnal in a Windows environment.
#### Training
To train the model run the following command at the root of the project folder :
```console
ipython training.ipy
```
If you got a W&B account, feel free to use it to visualize the results, otherwise just skip it when asked to. \
The default epoch is set to 50, you can change this by editing the line 295 :
```py
!python3 train.py --img 640 --batch 32 --epochs 50 --data data/data.yaml --cfg models/custom_yolov5s.yaml --weights yolov5s.pt --name yolov5s_results  --cache
```
#### Detection
To start a detection, run the following command at the root of the project folder :
```console
ipython detection.ipy
```
This will launch a face mask detection on the test images of the dataset and then plot you the result on two random images from the test set. \
Once you've closed the results, it'll then launch a webcam detection for a real time face mask detection on yourself. To stop it, you can simply ctrl + c in your terminal, the result will be saved in `yolov5/runs/detect`

# Weight & Biases results
Here's the Weights & Biases report on a 100 epochs run : \
https://wandb.ai/gprebot/YOLOv5/reports/Face-Mask-Detection--VmlldzoyMDUwMzU4?accessToken=4icxj889m3jzxlnr5wj7d5vefzjypgjf6ygux6uq2kfta2wj693l642r3s4420gh 
