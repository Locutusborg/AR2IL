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

