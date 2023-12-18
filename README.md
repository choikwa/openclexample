Need OpenCL installed and then invoke CMake like below in build dir:

cmake -A x64 -DOpenCL_INCLUDE_DIR=<OpenCLPath>/include/ -DOpenCL_LIBRARY=<OpenCLPath>/lib/OpenCL.lib ..
