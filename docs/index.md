<img src="assets/octron_logo.svg" alt="OCTRON Logo" width="82%" style="display: block; margin-left: auto; margin-right: auto; margin-top: -2rem; margin-bottom: 1rem;" />

OCTRON is a pipeline built on [napari](https://www.napari.org) that enables segmentation and tracking of animals in behavioral setups. It helps you to create rich annotation data that can be used to train your own machine learning segmentation models. This enables dense quantification of animal behavior across a wide range of species and video recording conditions. 

Octron is built on [napari](https://www.napari.org), [segment anything](https://segment-anything.com/), [yolo](https://www.ultralytics.com/) and 💜.


<video width="100%" autoplay loop muted>
  <source src="assets/videos/presentation_tomopt.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

## Installation

!!! note "Important Update Information"
    Just a heads up that there will be changes accumulating in the repo over these days. 
    So the first thing that you should do before playing with OCTRON (after you installed it successfully once, see below), should be:

    1.  Pull latest changes from main (in the github desktop app for example)
    2.  In your terminal, browse to your cloned repository folder on disk and then
    3.  `pip install . -U` for installing the new code and to update existing packages.

    If you ever mess up completely, do not despair! You can trash everything with:

    -   `conda deactivate` and then
    -   `conda env remove --name octron --yes`.

    Then you have to start with the conda *.yml* again (see steps explained below).

Follow these steps: 

1. Make sure **ffmpeg** is installed on the system. Some packages rely on it.<br>
    - `ffmpeg -version`
    - If the command fails for some reason, make sure you install ffmpeg first:
        - [step by step guide for windows](ffmpeg_windows.md)
        - on MacOS you can use [homebrew](https://formulae.brew.sh/formula/ffmpeg) and `brew install ffmpeg`
        - Linux users: You know what to do (:

2. Download miniconda. Open your web browser and go to the official Miniconda download page: [Miniconda Download](https://docs.conda.io/en/latest/miniconda.html). Download and execute the installer for your operating system (Windows, macOS, or Linux). Then restart your terminal.

3. Clone this repository and in a terminal (CMD on Windows) browse to the folder that you cloned it to (`cd "YOUR/CLONED/FOLDER"`)

4. Create a new Conda environment called "octron" with Python version 3.11:
    ```sh
    conda env create -f environment.yaml
    ```

!!! important "CUDA Users"
    **If you have a CUDA compatible graphics card in your computer, do *instead***:

    ```sh
    conda env create -f environment_cuda.yaml
    ```

    This will install the right PyTorch version automatically on Windows systems.

5. Activate the new environment:
    ```sh
    conda activate octron
    ```
6. Check the accessibility of GPU resources on your computer:
    ```sh
    python test_gpu.py
    ```
    This should show your graphics card, if it is correctly installed and accessible by pytorch. If this fails, you should correct this first, since OCTRON will not engage your GPU otherwise (and that is much slower).

## Usage
1. Activate the new environment:
    ```sh
    conda activate octron
    ```
2. Start the GUI:
    ```sh
    octron-gui
    ```
    ... and enjoy! 
    On first start this will take a long time to load, since all available models are downloaded once. But subsequent startups will be much quicker. 

<br>



!!! info "Attributions"
    - Interface button and icon images were created by user [Arkinasi](https://thenounproject.com/browse/collection-icon/marketing-agency-239829/) from Noun Project (CC BY 3.0)
    - Logo font: [datalegreya](https://datalegreya.figs-lab.com/?lang=en)
    - OCTRON training is accomplished via ultralytics: 
    ```{bibtex}
    @software{yolo11_ultralytics,
      author = {Glenn Jocher and Jing Qiu},
      title = {Ultralytics YOLO11},
      version = {11.0.0},
      year = {2024},
      url = {https://github.com/ultralytics/ultralytics},
      orcid = {0000-0001-5950-6979, 0000-0002-7603-6750, 0000-0003-3783-7069},
      license = {AGPL-3.0}
    }
    ```
    - OCTRON annotation data is generated via Segment Anything:
    ```{bibtex}
    @article{kirillov2023segany,
      title={Segment Anything},
      author={Kirillov, Alexander and Mintun, Eric and Ravi, Nikhila and Mao, Hanzi and Rolland, Chloe and Gustafson, Laura and Xiao, Tete and Whitehead, Spencer and Berg, Alexander C. and Lo, Wan-Yen and Doll{\'a}r, Piotr and Girshick, Ross},
      journal={arXiv:2304.02643},
      year={2023}
    }
    ```
    ```{bibtex}
    @inproceedings{sam_hq,
        title={Segment Anything in High Quality},
        author={Ke, Lei and Ye, Mingqiao and Danelljan, Martin and Liu, Yifan and Tai, Yu-Wing and Tang, Chi-Keung and Yu, Fisher},
        booktitle={NeurIPS},
        year={2023}
    }  
    ```