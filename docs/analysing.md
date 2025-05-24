# Analyze (new) videos
Once you have a trained model, you can use it to analyze new videos.

<img src="../assets/annotated_images/analysis.png"/>

## Add video files
Start by adding the video(s) you want to analyse in the *Add video files* section

## Create predictions from videos
Next, in the *Create predictions from videos* section you select how the videos you selected should be analyzed with the following options:

- **Choose model...:** choose which model you want to use from the drop-down menu. You can choose models from different stages of the training, e.g. the model that was saved after x number of epochs, or the best/last one that was saved (recommended).
- **Tracker...:** if you have annotated more than one object for a given label (e.g. artemia 1, artemia 2), a tracker needs to be used to help the model determine which is which across frames. Pick the one you prefer in this drop-down menu. If you only have one object per label, click the **1 subject** option.

    ??? question "Which tracker should I use?"
        Short answer: it probably doesn't matter which one you choose. You can find detailed information from the creators of each tracker here: 

        - **[ByteTrack](https://github.com/FoundationVision/ByteTrack)** 
        - **[BoT-SORT](https://github.com/NirAharon/BoT-SORT)** 

- **Videos:** select which video you want to analyze first.
- **Polygon sigma (x-y):** details
- **Conf. thres. (confidence threshold, 0-1):** the confidence threshold that should be used to determine which tracked frames to keep. There will likely be frames where the model is more confident that it has identified the right object than others. If the confidence threshold is set to 0.8 it means the model will only track frames where it is 80% certain that it has correctly identified a given object.
- **View results:** select this option if you want OCTRON to automatically open a new window where you can see the result of the analysis once it is complete.
- **Overwrite:** select this option if you've previously analysed the selected video and want to replace that analysis,
- **IOU (intersection over union, 0-1):** this threshold determines how much objects can overlap and still be considered separate objects. If this value is zero, then objects that have no overlap will be considered to be the same object, i.e. there is only one object.

Click *Predict*

OCTRON will now analyze your video(s) and show its progress via the progress bars (if analyzing multiple videos at once, then the first progress bar displays the progress of a single video while the second bar updates with the completion of each video) along with an estimate for when the analysis will finish.

