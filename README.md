# Shapesorter

This is a tutorial following https://agray3.github.io/2016/11/29/Demystifying-Data-Input-to-TensorFlow-for-Deep-Learning.html

# Demystifying data input to TensorFlow for Deep Learning

to get this working follow these steps

1. Create the rectangles and triangles by running createShapes.py
2. Move 1/4 of the traning data to the corosponding validate folder

	$ mv data/train/squares/data3*  data/validate/squares/.
	
	$ mv data/train/triangles/data3*  data/validate/triangles/. 

3. Convert our images to TensorFlow TFRecord format.

	$ cd data/
	
	$ python build_image_data.py --train_directory=./train --output_directory=./  \\ \
	--validation_directory=./validate --labels_file=mylabels.txt   \\ \
	--train_shards=1 --validation_shards=1 --num_threads=1
	
3. now you can run shapesorter.py
	you can change simpleModel variable true to use a simple model and and False for convolutional neural network
