---
layout: page
title: FAQ
include_in_header: true
---

* TOC
{:toc}

## What is this?

UTM is an app for running other operating systems on your iPhone or iPad. It is **not** for running iOS on other systems. This allows you, among other things, to run Windows or Linux on your iOS device at a usable speed.

## Does this require a jailbreak?

UTM is supported on iOS 11, 12, and 13 for non-jailbroken devices through sideloading. UTM requires a jailbreak to use on iOS 14.

## Do you require a computer to use this on iOS and iPadOS?

Unfortuanately, yes. As of September, 11, 2023, you need a device capable of running Windows, macOS, or directly running Linux only once via SideStore. Windows and macOS are reccomended above Linux as of now due to it's official support for SideServer. Windows 10 is required if you use Windows, and macOS 10.15 "Catalina" for macOS. If you use ChromeOS, as of now, there is no way to get iPhones to connect with the virtual Linux container, as ChromeOS's virtualization software only supports 8-bit USB identifiers to connect with any virtual machine. You also require both a Lightning to USB-A or USB-C cable (we only reccomend Apple genuine cables, as counterfiet ones may not support data transfers or damage your device), and a USB-A or a USB-C port on your computer. Most Cloud PCs are not supported for this reason. If you are in the European Union, support for sideloading without a computer will soon not be required. If you do not own a computer outside of the European Union, including the United States of America, you need to buy a computer, or move to the European Union. Note that if you live in the United Kingdom, Turkey, Russia, Ukraine, Belarus, Alibania, or Yugoslavia, you will not be able to sideload without a computer.


## How do I sideload an app?

Sideloading allows you to load unofficial apps on your iOS device. If you have a free Apple account, you must re-sign the app every 7 days. If you have a paid ($99/year) Apple developer account, you must re-sign the app every year. For more information checkout the [install page]({% link _pages/install.md %}).

## How does UTM work?

The majority of the work is done by [qemu](https://www.qemu.org). Because iOS devices lack hardware virtualization support, we cannot use the KVM accelerator and instead use the TCG accelerator which does dynamic code translation and JIT compilation. UTM also includes a [SPICE](https://www.spice-space.org) client written for Metal. This connects with the SPICE server in qemu and allows for some para-virtualization as the QXL graphics driver running on the guest OS can send low-level draw commands directly to Metal APIs.

For more in-depth information on the changes made to qemu for JIT to work on iOS, check out [this document](https://github.com/utmapp/qemu/blob/ios-support/docs/devel/ios.rst).

## What does UTM mean?

UTM stands for [Universal Turing Machine](https://en.wikipedia.org/wiki/Universal_Turing_machine), a machine capable of computing any computable sequence, as described by Alan Turing in his seminal paper "On Computable Numbers, with an Application to the Entscheidungsproblem".

## What are the limitations?

The lack of hardware virtualization on Apple A-chips means that even for ARM code we must re-compile it with JIT. Therefore performance would never reach the levels possible with KVM. There is also no support for GPU virtualization so that means no DirectX or OpenGL. This makes most modern games non-playable.

## How can I contribute?

We need all the help we can get! We need both people to work on improving/optimizing the qemu backend as well as people working on the UI and front-end. You can check out our [Github](https://github.com/utmapp/) and join our [Discord](https://discord.gg/UV2RUgD).

## Where do I get support?

Check out [https://docs.getutm.app](https://docs.getutm.app)
