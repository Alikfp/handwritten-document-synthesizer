## About this fork

This fork focuses on improving the handwritten document synthetization aspect of the original repo.
I tried to keep the synthesizer as stand-alone as possible, so some files and code were relocated or removed.

These are the main modifications which were made (based on the version cloned on Apr 28, 2018):
- Added new distortions: elastic deformation and ink degradation.
- Modified existing distortions: spline interpolation, document noise, background blending.
- Added the option to disable distortions while still generating parameters (useful when using a fixed seed for the RNG).
- Added more options to text rendering (see comments in the code).
- Words and lines are now split using the text string and not the character bounding boxes (much more reliable).
- The synth can now generate a synthetic clone of a dataset if the necessary data is provided.
- The synth can now generate pages, lines and words at the same time.
- Everything should work with UTF-8 now (needs more testing)
- Misc bug fixes and code refactoring.

<sup>Note: this list is not a comprehensive changelog.</sup>

### Known issues
The following are the main known issues which need to be solved:
- When cloning a dataset, page width is not adjusted to text precisely because it can cause an error.

## Install dependencies
# LINUX
To run this code, you must have Python 2.7 installed.
You also need some libraries for text rendering:
```bash
sudo apt install libcairo2-dev libpango1.0-dev
```
After that, you need to install the python bindings for them:
```bash
sudo apt install python-gtk2
```
Finally, the following python packages are required:
```bash
sudo pip install Pillow matplotlib numpy opencv-contrib-python scikit-image scipy
```

# MAC OS
First install pango and cairo using brew
```bash
brew install pango
```
```bash
brew install cairo
```

then you need the python bindings, or else python will not be able to find the module. The relevant python binding is "pytgk", it cannot be installed through "brew" anymore, so download and install it from [here](http://sourceforge.net/projects/zero-install/files/PyGTK/2.24.0/org.pygtk.macosx.pkg/download)
## Usage

See the readme in the `synthesizer` and `IAM_utilities` folders for usage information.

