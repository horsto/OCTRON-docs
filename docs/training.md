# Train model
Once you have a decent number of annotated frames, you are ready to train your model. This is done in the **Train model** tab.

IMAGE: annotated overview of this section

## Generate training data
OCTRON needs to generate data to train the model on, i.e. it takes you annotations and splits them into a training dataset and a testing dataset. This enables it to evaluate how well the training is going by comparing its predictions against the ground truth. First, consider these options:

- **Prune:** select this if there are frames in which it is likely that not all of your objects were annotated despite them all being present. By selecting this option OCTRON will 'prune' the annotated frames so that only those where all labels are present are used. Otherwise you will be counteracting the training (the model will think that if one object isn't annotated in a certain frame, but the other objects are, this means the un-annotated object isn't there)
- **Overwrite:** if you've generated a training dataset before, selecting this option will overwrite the existing one (recommended)

Once you click *Generate*, you can observe the progress in the two progress bars:

- **label:** details
- **label and split:** details

## Train
Once the training data has been generated, OCTRON is ready to train your model. There are a few settings to consider:

- **Choose model:** choose which model to use

    ??? question "Which model should I choose?"
        - **YOLO11m-seg:** details 
        - **YOLO11l-seg:** details 
        - **YOLO11x-seg:** details

- **Img. size:** choose which image size OCTRON should work with

    ??? question "Which image size should I choose?"
        - **x:** details 
        - **y:** details 

- **Epochs:** decide how many epochs the model should train for. The higher the number, the longer the training will take, but if no significant improvement is detected across x number of epochs then the training will automatically stop

- **Save period:** decide how often (in number of ephocs) to save the training results

- **Resume:** details <br>
- **Overwrite:** details <br>
- **Tensorboard:** details

Click *Train*