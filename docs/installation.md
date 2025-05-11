# Installation

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

Follow these steps to install OCTRON: 

1. Make sure **ffmpeg** is installed on the system. Some packages rely on it.<br>
    - `ffmpeg -version`
    - If the command fails for some reason, make sure you install ffmpeg first
    ??? note "Installing ffmpeg"
        === "Windows"
            ### Step 1: Download FFmpeg
            1. Open your web browser and go to the official FFmpeg download page: [FFmpeg Download](https://ffmpeg.org/download.html).
            2. Under the "Get packages & executable files" section, click on the Windows logo.
            3. You will be redirected to a page with various builds. Click on the link for the "Windows builds from gyan.dev".
            4. On the gyan.dev page, scroll down to the "Release builds" section and download the "ffmpeg-release-essentials.zip" file.

            ### Step 2: Extract the FFmpeg Zip File
            1. Once the download is complete, navigate to the folder where the zip file was downloaded.
            2. Right-click on the `ffmpeg-release-essentials.zip` file and select "Extract All...".
            3. Choose a destination folder to extract the files to (e.g., `C:\ffmpeg`) and click "Extract".

            ### Step 3: Add FFmpeg to the System Path
            1. Open the extracted folder (e.g., `C:\ffmpeg`) and navigate to the `bin` directory.
            2. Copy the path to the `bin` directory (e.g., `C:\ffmpeg\bin`).

            3. Open the Start menu, search for "Environment Variables", and select "Edit the system environment variables".
            4. In the System Properties window, click on the "Environment Variables..." button.
            5. In the Environment Variables window, find the "Path" variable under the "System variables" section and select it. Click "Edit...".
            6. In the Edit Environment Variable window, click "New" and paste the path to the `bin` directory (e.g., `C:\ffmpeg\bin`). Click "OK" to close all windows.

            ### Step 4: Verify the Installation
            1. Open the Command Prompt by pressing `Win + R`, typing `cmd`, and pressing `Enter`.
            2. In the Command Prompt, type `ffmpeg -version` and press `Enter`.
            3. If FFmpeg is installed correctly, you should see the version information for FFmpeg.

            ### Step 5: Use FFmpeg
            You can now use FFmpeg from the Command Prompt or any other terminal on your Windows system.

            ### Troubleshooting
            If you encounter any issues during the installation process, make sure to:

            - Double-check that the path to the `bin` directory is correct.
            - Ensure that the path is added to the "System variables" section, not the "User variables" section.
            - Restart your Command Prompt or computer to apply the changes.
        === "MacOS"
            On MacOS you can use [homebrew](https://formulae.brew.sh/formula/ffmpeg) and `brew install ffmpeg`
        === "Linux"
            You know what to do (:

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
