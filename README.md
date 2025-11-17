# Rust OpenCL MVP
Reference for [https://github.com/cogciprocate/ocl](https://github.com/cogciprocate/ocl) minimum viable product.
# Setup
Arch Linux's `pacman` package manager is used for these instructions. Equivalent packages should exist for other Linux distros.
## Install the ICD Loader
```
sudo pacman -S ocl-icd opencl-headers
```

## Install the Vendor Driver
### NVIDIA
```
sudo pacman -S opencl-nvidia
```
## AMD
```
sudo pacman -S rocm-opencl-runtime
```
## Intel
Yes, Intel makes GPUs now
```
sudo pacman -S intel-compute-runtime
```

# Verify Install
```
clinfo
```

In my case, I have an AMD card.

If everything is correct, there should be at least one platform listed:
```
Number of platforms                               1
  Platform Name                                   AMD Accelerated Parallel Processing
  Platform Vendor                                 Advanced Micro Devices, Inc.
  Platform Version                                OpenCL 2.1 AMD-APP.dbg (3649.0)
  Platform Profile                                FULL_PROFILE
  Platform Extensions                             cl_khr_icd cl_amd_event_callback 
  Platform Extensions function suffix             AMD
  Platform Host timer resolution                  1ns

  Platform Name                                   AMD Accelerated Parallel Processing
```

And a corresponding GPU for that platform.
```
Number of devices                                 2
  Device Name                                     gfx1031
  Device Vendor                                   Advanced Micro Devices, Inc.
  Device Vendor ID                                0x1002
  Device Version                                  OpenCL 2.0 
  Driver Version                                  3649.0 (HSA1.1,LC)
  Device OpenCL C Version                         OpenCL C 2.0 
  Device Type                                     GPU
  Device Board Name (AMD)                         AMD Radeon RX 6700 XT
  ...
```