MultiKinect
===========

This repository contains codes where I explore multiple kinect cameras connected to one computer. README

<h1> Installing python wrappers from libfreenect </h1> 

        Firstly install the libfreenect library. See the manual build under OSX. 
        i.e. http://openkinect.org/wiki/Getting_Started#Manual_Build_under_OSX


<h2> Installing python plugins </h2> 

After installing the libfreenect libraries, as mentioned above. Just goto the /libfreenect/wrappers/python and then run the command: 
        
        sudo python setup.py install 

This will install everything you need. 
Note, there are a lot of plugins that might be required, so install the things on the fly. However, below I will try to enter the libraries required. 
libusb from : http://sourceforge.net/projects/libusb/



<h2> Parallel usage with pyusb </h2> 

If you also want to use pyusb to play with the Kinect, you will need libusb-1.0.8 (it seems). Install it via homebrew and then define the _lib variable before finding the usb device:

Output: 

        from ctypes import *
        import usb.core
        import usb.utils

_lib = CDLL('/usr/local/Cellar/libusb/1.0.8/lib/libusb-1.0.dylib') # That's the location homebrew puts the libusb libraries
dev = usb.core.find(idVendor=0x045e, idProduct=0x02B0)

<h2> Read more here: </h2> 

        http://openkinect.org/wiki/Getting_Started#OS_X

