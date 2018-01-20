[FFmpeg-Android](http://hiteshsondhi88.github.io/ffmpeg-android/) [![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-FFmpeg--Android-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/925)
==============

* FFmpeg for Android compiled with x264, libass, fontconfig, freetype and fribidi
* Supports Android L
* [FFmpeg Android Library](https://github.com/hiteshsondhi88/ffmpeg-android-java)

Supported Architecture
----
* armv7
* armv7-neon
* x86

Instructions (tested on Ubuntu 16.04)
----
* Install Android NDK r13b (Important: must use NDK r13b)
  1. Get it from: https://developer.android.com/ndk/downloads/older_releases.html
* Set environment variable
  1. export ANDROID_NDK={Android NDK Base Path}
* Install nasm from scratch (required for building x264)
  1. Follow instructions from: http://www.linuxfromscratch.org/blfs/view/svn/general/nasm.html
* Run following commands to compile ffmpeg
  1. sudo apt-get --quiet --yes install build-essential git autoconf libtool pkg-config gperf gettext yasm python-lxml
  2. sudo apt-get --quiet --yes install zlibc zlib1g-dev zlib1g libfontconfig1-dev libx264-dev libpng12-dev libass-dev libavcodec-dev libavcodec-extra libavcodec-ffmpeg-extra56 libavformat-dev libavutil-dev libfreetype6-dev libexpat1-dev libvpx
  3. These *may* be helpful: sudo apt-get --quiet --yes install libfdk-aac-dev libopus-dev libtheora-dev libvorbis-dev libvpx-dev libssl-dev
  4. ./init_update_libs.sh
* REPLACE fribidi dir with a fresh clone of the repo using the build-cc branch using the following commands:
  1. mv fribidi/ fribidi-old
  2. git clone https://github.com/fribidi/fribidi
  3. cd fribidi; git checkout build-cc;
* REPLACE x264 dir with a fresh clone of the repo using the stable branch using the following commands:
  1. mv x264/ x264-old
  2. git clone https://github.com/mirror/x264.git
  3. cd x264; git checkout stable
* REPLACE ffmpeg dir with a fresh clone of the repo using the release/3.2 branch using the following commands:
  1. mv ffmpeg/ ffmpeg-old
  2. git clone https://github.com/FFmpeg/FFmpeg.git
  3. cd ffmpeg; git checkout release/3.2
* You *may* need to follow the same process to update fontconfig if you are running into compile issues.
* Build!
  1. ./android_build.sh
* If you run into issues compiling x86, follow advice from: https://github.com/WritingMinds/ffmpeg-android/issues/40#issuecomment-269427778
* To update submodules and libraries you can use ./init_update_libs.sh command
* Find the executable binary in build directory.
* If you want to use FONTCONFIG then you need to specify your custom fontconfig config file (e.g - "FONTCONFIG_FILE=/sdcard/fonts.conf ./ffmpeg --version", where /sdcard/fonts.conf is location of your FONTCONFIG configuration file).
* You can also download [prebuilt-binaries](https://github.com/hiteshsondhi88/ffmpeg-android/releases/latest) (Releases &gt; Downloads &gt; prebuilt-binaries[zip|tar.gz]).

License
----
  check files LICENSE.GPLv3 and LICENSE

HIRE US
--------
Get in touch with us - http://www.writingminds.com


[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/hiteshsondhi88/ffmpeg-android/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

