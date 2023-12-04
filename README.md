# Suite2P GUI Modifications
Created for Wang Lab (Neuronal Mechanisms of Episodic Memory at Max Planck Florida Institute for Neuroscience)

Changed Suite2P user interface to add buttons and hotkeys for more rapid sorting of ROIs

The modifications require both replacing the gui2p.py file and uninstalling PyQt6 while keeping PyQt5. The current file has been lightly tested for compatibility with Suite2p v0.14.0.

### To make use of the enhanced interface for more rapid sorting of ROIs, do the following:
1. Install Suite2P v0.14.0. To ensure this works, you can do the following:
   - Open an anaconda prompt / command prompt with `conda` for python 3 in the path.
   - If existing installation of Suite2P exists, remove it and the environment with `conda env remove --name myenv --all`, replacing `myenv` with the conda environment that previously stored the Suite2P installation (likely `suite2p`).
   - Create a new conda environment with `conda create --name suite2p python=3.9`.
   - Activate the new conda environment by running 'conda activate suite2p'.
   - Install the GUI version of Suite2P with `python -m pip install suite2p[gui]`. If you're on a zsh server, you may need to use `' '` around the suite2p[gui] call: `python -m pip install 'suite2p[gui]'`. This also installs the NWB dependencies.
   - For additional dependencies, like h5py, NWB, Scanbox, and server job support, use the command `python -m pip install suite2p[io]`.
   - Run `python -m suite2p` to check the download and installation of Suite2P was successful. Running the command `suite2p --version` in the terminal will print the install version of suite2p.
2. Navigate to where Suite2P was installed (typically under `anaconda3\envs\suite2p` and then go to `\Lib\site-packages\suite2p\gui`.
3. Download the `gui2p.py` file from this repository. Replace the `gui2p.py` file from the Suite2P installation with the `gui2p.py` file downloaded from this repository.
4. Uninstall PyQt6 by running `python -m pip uninstall PyQt6`. Check PyQt5 is installed by running `python -m pip install PyQt5`.
5. Now, you should be able to reactive the `suite2p` environment by running `conda deactivate` followed by `conda activate suite2p`. Then to run Suite2P with the enhanced user interface, run `python -m suite2p`. On future start up of Suite2P, activate the conda environment for Suite2P by running `conda activate suite2p` followed by `python -m suite2p`. FOr more information on Suite2P, read the documentation found at https://suite2p.readthedocs.io/ 
