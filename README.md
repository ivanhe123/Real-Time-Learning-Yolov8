# Real-Time-Learning-Yolov8
Real Time Learning is not the normal concept that others see on most papers on the internet.
Infact, it is just what it means, a kind of code that allows an AI to learn (train a model) when it is running.

For this particular example, the code will run the task of detecting a face while training.

First, while it finished detecting a face in one frame, a function will record the frame without annotation and also record the bbox into yolo_txt format: xywh (x=center of x of bbox/width of frame, y=center of y of bbox/hidth of frame, w=width of bbox/width of frame, and h=height of bbox/height of frame).

Note: the width of frame in opencv-python is frame.shape[1], while the height of fram is frame.shape[0]. 

a variable will change by one after a record has been made, if the variable is bigger than some constant, for example, 300, the function will start a training function.

The training function is a thread that can run parallel with the detection system.

After the training is complete, the model will be automaticly replaced by the newest one.

If you wanted to see the .pt model you just trained, open runs/detect/ after training, open the last folder (meaning this will be the last model you trained before another train starts), open the weights folder, and find best.pt.
