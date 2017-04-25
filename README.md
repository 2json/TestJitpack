# TestJitpack

[![](https://jitpack.io/v/gdky005/TestJitpack.svg)](https://jitpack.io/#gdky005/TestJitpack) [![Build Status](https://travis-ci.org/gdky005/TestJitpack.svg?branch=master)](https://travis-ci.org/gdky005/TestJitpack) [![CircleCI](https://circleci.com/gh/gdky005/TestJitpack/tree/master.svg?style=svg)](https://circleci.com/gh/gdky005/TestJitpack/tree/master)

# Travis CI 协议问题解决方案
http://stackoverflow.com/questions/37615379/travis-ci-build-doesnt-work-with-android-constraint-layout

# 存档链接
http://www.jianshu.com/p/2935b96d3059

TestJitpack


# Travis CI 和 Circle CI 遇到 android 协议解决办法

### Circle CI
machine:
  environment:
      ANDROID_HOME: /usr/local/android-sdk-linux
      
dependencies:
  pre:
    - mkdir -p "$ANDROID_HOME/licenses"
    - echo -e "\n8933bad161af4178b1185d1a37fbf41ea5269c55" > "$ANDROID_HOME/licenses/android-sdk-license"
    - echo -e "\n84831b9409646a918e30573bab4c9c91346d8abd" > "$ANDROID_HOME/licenses/android-sdk-preview-license"
    
### Travis CI
language: android

android:
  licenses:
      - android-sdk-license-.+
      - '.+'

before_install:
  - mkdir "$ANDROID_HOME/licenses" || true
  - echo -e "\n8933bad161af4178b1185d1a37fbf41ea5269c55" > "$ANDROID_HOME/licenses/android-sdk-license"
  - echo -e "\n84831b9409646a918e30573bab4c9c91346d8abd" > "$ANDROID_HOME/licenses/android-sdk-preview-license"
  
  

