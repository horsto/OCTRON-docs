# Generate annotation data

How to create annotations
IMAGE: annotated overview of this section

## Model selection


??? question "Which model should I choose?"
    **SAM2 Base Plus:** details <br>
    **SAM2 Tiny:** details <br>
    **SAM2 Small:** details <br>
    **SAM2 Large:** details


## Layer controls
### Types
- Shapes:
- Points:


### Labels
- Create: 
- Remove: 

**Suffix:** add a number here if you want to label multiple instances of the same thing (e.g. you have two LEDs and want to label them separately as *LED 1* and *LED 2*)

Click *Create* <br>
**Reset:** details

<video width="100%"  loop muted>
  <source src="../assets/videos/tutorial/3__load_model_add _annotationlayers-fast.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

Start annotating

<video width="100%"  loop muted>
  <source src="../assets/videos/tutorial/4__oneclickannotations-fast.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

Switch annotation type
<video width="100%"  loop muted>
  <source src="../assets/videos/tutorial/5__changing_annotationlayermode-fast.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

## Parameters
**Opening kernel radius:** details

## Batch prediction
**Skip:** the number of frames you want to skip before the labels are predicted on a frame

Click ▶️ to predict the next frame <br>
Click *15 frame* to predict 15 frames in a row (this will also skip the number of frames specified under *Skip* between each predicted frame)

<video width="100%"  loop muted>
  <source src="../assets/videos/tutorial/6_batchpredict-fast.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video> 