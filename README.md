# Gesture-Recognition-Model

Imagine you are working as a data scientist at a home electronics company which manufactures state of the art smart televisions. You want to develop a cool feature in the smart-TV that can recognise five different gestures performed by the user which will help users control the TV without using a remote.

The gestures are continuously monitored by the webcam mounted on the TV. Each gesture corresponds to a specific command:
    •	Thumbs up: Increase the volume
    •	Thumbs down: Decrease the volume
    •	Left swipe: 'Jump' backwards 10 seconds
    •	Right swipe: 'Jump' forward 10 seconds
    •	Stop: Pause the movie
    
Each video is a sequence of 30 frames (or images)


The popular architecture used to process videos is a natural extension of CNNs - a 3D convolutional network.

The training data consists of a few hundred videos categorized into one of the five classes. Each video (typically 2-3 seconds long) is divided into a sequence of 30 frames(images). These videos have been recorded by various people performing one of the five gestures in front of a webcam - similar to what the smart TV will use.



Model Summary with Adam optimizer:

Layer (type)                 Output Shape              Param #   
=================================================================
conv3d_5 (Conv3D)            (None, 30, 120, 120, 8)   656       
_________________________________________________________________
batch_normalization_4 (Batch (None, 30, 120, 120, 8)   32        
_________________________________________________________________
activation_5 (Activation)    (None, 30, 120, 120, 8)   0         
_________________________________________________________________
max_pooling3d_5 (MaxPooling3 (None, 15, 60, 60, 8)     0         
_________________________________________________________________
conv3d_6 (Conv3D)            (None, 15, 60, 60, 16)    3472      
_________________________________________________________________
batch_normalization_5 (Batch (None, 15, 60, 60, 16)    64        
_________________________________________________________________
activation_6 (Activation)    (None, 15, 60, 60, 16)    0         
_________________________________________________________________
max_pooling3d_6 (MaxPooling3 (None, 7, 30, 30, 16)     0         
_________________________________________________________________
conv3d_7 (Conv3D)            (None, 7, 30, 30, 32)     4640      
_________________________________________________________________
batch_normalization_6 (Batch (None, 7, 30, 30, 32)     128       
_________________________________________________________________
activation_7 (Activation)    (None, 7, 30, 30, 32)     0         
_________________________________________________________________
max_pooling3d_7 (MaxPooling3 (None, 3, 15, 15, 32)     0         
_________________________________________________________________
conv3d_8 (Conv3D)            (None, 3, 15, 15, 64)     18496     
_________________________________________________________________
activation_8 (Activation)    (None, 3, 15, 15, 64)     0         
_________________________________________________________________
dropout_4 (Dropout)          (None, 3, 15, 15, 64)     0         
_________________________________________________________________
max_pooling3d_8 (MaxPooling3 (None, 1, 7, 7, 64)       0         
_________________________________________________________________
flatten_2 (Flatten)          (None, 3136)              0         
_________________________________________________________________
dense_4 (Dense)              (None, 256)               803072    
_________________________________________________________________
dropout_5 (Dropout)          (None, 256)               0         
_________________________________________________________________
dense_5 (Dense)              (None, 128)               32896     
_________________________________________________________________
dropout_6 (Dropout)          (None, 128)               0         
_________________________________________________________________
dense_6 (Dense)              (None, 5)                 645       
=================================================================
Total params: 864,101
Trainable params: 863,989
Non-trainable params: 112

