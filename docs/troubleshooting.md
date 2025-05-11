# Troubleshooting

Having problems? If you can't find a solution in the documentation or in the FAQs below, check if someone else has had the same problem on the [repository issues page](https://github.com/horsto/OCTRON-GUI/issues). If not, add it and we'll try to help! 

## Frequency asked questions
??? question "My GPU isn't engaged - what do I do?"
    If everything is slow and you notice that everything is running on your CPU instead of your GPU and you get this error: 
    ```
    “RuntimeError: could not run ‘torchvision::nms’ with arguments from the ‘CUDA’ backend." 
    ```
    then that means torchvision was installed without cuda support.
    Running this should solve the problem:
    ```
    pip install --force-reinstall torchvision==0.21.0 --index-url https://download.pytorch.org/whl/cu126
    ```

??? question "Some other issue"
    What to do
