---
layout: post
title: "Project and Control Linux Desktop from Android through VNC Using Vino"
categories: Linux
author: "Muhammad Naufal Hilmy Makarim"
---


![My Linux (Zorin OS) projected and controlled by my Android]({{ site.post_img }}/2021-05-11-project-and-control-linux-desktop-from-android-through-vnc-using-vino/1.png)

Linux distributions that come with GNOME desktop environment (Debian, Ubuntu, etc.) will have Vino as default VNC (Virtual Network Computing) server. So we will use it _Before continuing, it is best if you read it at least once._

1.  Open GNOME Settings.

    ![]({{ site.post_img }}/2021-05-11-project-and-control-linux-desktop-from-android-through-vnc-using-vino/2.png)

2.  Click "Sharing".

3.  Turn the toggle ON.

4.  Click "Screen Sharing".

    ![]({{ site.post_img }}/2021-05-11-project-and-control-linux-desktop-from-android-through-vnc-using-vino/3.png)

5.  Adjust "Screen Sharing" settings according to your preference.

    ![]({{ site.post_img }}/2021-05-11-project-and-control-linux-desktop-from-android-through-vnc-using-vino/4.png)

6.  To avoid problems caused by the incompatibility of the encryption used by Vino, we need to disable the encryption with the following command:

    ```
    gsettings set org.gnome.Vino require-encryption false
    ```

    After doing this, the connection to the Vino server becomes unencrypted making it insecure. It is not recommended to use it when on a public network.

    Now we have finished the setup on the Vino server. Next, we need to install VNC viewer on the Android device. So far there are two applications that I recommend, that is:

    - [VNC Viewer for Android](https://play.google.com/store/apps/details?id=android.androidVNC) by androidVNC team + antlersoft
    - [VNC Viewer - Remote Desktop](https://play.google.com/store/apps/details?id=com.realvnc.viewer.android) by RealVNC Limited

    The first one has a touch control feature so we don't need to control the mouse. The app is outdated but the features can be used well. The second is a more modern application but only has mouse controls. The touch control feature is only available for iOS. If you know of other good apps, let us know in the comments column below :)

7.  After downloading VNC viewer. We will be asked to enter our computer's IP address. To find out, we can run the following command in the terminal:

    ```
    hostname -I
    ```
    ![]({{ site.post_img }}/2021-05-11-project-and-control-linux-desktop-from-android-through-vnc-using-vino/5.png)

    Use the first IP address (192.168.1. *). If asked, use port 5900.

8.  Run the VNC viewer application that has been installed, adjust it to the VNC server configuration.

    ![]({{ site.post_img }}/2021-05-11-project-and-control-linux-desktop-from-android-through-vnc-using-vino/6.png)

9.  Click "Connect".


<br>
Now, your Linux desktop can be controlled from Android. You can also use stylus to write or draw on the touch screen of your Android. Enjoy :)
