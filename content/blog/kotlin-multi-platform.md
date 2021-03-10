---
title: "Kotlin MultiPlatform"
date: 2020-07-13T12:49:27+06:00
featureImage: images/blog/kt.png
postImage: images/single-blog/feature-image.jpg
---

The most obvious benefit of cross-platform mobile development: cost savings. Simply put, using the same tools to simultaneously build an app for iOS and Android will save you time and money over using different toolsets to build those app versions sequentially.

Cross-platform systems such as Flutter, Xamarin and React Native will let you avoid a lot of duplicated work and might only cost you, say, between 1.2x and 1.5x more than if you hadn’t pursued cross-platform development. While you can’t use all of the same code for both iOS and Android, you certainly save hours and aggravation when you duplicate non-platform-specific code, and then just add platform-specific code for cameras and other features.

JetBrains, the outfit behind Resharper, Kotlin and other software IDEs, is now stepping into this battle with their own offering: Kotlin Multiplatform Mobile (KMM). This is important because Google recently named Kotlin a first-class language for Android development, which means its popularity for building mobile apps will surely increase in coming years.

One of the big rumors behind Google’s push is that the search-engine giant is looking for replacements for Java, which has long powered Android development, but has also become legally problematic thanks to Oracle. Whatever the truth to those rumors, Kotlin’s Java compatibility makes it ultra-useful for anyone who’s used to Java but wants a new platform that’s more concise, with safer code (see this comparison to get an idea of the differences).

In 2017 Google added Kotlin as a development language for Android. Right when the Oracle-Google case was heating up in court, Google went one step further gave Kotlin that aforementioned “first class” designation.

All of this brings us to Kotlin Multiplatform Mobile, which allows Kotlin developers to write just once for iOS and Android.
Android Studio

In order to use Kotlin Multiplatform Mobile, you must install Android Studio (version 4.1 or higher). If you’re building for iOS, you’ll also need to install Xcode (version 11.3 or higher). Fortunately, there’s a handy step-by-step guide for installing the KMM plugin.

(A quick side note about Android Studio, if you’re totally new to it: it’s free, and based on the community edition of JetBrains’ IntelliJ IDEA. If you’re looking for a Java IDE, IntelliJ IDEA is worth your attention, but keep in mind that you’ll need to install some plugins and other stuff for optimum Android app development. Android Studio also has a lot of documentation, so if you’re new to Android/Java/Kotlin, you’ll have the resources you need to actually learn stuff.)

KMM’s New Project Wizard features project templates and tools designed to make your life easier. However, I found it was a bit rough around the edges on a Windows PC. Android Studio will only let you create a KMM project if you have the right plugin installed and enabled; even if you do everything right, though, you still receive error messages to the effect that the KMM plugin “is supposed to work on macOS only.”

At first, I thought it was something I’d done, but I see on the Kotlin bug tracker site that I’m not the first to pick up on this question about the KMM plugin. The advice for handling this issue? Create a project from the samples. That’s quite a workaround. Fortunately, despite the error messages, KMM development via Windows is very much possible.

Running my cross-platform app also took some work. As I use Hyper-V on my PC, VT-x is turned off, which means you can’t install the Intel HAXM that speeds up Android emulation on an Intel PC. Flutter development in Android Studio, strangely, doesn’t suffer from this!
Kotlin Multiplatform Mobile: Worth Trying?

KMM was only released as alpha in August 2020, so perhaps we should expect the odd glitch. And it’s not as if the iOS development environment makes it easy to develop without a Mac, thanks to Apple’s restrictions; even Xamarin, which provides a Windows iOS simulator, requires you to pair your PC to a Mac to build iOS apps. So if you want to build effective cross-platform apps via KMM, get very familiar with Xcode and macOS.

Despite all that, can KMM surf Kotlin’s rising popularity to become a much-in-demand cross-platform app builder? Well, JetBrains has done pretty well with Kotlin; but when it comes to cross-platform products, KMM will have to take market-share from the ultra-popular Flutter, Xamarin, and React Native. In order to do that, KMM will probably need a bit more polished.
