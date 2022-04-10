# AR2IL
Code repository of the AR2IL lab

## Content
1. [2D Neural Style Transfer](#neuralstyle)
2. [Tree-GAN](#treegan)

<a name="neuralstyle"></a>
## Neural Style Transfer
Neural style transfer is an optimization technique used to take two images—a content image and a style reference image (such as an artwork by a famous painter)—and blend them together so the output image looks like the content image, but “painted” in the style of the style reference image. 

This technique is outlined in <a href="https://arxiv.org/abs/1508.06576" class="external">A Neural Algorithm of Artistic Style</a> (Gatys et al.).

This is implemented by optimizing the output image to match the content statistics of the content image and the style statistics of the style reference image. 

In the colab notebook "2d-2d_Style_transfer.ipynb", deep learning is used to create a new image version of the primary image (content image) while using the style of the secondary image (style image).

### Guide to the colab notebook 2d-2d_Style_transfer.ipynb:

**Step 1:** Connect your google drive with this colab notebook by running the block below. You will have to give permission to connect by choosing the following options:

Connect to google drive -> Select your google account on which this colab notebook is saved -> click on "Allow"

**Step 2:** Import necessary libraries and supplementary files required by running the block below. Make sure that you have the 2 files: 'image_preprocess_functions.py' and 'neural_model.py' inside the same folder as your colab notebook.

To get the path of the files, you can simply:
1. Locate the file by clicking on the "folder" icon on the left section of your colab notebook.
2. To locate it, select drive -> MyDrive -> "your location of the notebook", till you see the name of your notebook in the format "your_notebook_name.ipynb".
3. To access the path, hover over your colab notebook name inside the branches, click on the 3 dots that appear on the right side of the name -> Select "Copy path".
4. Paste the path inside the following line: 

    sys.path.append(os.path.abspath("your_path"))
 
**Step 3:** Choose a style image and a content image and download them. Upload the images to your google drive (same google drive which has your colab notebook file) and copy the path of the images using the same procedure as the above. 

1. Copy the path of the content image on the 1st line below.
2. Copy the path of the style image on the 2nd line below.

##Visualize the input

**Step 4:** Using the load_img and imshow functions from the image_preprocess_functions.py (ip) file to display the content and style images.

In our case, our result is:


**Step 5:** Creating the neural network model with only the desired layers. Choosing layers for the content and style images separately. Here we have used the intermediate layers of [VGG19](https://keras.io/api/applications/vgg/#vgg19-function).

## Define content and style representations
Use the intermediate layers of the model to get the *content* and *style* representations of the image. Starting from the network's input layer, the first few layer activations represent low-level features like edges and textures. As you step through the network, the final few layers represent higher-level features—object parts like *wheels* or *eyes*. In this case, you are using the VGG19 network architecture, a pretrained image classification network. These intermediate layers are necessary to define the representation of content and style from the images. For an input image, try to match the corresponding style and content target representations at these intermediate layers.

**Step 6:** Creating the model and extracting the style and content.

**Step 7:** Defining the loss function that is to be reduced.

**Step 8:** Defining the optimizer and weighting parameters. Experiment with the following parameters to improve the output:

```
style_weight, content_weight, total_variation_weight
```

The `train_step` function defines each iteration of the program and the weights update based on the gradient w.r.t the loss defined in `style_content_loss`

**Step 9**: Now run a few steps to test. We test the neural network on a few steps first before proceeding for more steps as it is way quicker to get a result as compared to for more number of steps.

**Step 10**: If your neural network is working above, perform a longer optimization by taking more number of steps.



