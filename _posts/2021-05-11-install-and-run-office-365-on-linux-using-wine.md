---
layout: post
title: "Install and Run Office 365 on Linux Using WINE"
categories: Linux
author: "Muhammad Naufal Hilmy Makarim"
---


![My Linux desktop (Zorin OS) running Office 365 through WINE]({{ site.post_img }}/2021-05-11-install-and-run-office-365-on-linux-using-wine/1.png)

_Before continuing, it is best if you read it at least once._

1.  Download WINE. [Click this](https://winehq.org/).

2.  Since I am using Zorin OS and it is an Ubuntu derivative, I use Ubuntu installation method.

    If you are using Debian 10, Ubuntu 18.04, or derivatives, you need to download FAudio, which is WINE dependency, because it is not available in distro's repository. [Download here](https://forum.winehq.org/viewtopic.php?f=8&t=32192).

    FAudio is available in the repository of Ubuntu 19.04 and later.

3.  Install WINE and FAudio (if needed).

4.  Create a WINEPREFIX folder with a 32-bit architecture only to isolate Office 365 from other Windows applications. This is necessary to prevent Office 365 failed to run in the future due to a conflict with any other Windows application dependency.To create it, run the following command on terminal:

    ```
    WINEPREFIX=$YOUR_PREFERRED_INSTALLATION_PATH WINEARCH=win32 winecfg
    ```

    Example:

    ```
    WINEPREFIX=~/.wine/office365 WINEARCH=win32 winecfg
    ```

    ![]({{ site.post_img }}/2021-05-11-install-and-run-office-365-on-linux-using-wine/2.png)

5.  On the "Wine configuration" dialog, select Windows 7 as "Windows Version". Do not use other Windows version!

6.  [Install winetricks](https://wiki.winehq.org/Winetricks). If you are using a Debian or Ubuntu derivative, you can install it by running the following command on terminal:

    ```
    sudo apt install winetricks
    ```

7.  Install Office 365 dependencies by running the following command on terminal:

    ```
    WINEPREFIX=$YOUR_PREFERRED_INSTALLATION_PATH WINEARCH=win32 winetricks msxml6 riched20 allfonts
    ```

    Example:

    ```
    WINEPREFIX=~/.wine/office365 WINEARCH=win32 winetricks msxml6 riched20 allfonts
    ```

8. Download Office 365 installation from [office.com](https://office.com). If you are using Linux, you will need to change your browser's user agent. If you are using chrome browser, you can change it by following these method:

    -   Open "Developer tools" or "Inspect element".
    -   Open "Network conditions".

        ![]({{ site.post_img }}/2021-05-11-install-and-run-office-365-on-linux-using-wine/3.png)

    -   Uncheck "Select automatically" then select "Chrome - Windows". Then reload the webpage.

        ![]({{ site.post_img }}/2021-05-11-install-and-run-office-365-on-linux-using-wine/4.png)

9. You will see "Install Office". Click it then click "Other installation".

    ![]({{ site.post_img }}/2021-05-11-install-and-run-office-365-on-linux-using-wine/5.png)

10. Click "View applications & devices"

    ![]({{ site.post_img }}/2021-05-11-install-and-run-office-365-on-linux-using-wine/6.png)

11. Select 32-bit version then click "Install Office". The download process will start immediately.

    ![]({{ site.post_img }}/2021-05-11-install-and-run-office-365-on-linux-using-wine/7.png)

12. To install Office 365, run the following command on terminal:

    ```
    WINEPREFIX=$YOUR_PREFERRED_INSTALLATION_PATH WINEARCH=win32 wine $YOUR_OFFICE365_DIRECTORY
    ```

    example:

    ```
    WINEPREFIX=~/.wine/office365 WINEARCH=win32 wine ~/Download/OfficeSetup.exe
    ```

    Please be patient as the process will take a very long time. You can view the percentage by clicking the icon in the Wine System Tray window.


<br>
After the installation process is complete, you can run Office 365 like any other native Linux application. There may still be some functionality that is not working, but the basic functionality is still usable. Enjoy :)
