# Generate annotation data
To train your model you first need to show it what it should be tracking, i.e. you need to annotate the videos you want the model to train on. This is done in the **Generate annotation data** tab.

IMAGE: annotated overview of this section

## Model selection
Select the model you would like to use for your annotations and click *Load model*

??? question "Which model should I choose?"
    **SAM2 Base Plus:** details <br>
    **SAM2 Tiny:** details <br>
    **SAM2 Small:** details <br>
    **SAM2 Large:** details


## Layer controls
This is where you create the labels for the animals/item/structure you want to track. 

1. In the *Type...* drop-down menu, select the type of annotation you would like to use to label your structure. There are two types:

    - **Points:** often the simplest and fastest. The model will automatically label what it thinks you want to track based on what you left-click on and exclude anything you right-click on. 
    - **Shapes:** recommended for labelling items that are not so easily created with the 'Points' type. Here you make an outline around the item to show the model what it should label.

2. In the *Label...* drop-down menu, select *Create* to open a dialogue box where you can name your label and click *Add* to add it. 

    Option:

    - **Suffix:** add a number here if you want to label multiple instances of the same thing (e.g. you have two LEDs and want to label them separately as *LED 1* and *LED 2*)

3. Click the *Create* button to create your label. Two new layers will appear in the left hand section of OCTRON (more on that later)
4. Repeat steps 1-3 until you have all the labels you want

??? note "Removing unwanted labels"
    If you want to remove one of the labels you've created, then click *Remove* in the *Label...* drop-down menu and select the label you would like to remove

If at some point the model that is helping you annotate the videos is starting to slow down, you can click the **Reset** button to make it forget what it's learned so far and start fresh (more on that later).

<video width="100%"  muted controls>
  <source src="../assets/videos/tutorial/3__load_model_add _annotationlayers-fast.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

### Start annotating
1. 

<video width="100%"  muted controls>
  <source src="../assets/videos/tutorial/4__oneclickannotations-fast.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

Switch annotation type
<video width="100%"  muted controls>
  <source src="../assets/videos/tutorial/5__changing_annotationlayermode-fast.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

## Parameters
**Opening kernel radius:** details

## Batch prediction
**Skip:** the number of frames you want to skip before the labels are predicted on a frame

Click ▶️ to predict the next frame <br>
Click *15 frame* to predict 15 frames in a row (this will also skip the number of frames specified under *Skip* between each predicted frame)

<video width="100%"  muted controls>
  <source src="../assets/videos/tutorial/6_batchpredict-fast.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video> 