# Suite2P GUI Modifications
Created for Wang Lab (Neuronal Mechanisms of Episodic Memory at Max Planck Florida Institute for Neuroscience)

### Instructions for Use of Documented Changes
Changed Suite2P user interface to add buttons and hotkeys for more rapid sorting of ROIs. 
- The `[:Cell` button adds the ROI to the cells side and jumps to the next ROI.
- The `]:NotCell` button adds the ROI to the not cell side and jumps to the next ROI.
- The `\:back` button goes back one ROI.

Added second window to the Suite2p GUI that includes multiclass sorting of ROIs (from 1 - 10 classes). The sorting results are stored as a dictionary that can be saved via the `Save Dictionary` button on the pop-up window.
- Click the `Open Custom Sorting Window` button. A pop-up window should appear. Type the number of classes you would like to sort into (remember the labels for each number you decide to use).
- Clicking `Button 1` will label the current ROI to that class. The corresponding number key is a hotkey.
- You can go back an ROI using the main window.
- Use the save button to save the dictionary as a text file in the desired location.

The modifications require both replacing the gui2p.py file and uninstalling PyQt6 while keeping PyQt5. The `suite2pgui2p.py` file is from the latest release as of January 9, 2024. The `wanglabgui2p.py` is the modified file with the above functionality. The current file is compatibile with Suite2p v0.14.0.

### To make use of the enhanced interface for more rapid sorting of ROIs, do the following:
1. Install Suite2P v0.14.0. To ensure this works, you can do the following (from Suite2p docs):
   - Open an anaconda prompt / command prompt with `conda` for python 3 in the path.
   - If existing installation of Suite2P exists, remove it and the environment with `conda env remove --name myenv --all`, replacing `myenv` with the conda environment that previously stored the Suite2P installation (likely `suite2p`).
   - Create a new conda environment with `conda create --name suite2p python=3.9`.
   - Activate the new conda environment by running `conda activate suite2p`.
   - Install the GUI version of Suite2P with `python -m pip install suite2p[gui]`. If you're on a zsh server, you may need to use `' '` around the suite2p[gui] call: `python -m pip install 'suite2p[gui]'`. This also installs the NWB dependencies.
   - For additional dependencies, like h5py, NWB, Scanbox, and server job support, use the command `python -m pip install suite2p[io]`. Again, if you're on a zsh server, you may need to use `' '` around the suite2p[gui] call: `python -m pip install 'suite2p[io]'`.
   - Run `python -m suite2p` to check the download and installation of Suite2P was successful. Running the command `suite2p --version` in the terminal will print the install version of suite2p.
2. Navigate to where Suite2P was installed (typically under `anaconda3\envs\suite2p` and then go to `\Lib\site-packages\suite2p\gui`.
3. Download the `wanglabgui2p.py` file from this repository. Replace the `gui2p.py` file from the Suite2P installation with the `wanglabgui2p.py` file downloaded from this repository and rename `wanglabgui2p.py` as `gui2p.py`.
4. Uninstall PyQt6 by running `python -m pip uninstall PyQt6`. Check PyQt5 is installed by running `python -m pip install PyQt5`.
5. Now, you should be able to reactive the `suite2p` environment by running `conda deactivate` followed by `conda activate suite2p`. Then to run Suite2P with the enhanced user interface, run `python -m suite2p`. On future start up of Suite2P, activate the conda environment for Suite2P by running `conda activate suite2p` followed by `python -m suite2p`. For more information on Suite2P, read the documentation found at https://suite2p.readthedocs.io/

For help or more issues, submit an issue on the GitHub repository. We will do our best to keep this updated with the latest version of suite2p and create functionality with PyQt6 in the future.
