# Face-Recognition

Face Recognition.

The objective of the project was to take an Image as input and figure out if it is one of the the authorized person in our database and if so who?

The FaceNet model takes a lot of data and a long time to train, so I have used a pre-trained Inception model that uses a 96\*96 dimensional RGB images and outputs a matrix of dimension 128\*1.

By using 128 Neuran fully connected layer as its last layer, the model ensures that output is an encoding vector of size 128. I have then compiled the model using triplet loss.

Triplet Loss tries to push the encodings of two images of the same person close together while pulling the encodings of two images of different persons further apart. 

After that, I have created a database that maps the name of the person with his/her 128 dimensional encoding of there face. 

Now to recognise the person I computed encodings of the target image and searched the database for the encoding with minimum distance from the target encoding which must be greater than decided threshold distance.

