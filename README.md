# module-help
Troubleshoot the installation and importing of Python modules

###  Usage
To use ```module_help```, students just need to have ```module_help.py``` in the same directory as the file they're want to use ```module_help``` with.

Here's how a student who's using ```pyaudio``` might use ```module_help```.

``` Python
from module_help import ensure_install
ensure_install('pyaudio')
import pyaudio
```

If ```pyaudio``` is installed properly, the program will continue is normal. However, if there are errors importing ```pyaudio``` into their file, ```module_help``` try to automatically install ```pyaudio``` to the version of Python that's being used to run the file, and help them troubleshoot if there are errors during installation.

### Features
```module_help.py``` can automatically
- install ```pip```
- install packages using ```pip```

It also outputs OS specific troubleshooting tips for the following errors
- permission denied (outputs an exact line to run in terminal to rerun the script with administrator privileges in the same version of Python)
- no matching distribution
- access is denied
- operation not permitted

If any other error is encountered, general troubleshooting tips are presented, and if there's a module manual for the module that failed to import, the link to the troubleshooting section of that module manual is displayed.
