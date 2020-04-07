# pixy2_example
How to link to Pixy2 using CMake and C++

I bought a pixy2 to play with some computer vision, but it turned out now to be what I expected. Linking to the library and installing it was a bit of a pain, so I thought I'd create a repo in case you're interested in writing some C/C++ code for it. 

The following steps are taken straight out of: https://docs.pixycam.com/wiki/doku.php?id=wiki:v2:building_the_libpixyusb_example_on_linux
```
 sudo apt install git libusb-1.0-0-dev g++ build-essential 
 git clone https://github.com/charmedlabs/pixy2 
 cd pixy2/scripts && ./build_libpixyusb2.sh 
 ```
 
 Once libpixy2.a is built, they don't have an obvious way of installing the library to link to it. Inside this repo there's
 an `install_libpixyusb2.sh` script.
 
 ```
 cp pixy2_example/scripts/install_libpixyusb2.sh pixy2/scripts/
 cd pixy2/scripts/
 sudo ./install_libpixyusb2.sh
 ```
 This will install the headers and library file to `/usr/local/`
 
 Now we can link to the library. Take a look at the `cmake` and `examples` directory. 
 ```
 mkdir build
 cmake -DCMAKE_BUILD_TYPE=Release ..
 make -j6
 ```


