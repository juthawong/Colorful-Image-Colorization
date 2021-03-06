# Colorizing Images
A deep learning approach to colorizing images, specifically for Pokemon.

The current model was trained on screenshots taken from Pokemon Silver, Crystal,
and Diamond, then tested on Pokemon Blue Version. Sample results below.

![test_1](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_3.png?raw=true)
![test_1](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_3_output.png?raw=true)

## Basic Training Usage
`python train.py --help`

`-c --checkpoint_dir <str> [path to save the model]`

`-b --batch_size     <int> [batch size]`

`-d --data_dir       <str> [path to root image folder]`

`-n --normalize      <str> [y/n normalize training images]`


You can use this with some sample training images provided in `images/train`.
Run `python train.py -c model_dir/ -b 5 -d ../images/train/ -n n` to start training
on the small amount of sample images. This will create a directory called `model_dir`
in the `train` folder. If you get an error about CUDA running out of memory, reduce
the batch size.

The files in the `images/train` folder are as follows:
- image_1.png: The original image extracted from the video (after possible cropping)
- image_1_resized.png: The original image resized to (160,144).
- image_1_resized_gray.png: The original image resized to (160,144) and converted to grayscale.

The training attempts to obtain the resized color image when given the resized gray image.

## Evaluating on Images
I've included a trained model in the `models/` directory that you can run your own images on.
You can either run the model on one image or a folder of images. For one image, run `eval_one.py`
and pass it the model and the image as parameters. To run it on multiple images, run `eval.py`
and pass it the model and the folder to the images. `eval.py` will save your images in the 
`output` folder, where as `eval_one.py` will save them in the current directory. Examples:

`python eval_one.py ../models/generation_2/training/ my_image.png`

`python eval.py ../models/generation_2/training/ ../images/testing/`

## Training your own data

There are scripts included to help create your own dataset, which is desirable because
the amount of data needed to obtain good results is a good amount. The results below
were trained on about 50,000 images.

The easiest method to obtain images is to extract them from Youtube walkthrough videos of
different games. Given that you have a folder with videos 

`videos/`

`video_1.mp4`
  
`video_2.mp4`
   
`...`


use `extract_frames.sh` to extract images from each video. Just pass it the folder containing images.

Depending on if the video had a border around the game, you may need to use `crop_images.py` to crop
out the border. There are comments in the script you can uncomment to view the image before it crops
all of them to be sure the cropping is correct.

Finally, use `convert_images.py` to create resized and gray images for training.

## Results

![test_1](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_3.png?raw=true)
![test_1](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_3_output.png?raw=true)

![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_5.png?raw=true)
![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_5_output.png?raw=true)

![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_1.png?raw=true)
![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_1_output.png?raw=true)

![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_2.png?raw=true)
![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_2_output.png?raw=true)

![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_4.png?raw=true)
![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_4_output.png?raw=true)

![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_6.png?raw=true)
![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_6_output.png?raw=true)

![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_7.png?raw=true)
![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_7_output.png?raw=true)

![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_8.png?raw=true)
![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_8_output.png?raw=true)

![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_9.png?raw=true)
![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_9_output.png?raw=true)

![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_10.png?raw=true)
![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_10_output.png?raw=true)

![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_11.png?raw=true)
![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_11_output.png?raw=true)

![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_12.png?raw=true)
![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_12_output.png?raw=true)

![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_13.png?raw=true)
![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_13_output.png?raw=true)

![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_14.png?raw=true)
![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_14_output.png?raw=true)

![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_15.png?raw=true)
![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_15_output.png?raw=true)

![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/testing/test_16.png?raw=true)
![test_2](https://github.com/cameronfabbri/Colorful-Image-Colorization/blob/master/images/resized/output/test_16_output.png?raw=true)

