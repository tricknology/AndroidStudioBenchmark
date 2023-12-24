[![Build Status](https://travis-ci.org/mozilla-mobile/focus-android.svg?branch=master)](https://travis-ci.org/mozilla-mobile/focus-android)
[![codecov](https://codecov.io/gh/mozilla-mobile/focus-android/branch/master/graph/badge.svg)](https://codecov.io/gh/mozilla-mobile/focus-android/branch/master)

# AndroidStudioBenchmark (Firefox for Android)

`AndroidStudioBenchmark` contains a large codebase to measure the compilation time in `Android Studio`.

You are probably familiar with the following question:

"Should I buy an i5, i7, or even i9 processor for Android development? How much RAM would be enough? How SSD/M.2/NVMe influence build time?".

`AndroidStudioBenchmark` is initially created for my personal youtube channel
https://www.youtube.com/c/serhiyradkivskyi/about
to compare the performance of top laptops to choose the best system for `Android development`, because I hate to wait lot
of time waiting project to be built. And if we are buying laptop for 1000+ USD we want to be sure that it will perform 100% faster than our current machine. But online shops in there most - don't give ability to make real world
testing on your project to compare results. And most of tech reviewers describe laptops from designers/youtubers point of view,
not that much information from real software developers.

I believe the results will help developers to make the right cost/performance trade-off decision when choosing their next Mac/PC.
If you are interested - just continue reading and if you'll find this test useful - it would be very cool if you can share your result
and subscribe for my channel - it would be cool to have like minded audiance to share some more test on and get feedback on any
professional stuff.

# Results of Android Studio Performance testing:
Excel table: https://docs.google.com/spreadsheets/d/1AeeT_54b2VnovN4ikIsglh2Sc7U0bWxAarDKmGAJFtg/edit?usp=sharing

Videos with test results are in this youtube playlist:

https://www.youtube.com/playlist?list=PLzZmmGI65hndugkUKKwZF-r9GG0hFObZW

_Browse like no one’s watching. The new Firefox Focus automatically blocks a wide range of online trackers — from the moment you launch it to the second you leave it. Easily erase your history, passwords and cookies, so you won’t get followed by things like unwanted ads._

<a href="https://play.google.com/store/apps/details?id=org.mozilla.focus" target="_blank"><img src="https://play.google.com/intl/en_us/badges/images/generic/en-play-badge.png" alt="Get it on Google Play" height="90"/></a>
<a href="https://f-droid.org/en/packages/org.mozilla.klar/" target="_blank">
<img src="https://f-droid.org/badge/get-it-on.png" alt="Get it on F-Droid" height="90"/></a>

* [Google Play: Firefox Focus (Global)](https://play.google.com/store/apps/details?id=org.mozilla.focus)
* [Google Play: Firefox Klar (Germany, Austria & Switzerland)](https://play.google.com/store/apps/details?id=org.mozilla.klar)
* [Download APKs](https://github.com/mozilla-mobile/focus-android/releases)

# Testing steps:

# 1. Install Android Studio:
https://developer.android.com/studio

I was running test on `Android Studio 4.1.1`, but you can run tests on the latest version (just write the version you have).

I was using default settings while installation almost for all my tests.

`Intel HAXM` also must be installed if you run on Intel chip (it is installed by default with Android Studio).

I have set 4Gb RAM for my android virtual machine.

And please remember your Android SDK location.

# 2. Download API Level 28 SDK for this do next:
Go to: `Tools -> SDK Manager`

Choose Tab: `SDK Platforms`

Select: `Android 9.0 (Pie) API Level 28` and download it.

Close `Android Studio` after this.

# 3. Install JDK 17:
It has support for M1+ machines (aarch64)
https://www.oracle.com/java/technologies/downloads/#java17

I have installed: 
```
openjdk 17.0.9 2023-10-17
OpenJDK Runtime Environment Homebrew (build 17.0.9+0)
OpenJDK 64-Bit Server VM Homebrew (build 17.0.9+0, mixed mode, sharing)
```

# 4. Set "JAVA_HOME" path in your Environment variables (System variables):
For me it was: ` % echo $JAVA_HOME: /usr/bin/java`

# 5. Download AndroidStudioBenchmark repository:
https://github.com/tricknology/AndroidStudioBenchmark

This is a fork of opensource `Firefox browser for Android` (https://github.com/mozilla-mobile/firefox-android).

This is quite a big project (after all gradle modules downloaded it weights X+Gb).

You can download it as zip file to you fast SSD location.

Unzip it.

# 6. Restart you system.
Then make sure that no other programs/antivirus/browsers/big massive custom processes running.

Make sure that system is quite idle.

# 7. Open Android Studio.
Go to `File -> Open`: select Firefox Focus for Android project from your location and open it.

`Wait while all gradle files will be synced`, it can take up to 5-10 minutes.

# 8. Run next command to test speed of your machine doing next work:
Go to: `View -> Tools Windows -> Terminal`

Type command and press enter:


Windows:
  ```shell
  gradlew clean assembleDebug
  ```

MacOS/Linux:
  ```shell
  ./gradlew clean assembleDebug
  ```

Wait for assembling to complete. Run it 3 times in a row.

First time it will be your fresh build and it will take a little longer. Two next builds will be normal one.

After each build completes make a screenshot and save time result.

While system assembling watch for you `Task Manager` how `CPU` is processing, how much `RAM` is used,
it would be cool if you can watch CPU temperature with some tool like `AIDA`: https://www.aida64.com/downloads

# 9. Share results
If you want to share result of your test with the community, please send it to my email: serhiyradkivskiy@gmail.com and I will add it here:

In such format:

Letter theme: `AndroidStudioPerformanceTest`

`Notebook model`: HP 250 G5 15.6"

`OS`: Windows/Linux/MacOS

`Android Studio version`: 4.1.1/Arctic Fox 2020.3.1 Patch 4/Bumblebee/etc.

`CPU model`: Intel Core i5-7200U 2.5GHz

`RAM`: 8Gb DDR4

`Hard disk`: SSD M.2 256Gb KINGSTON SUV400S37240G (or HDD disk model)

`Test results`: 8:28min, 5:43, 5:37. And screenshots for them!! (Screenshots are needed for me to be 100% sure that results are not fake)

`Additional comments`: you can write here whenever you want: The CPU was running all time 100%, laptop was extremely hot
near the screen, ram was used for 80% etc, fans where running very hard etc..

`Contributor`: If you want to leave here a link to your youtube channel/linkedin/other contact info/alias etc - you are welcome, if not - it will be empty.


# 10. YouTubers and bloggers
You are free to use these results in your videos and articles as well as to run `AndroidStudioBenchmark` to compare Macs/PCs.

If you decide to record video with this test - it would be very cool if you could upload it to youtube!

Please make sure to add the link to this repository: https://github.com/yozhik/AndroidStudioBenchmark

Please name it: `Android Studio Perfomance Test on <You machine name>`.

Hashtag: `#AndroidStudioPerformanceTest`

So everyone could find it and watch and your audiance could repeat steps after you and compare their machine results.

The results show relative performance of Android Studio, compared to other machines running under similar conditions.


---


This repository hosts the Firefox for Android (Fenix), Focus on Android, and Mozilla Android Components projects.

# Firefox for Android

[![Task Status](https://firefox-ci-tc.services.mozilla.com/api/github/v1/repository/mozilla-mobile/firefox-android/main/badge.svg)](https://firefox-ci-tc.services.mozilla.com/api/github/v1/repository/mozilla-mobile/firefox-android/main/latest)
[![chat.mozilla.org](https://img.shields.io/badge/chat-on%20matrix-51bb9c)](https://chat.mozilla.org/#/room/#fenix:mozilla.org)

_Get the people-first browser that’s backed by a non-profit._

_It’s a new era in tech. Don’t settle for a browser produced by giant, profit-driven, data-hoarding tech companies. Firefox is the obvious choice for independent, ethical tech that respects your privacy and gives you more ways than ever before to tailor your internet experience exactly the way you want it._

Fenix (internal codename) is the all-new Firefox for Android browser, based on [GeckoView](https://mozilla.github.io/geckoview/) and [Mozilla Android Components](https://mozac.org/).

<a href="https://play.google.com/store/apps/details?id=org.mozilla.firefox" target="_blank"><img src="https://play.google.com/intl/en_us/badges/images/generic/en-play-badge.png" alt="Get it on Google Play" height="90"/></a>

Please file issues for Fenix (Firefox for Android) in [Bugzilla](https://bugzilla.mozilla.org/enter_bug.cgi?product=Fenix), selecting the corresponding component.

[Learn more about Firefox for Android](fenix/README.md)

# Firefox Focus for Android

[![Task Status](https://firefox-ci-tc.services.mozilla.com/api/github/v1/repository/mozilla-mobile/firefox-android/main/badge.svg)](https://firefox-ci-tc.services.mozilla.com/api/github/v1/repository/mozilla-mobile/firefox-android/main/latest)
[![chat.mozilla.org](https://img.shields.io/badge/chat-on%20matrix-51bb9c)](https://chat.mozilla.org/#/room/#focus-android:mozilla.org)

_Browse like no one’s watching. The new Firefox Focus automatically blocks a wide range of online trackers — from the moment you launch it to the second you leave it. Easily erase your history, passwords and cookies, so you won’t get followed by things like unwanted ads._

Firefox Focus provides automatic ad blocking and tracking protection on an easy-to-use private browser.

<a href="https://play.google.com/store/apps/details?id=org.mozilla.focus" target="_blank"><img src="https://play.google.com/intl/en_us/badges/images/generic/en-play-badge.png" alt="Get it on Google Play" height="90"/></a>

* [Google Play: Firefox Focus (Global)](https://play.google.com/store/apps/details?id=org.mozilla.focus)
* [Google Play: Firefox Klar (Germany, Austria & Switzerland)](https://play.google.com/store/apps/details?id=org.mozilla.klar)
* [Download APKs](https://github.com/mozilla-mobile/firefox-android/releases)

Firefox Focus (Android) issues should now also be filed in [Bugzilla](https://bugzilla.mozilla.org/enter_bug.cgi?product=Focus) under the Focus product.

[Learn more about Focus for Android](focus-android/README.md)

# Android components

[![Task Status](https://firefox-ci-tc.services.mozilla.com/api/github/v1/repository/mozilla-mobile/firefox-android/main/badge.svg)](https://firefox-ci-tc.services.mozilla.com/api/github/v1/repository/mozilla-mobile/firefox-android/main/latest)
[![chat.mozilla.org](https://img.shields.io/badge/chat-on%20matrix-51bb9c)](https://chat.mozilla.org/#/room/#android-components:mozilla.org)

_A collection of Android libraries to build browsers or browser-like applications._

A fully-featured reference browser implementation based on the components can be found in the [reference-browser repository](https://github.com/mozilla-mobile/reference-browser).

Please file issues for Android Components in the Fenix [Bugzilla](https://bugzilla.mozilla.org/enter_bug.cgi?product=Fenix), selecting the corresponding component.

[Learn more about Android Components](android-components/README.md)
