---
layout: post
title: "Install Ruby Gems in openSUSE"
categories: Linux
author: "Muhammad Naufal Hilmy Makarim"
---


1.  Some packages in `devel_basis` pattern like `gcc`, `make`, etc. are needed so we should install it first.
    ```
    sudo zypper in -t pattern devel_basis
    ```

2.  After that, we should install `ruby-devel` package.
    ```
    sudo zypper in ruby-devel
    ```

3.  Then you can install any Ruby gems such as `jekyll`

<br>
Just it, hehe