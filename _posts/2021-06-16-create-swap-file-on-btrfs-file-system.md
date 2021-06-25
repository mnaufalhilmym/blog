---
layout: post
title: "Create Swap File on Btrfs File System"
categories: Linux
author: "Muhammad Naufal Hilmy Makarim"
---


The following commands will create swap file on /swap/swapfile with size 2048MiB and blocksize (bs) 1MiB.


1.  Create a subvolume. This subvolume must be non-compressed and non-snapshotted. We will configure it in the next steps.
    ```
    sudo btrfs subvolume create /swap
    ```

2.  Create a zero length file
    ```
    sudo truncate -s 0 /swap/swapfile
    ```

3.  Set No_COW attribute
    ```
    sudo chattr +C /swap/swapfile
    ```

4.  Disable compression in file
    ```
    sudo btrfs property set /swap/swapfile compression none
    ```

5.  Create a swap file
    ```
    sudo dd if=/dev/zero of=/swap/swapfile bs=1M count=2048 status=progress
    ```

6.  Set permission to avoid vulnerability
    ```
    sudo chmod 600 /swap/swapfile
    ```

7.  Format to swap
    ```
    sudo mkswap /swap/swapfile
    ```

8.  Activate the swap file
    ```
    sudo swapon /swap/swapfile
    ```

9.  Add swap entry in the fstab configuration. Use vim, nano, etc to edit file in /etc/fstab. Add below configuration in the end of the file.
    ```
    /swap/swapfile    none    swap    defaults    0 0
    ```


<br>
Yapp.. It's done :)
