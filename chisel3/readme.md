chisel3 学习笔记

目录

# 1. chisel3介绍 


[![Join the chat at https://gitter.im/freechipsproject/chisel3](https://badges.gitter.im/freechipsproject/chisel3.svg)](https://gitter.im/freechipsproject/chisel3?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![CircleCI](https://circleci.com/gh/freechipsproject/chisel3/tree/master.svg?style=shield)](https://circleci.com/gh/freechipsproject/chisel3/tree/master)

Chisel is a new hardware construction language to support advanced hardware design and circuit generation.
The latest iteration of [Chisel](https://chisel.eecs.berkeley.edu/) is Chisel3,
which uses Firrtl as an intermediate hardware representation language.

Chisel3 releases are available as jars on Sonatype/Nexus/Maven and as tagged branches on the [releases tab](https://github.com/freechipsproject/chisel3/releases) of this repository.
The latest release is [3.1.3](https://github.com/freechipsproject/chisel3/releases/tag/v3.1.3).

Please visit the [Wiki](https://github.com/ucb-bar/chisel3/wiki) for documentation!

The ScalaDoc for Chisel3 is available at the [API tab on the Chisel web site.](https://chisel.eecs.berkeley.edu/api/latest/index.html)

## Overview
The standard Chisel3 compilation pipeline looks like:
- Chisel3 (Scala) to Firrtl (this is your "Chisel RTL").
- [Firrtl](https://github.com/ucb-bar/firrtl) to Verilog (which can then be passed into FPGA or ASIC tools).
- Verilog to C++ for simulation and testing using [Verilator](http://www.veripool.org/wiki/verilator).

# 2. chisel3 Ubuntu 18.04 linux安装
### (Ubuntu-like) Linux

1. Install Java
   ```
   sudo apt-get install default-jdk
   ```
1. [Install sbt](http://www.scala-sbt.org/release/docs/Installing-sbt-on-Linux.html),
    which isn't available by default in the system package manager:
    ```
    echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 642AC823
    sudo apt-get update
    sudo apt-get install sbt
    ```
1. Install Verilator.
    We currently recommend Verilator version 3.922.
    Follow these instructions to compile it from source.
    
    1. Install prerequisites (if not installed already):
        ```
        sudo apt-get install git make autoconf g++ flex bison
        ```
    
    2. Clone the Verilator repository:
        ```
        git clone http://git.veripool.org/git/verilator
        ```
    
    3. In the Verilator repository directory, check out a known good version:
        ```
        git pull
        git checkout verilator_3_922
        ```

    4. In the Verilator repository directory, build and install:
        ```
        unset VERILATOR_ROOT # For bash, unsetenv for csh
        autoconf # Create ./configure script
        ./configure
        make
        sudo make install
        ``` 
# 2. chisel3 基本语法
# 3. 第一个chisel3 FPGA 工程
# 4. Chisel3-FPGA-组合逻辑
# 5. Chisel3-FPGA-时序逻辑
# 6. Chisel3-FPGA-有限状态机
# 7. Chisel3-FPGA-FIR滤波器
# 8. Chisel3-FPGA-自适应滤波器
# 9. Chisel3-FPGA-神经网络
# 10. FPGA 加速器

