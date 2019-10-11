﻿
![](./doc/picture/introduction/TencentOS_tiny_log.png)

[![license](http://img.shields.io/badge/license-BSD-blue.svg)](https://github.com/Tencent/TencentOS-tiny/blob/master/LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-blue.svg)](https://github.com/Tencent/TencentOS-tiny/pulls)
[![Build status](https://travis-ci.org/Tencent/TencentOS-tiny.svg?branch=master)](https://travis-ci.org/Tencent/TencentOS-tiny)
# Introduction to TencentOS Tiny

[TencentOS tiny](https://cloud.tencent.com/product/tos-tiny) is a real-time operating system developed by Tencent for the Internet of Things. It features low power consumption, low resource consumption, modularity, security and reliability, and can effectively improve the development efficiency of IoT terminal products. TencentOS tiny provides a streamlined RTOS core that can be tailored and configurable for rapid migration to a wide range of mainstream MCUs (such as the full range of STM32) and module chips. Moreover, based on the RTOS kernel, it provides a wealth of IoT components, and internally integrates mainstream IoT protocol stacks (such as CoAP/MQTT/TLS/DTLS/LoRaWAN/NB-IoT, etc.), which can help IoT terminals and services to quickly access Tencent. Cloud Internet of Things platform.


## 1、The software architecture of TencentOS tiny

![](./doc/picture/introduction/TencentOS_tiny_Architecture.png)

TencentOS tiny main architecture diagram, from bottom to top, mainly includes:

**CPU libs** ：The CPU IP core architecture supported by TencentOS tiny,currently supports ARM Cortex M0/3/4/7.

**Drive management** ：Including board support package (BSP, mainly developed and maintained by MCU chip manufacturers), hardware abstraction (HAL, mainly provided by TencentOS tiny, to facilitate adaptation and porting of different chips), device drivers (Drivers, such as Wi-Fi, GPRS Drivers for modules such as LoRa).

**kernel** ：The TencentOS tiny real-time kernel includes tasks management, real-time scheduling, time management, interrupt management, memory management, exception handling, software timers, linked lists, message queues, semaphores, mutex locks, event flags, and more.

**IoT protocol stack**：TencentOS tiny provides lwip, AT Adapter, SAL layer, supports different network hardware, such as Ethernet, serial Wi-Fi, GPRS, NB-IoT, 4G and other communication modules. A commonly used IoT protocol stack, such as CoAP and MQTT, is provided on the TCP/IP network protocol stack to support the terminal service to quickly access Tencent Cloud.

**Security framework**：TencentOS tiny provides a complete security solution to ensure data transmission security and device authentication security for IoT terminals. The DTLS and TLS security protocols provided by the security framework reinforce the transport layer of COAP and MQTT to ensure that the IoT terminal implements secure authentication and data encryption when docking Tencent Cloud. In addition, for the low-resource terminal hardware, the security framework also provides Tencent. The key authentication scheme of the cloud IoTHub ensures that resource-constrained devices can also achieve device security certification to a certain extent.

**Component framework**：TencentOS tiny provides a series of components such as file system, KV storage, ad hoc network, JS engine, low-power framework, device framework, OTA, and debugging toolchain for users to choose according to business scenarios.

**Open API (in planning and development)**：TencentOS tiny will provide open API functions on the protocol middleware and framework layer, which is convenient for users to call the middleware function, so that users do not need to pay much attention to the implementation of middleware, quickly connect to Tencent cloud, realize the cloud demand on the terminal business, and expect the maximum degree. Reduce the development cycle of the terminal IoT product and save development costs.

**examples**：TencentOS tiny provides sample code, module test code, etc., which is convenient for users to refer to.

## 2、TencentOS tiny优势

### (1).Small size

Minimum kernel: RAM 0.6KB, ROM 1.8KB  
Typical LoraWAN and Sensor Applications: RAM 3.3KB, ROM 12KB 
### (2).Low power consumption
Minimum sleep power consumption as low as 2 uA
Support for peripheral power management framework
### (3).Rich IoT components
Integrate mainstream IoT protocol stack
Multiple communication module SAL layer adaptation framework;
Support FOTA 
Provides easy-to-use end-cloud API to accelerate user service access to Tencent Cloud
### (4).Reliable security framework
Diversified security grading scheme
Balanced security requirements & cost control
### (5).Good portability
Highly decoupled core and IoT components, providing a standard adaptation layer
Provide automated migration tools to improve development efficiency
### (6).Convenient debugging means
Provide cloudized last screen debugging
The fault scene information is automatically uploaded to the cloud platform, which is convenient for developers to debug and analyze.

## 3、TencentOS tiny and partners are committed to building the IoT ecosystem

![](./doc/picture/introduction/Partners.png)

TencentOS tiny currently supports mainstream MCUs such as STM32, NXP, Huada Semiconductor, National Technology, GD32, Nordic, and TI. Two sets of official custom development board designs have been completed, supporting the full range of STM32 NUCLEO official evaluation board kernel migration. TencentOS tiny will work together with partners to provide better IoT terminal software solutions for IoT terminal manufacturers, facilitating the rapid access of various IoT devices to Tencent Cloud, and jointly expanding the IoT ecosystem to better support smart cities, smart water meters, and smart homes. , smart wear, car networking and other industrial applications.

# TencentOS tiny code directory
- [TencentOS tiny代码目录说明](./doc/TencentOS-tiny-代码目录说明.md)

# TencentOS tiny reference documentation
## 1、Porting guide
- [TencentOS tiny移植指南（KEIL版本）](./doc/TencentOS-tiny-porting-keil.md)
- [TencentOS tiny移植指南（IAR版本）](./doc/TencentOS-tiny-porting-iar.md)
- [TencentOS tiny移植指南（GCC版本）](./doc/TencentOS-tiny-porting-gcc.md)

## 2、Development guide
- [TencentOS tiny内核开发指南](./doc/4.TencentOS-tiny开发指南.md)
- [TencentOS tiny API参考](./doc/5.TencentOS-tiny-SDK文档.md)
- [TencentOS tiny对接腾讯云IoTHub开发指南](./doc/8.TencentOS-tiny对接腾讯云IoTHub开发指南.md)

# TencentOS tiny opensource license
* TencentOS tiny follow [BSD-3 Open source license agreement](LICENSE)


# The IoT platform TencentOS tiny  support 
TencentOS tiny can support IoT terminal devices and services for fast access to Tencent Cloud IoT Platform [IoT Explorer](https://cloud.tencent.com/product/iotexplorer)。

TencentOS tiny combines Tencent Cloud IoT development platform IoT Explorer, which has built up the ability to connect communication chips to cloud development. Together with the largest LoRa network in China, Tencent has completely opened up from chip communication development, network support services, and physical equipment. Defining management, data analysis and multi-scenario application development and other full-chain IoT cloud development service capabilities, redefining the IoT development model, helping multi-mode multi-mode multi-mode low threshold access to Tencent cloud services. As an IoT infrastructure construction service provider, Tencent will continue to build an open IoT ecosystem and promote the sound development of the Internet of Things.

# TencentOS tiny Quick Start Reference
TencentOS tiny joint partner (Nanjing Houde IoT) designed a custom development board, as shown below:
![](./doc/picture/introduction/EVB_MX.png)

- [TencentOS tiny custom development board introduction page](http://www.holdiot.com/product/showproduct.php?id=8) ,Developers can quickly learn based on custom development boards, click to download reference documentation
- [TencentOS-tiny Custom Development Board Getting Started Guide](./doc/TencentOS-tiny定制开发板入门指南.pdf)

# Contribution code
* 1.  Under the Fork TencentOS tiny open source project under your own GitHub account;
* 2.  Clone a TencentOS tiny code locally according to your needs;
* 3.  After you modify or add a new function, push to the remote branch of your fork;
* 4.  Create a pull request and submit a join request to the official TencentOS tiny development branch;
* 5.  The TencentOS tiny R&D team will periodically review the code and pass the test.

# Join the TencentOS tiny official QQ technology exchange group

Scan the QR code plus group, please note the TencentOS tiny developer, the staff will review according to the notes:

![](./doc/picture/introduction/qq.png)

# Third-party developer contributions

Thanks to the contribution of CSDN blog expert Jiejie

Based on the wildfire stm32f103 development board to transplant TencentOS tiny routines, source code analysis, video explanation.

## Simple to get started

- [超详细的 TencentOS tiny 移植到STM32F103全教程](https://blog.csdn.net/jiejiemcu/article/details/101034426)

## Deep source analysis

- [【TencentOS tiny学习】源码分析（1）——task](https://blog.csdn.net/jiejiemcu/article/details/99618912)

- [【TencentOS tiny学习】源码分析（2）——调度器](https://blog.csdn.net/jiejiemcu/article/details/99665883)

- [【TencentOS tiny学习】源码分析（3）——队列](https://blog.csdn.net/jiejiemcu/article/details/99687678)

- [【TencentOS tiny学习】源码分析（4）——消息队列](https://blog.csdn.net/jiejiemcu/article/details/99781093)

- [【TencentOS tiny学习】源码分析（5）——信号量](https://blog.csdn.net/jiejiemcu/article/details/100052643)

- [【TencentOS tiny学习】源码分析（6）——互斥锁](https://blog.csdn.net/jiejiemcu/article/details/100056641)

- [【TencentOS tiny学习】源码分析（7）——事件](https://blog.csdn.net/jiejiemcu/article/details/100492219)

- [【TencentOS tiny学习】源码分析（8）——软件定时器](https://blog.csdn.net/jiejiemcu/article/details/101846089)

## Example Code

- [【TencentOS tiny学习】例程（0）——hello world](https://github.com/jiejieTop/TencentOS-Demo/tree/master/hello-world)

- [【TencentOS tiny学习】例程（1）——task](https://github.com/jiejieTop/TencentOS-Demo/tree/master/01-task)

- [【TencentOS tiny学习】例程（2）——队列](https://github.com/jiejieTop/TencentOS-Demo/tree/master/02-queue)

- [【TencentOS tiny学习】例程（3）——消息队列](https://github.com/jiejieTop/TencentOS-Demo/tree/master/03-msg_queue)

- [【TencentOS tiny学习】例程（4）——信号量](https://github.com/jiejieTop/TencentOS-Demo/tree/master/04-sem)

- [【TencentOS tiny学习】例程（5）——互斥锁](https://github.com/jiejieTop/TencentOS-Demo/tree/master/05-mutex)

- [【TencentOS tiny学习】例程（6）——事件](https://github.com/jiejieTop/TencentOS-Demo/tree/master/06-event)

- [【TencentOS tiny学习】例程（7）——软件定时器](https://github.com/jiejieTop/TencentOS-Demo/tree/master/07-timer)

- [【TencentOS tiny学习】例程（8）——内存池](https://github.com/jiejieTop/TencentOS-Demo/tree/master/08-mmblk)

- [【TencentOS tiny学习】例程（9）——内存堆](https://github.com/jiejieTop/TencentOS-Demo/tree/master/09-mmheap)


## Video tutorial

- [【TencentOS tiny学习】视频汇总](https://www.bilibili.com/video/av70478596?from=search&seid=10160676184801585522)
- [【视频】01-初识TencentOS tiny](https://www.bilibili.com/video/av70478596/?p=1)
- [【视频】02-TencentOS tiny基础知识](https://www.bilibili.com/video/av70478596/?p=2)
- [【视频】03-TencentOS tiny移植](https://www.bilibili.com/video/av70478596/?p=3)
- [【视频】04-TencentOS tiny任务-1](https://www.bilibili.com/video/av70478596/?p=4)
- [【视频】05-TencentOS tiny任务-2](https://www.bilibili.com/video/av70478596/?p=5)
- [【视频】06-TencentOS tiny队列-1](https://www.bilibili.com/video/av70478596/?p=6)
- [【视频】07-TencentOS tiny队列-2](https://www.bilibili.com/video/av70478596/?p=7)
- [【视频】08-TencentOS tiny消息队列](https://www.bilibili.com/video/av70478596/?p=8)
- [【视频】09-TencentOS tiny信号量-1](https://www.bilibili.com/video/av70478596/?p=9)
- [【视频】10-TencentOS tiny信号量-2](https://www.bilibili.com/video/av70478596/?p=10)
- [【视频】11-TencentOS tiny互斥锁-1](https://www.bilibili.com/video/av70478596/?p=11)
- [【视频】12-TencentOS tiny互斥锁-2](https://www.bilibili.com/video/av70478596/?p=12)
- [【视频】13-TencentOS tiny互斥锁-3](https://www.bilibili.com/video/av70478596/?p=13)
- [【视频】14-TencentOS tiny事件-1](https://www.bilibili.com/video/av70478596/?p=14)
- [【视频】15-TencentOS tiny事件-2](https://www.bilibili.com/video/av70478596/?p=15)
- [【视频】16-TencentOS tiny软件定时器-1](https://www.bilibili.com/video/av70478596/?p=16)
- [【视频】17-TencentOS tiny软件定时器-2](https://www.bilibili.com/video/av70478596/?p=11)
- [【视频】18-TencentOS tiny软件定时器-3](https://www.bilibili.com/video/av70478596/?p=18)

## Related PPT doc
- [【TencentOS tiny学习】视频PPT](https://github.com/jiejieTop/TencentOS-Demo/tree/master/PPT)

