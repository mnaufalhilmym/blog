---
layout: post
title: "Run Specific Linux Application Using Dedicated NVIDIA GPU Card"
categories: Linux
author: "Muhammad Naufal Hilmy Makarim"
---

This method should work on all Linux distributions, such as Debian, Ubuntu, Arch, Manjaro, among others.

1.  Make sure your Linux desktop has PRIME Profile NVIDIA On-Demand.

    ![]({{ site.post_img }}/2021-05-12-run-specific-linux-application-using-dedicated-nvidia-gpu-card/1.png)

    You can also check it by running the command as shown below.

    ![]({{ site.post_img }}/2021-05-12-run-specific-linux-application-using-dedicated-nvidia-gpu-card/2.png)

2.  In short, you can run certain applications using a dedicated NVIDIA GPU by running the following command.
    ```
    __NV_PRIME_RENDER_OFFLOAD=1 __GLX_VENDOR_LIBRARY_NAME=nvidia $YOUR_APP
    ```

    example:
    ```
    __NV_PRIME_RENDER_OFFLOAD=1 __GLX_VENDOR_LIBRARY_NAME=nvidia android-studio
    ```

 3. To make sure that this method works, you can run the following command.
    ```
    __NV_PRIME_RENDER_OFFLOAD=1 __GLX_VENDOR_LIBRARY_NAME=nvidia glxinfo | grep vendor
    ```

    ![]({{ site.post_img }}/2021-05-12-run-specific-linux-application-using-dedicated-nvidia-gpu-card/3.png)

    If NVIDIA GPU is displayed, then the configuration is correct and the application can be run using dedicated NVIDIA GPU. 

4. If you want to find out more advanced features, [click here](http://us.download.nvidia.com/XFree86/Linux-x86_64/460.73.01/README/primerenderoffload.html).


<br>
Enjoy :)
