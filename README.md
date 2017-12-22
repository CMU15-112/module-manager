# module-manager
Troubleshoot the installation and importing of Python modules

###  Usage
To use `module_manager`, students just need to have `module_manager.py` in the same directory as the file they want to use `module_manager` with. If they're using Pyzo, they have to make sure to run their main file as a script (just like they do when they're using the linter).

Here's how a student who's using ```pyaudio``` might use `module_manager`.

``` Python
import module_manager
module_manager.review()

import pyaudio
```

If ```pyaudio``` is installed properly, the program will continue is normal. However, if there are errors importing ```pyaudio``` into their file, ```module_manager``` try to automatically install ```pyaudio``` to the version of Python that's being used to run the file, and help them troubleshoot if there are errors during installation.

### Commands
`module_manager.review()`
- Ensures that pip is installed for the current version of python, and automatically installs pip if not
- Reads the current file, finds all imported modules, and automatically pip installs any modules that aren't already installed

`module_manager.set_pip_name(module_name, pip_install_name)`
- Explicitly sets a pypi package name (like "opencv-python") to use when importing a module (like "cv2")

`module_manager.ignore_module(package_name)`
- Tells `module_manager` not to verify that a certain module is installed

### Pip Error Support
`module_manager` automatically elevates itself to an administrator when installing modules in order to avoid the following errors

- permission denied
- access is denied

and prints out OS specific troubleshooting tips when it encounters the following errors

- no matching distribution
- operation not permitted

If any other error is encountered, general troubleshooting tips are presented, and if there's a module manual for the module that failed to import, the link to the troubleshooting section of that module manual is displayed.
