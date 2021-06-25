
# UXR Dock SDK

# Intro
* The UXR SDK is based on Google Cardboard plugin, it helps to create your own XR experiences for Rokid glass. It supports
essential XR features, such as:

    * Motion tracking
    * Stereoscopic rendering
    * Voice Recognition
    * Gesture Recognition

* With these capabilities you can build entirely new XR experiences, or enhance
existing apps with XR capabilities.

* This Unity SDK sample demonstrates the usage of the features mentioned above by some scenes:
     * HeadTracking scene  
   shows usage of 3 dof head tracking, and stereoscopic rendering for glass
     * VoiceRecog scene  
   shows usage of rokid voice recognition(offline voice instruction for Chinese and English)
	 * GestureRecog scene  
   shows usage of rokid gesture recognition(Four types of 2D gestures at present)

# Preparation
  * Hardware
    *  Rokid dock(supports Rokid Yidao Dock, system version 2.3.1-20210623-100003+) + Rokid glass(supports Rokid Air glass)
    *  Rokid X-Craft(RG-crown, system version 1.3.5-20210618-502103+)
  * Software
    *  Unity3D (2019.3.15f1 ~ 2020.1）
    *  JDK, Android SDK and NDK compatiable with Unity3D

# Get started

To get started with the UXR SDK Sample:

* Please read and follow the steps below  
 [Quickstart\_UXR\_Unity](./Quickstart_UXR_Unity_EN.md) 


# API reference

Please see the [UXR\_API](./UXR_API_EN.md)


# SDK Download
Unity SDK Sample download link:  
``https://ota-g.rokidcdn.com/toB/Rokid_Glass/SDK/UXR_SDK/Unity/forDock/RokidUXR_Unity_ForDock_1.5.3.zip``


# ChangeLog

| Version                      | Date       | Author               | Notes                             |
| --------                     | ---------- | -------------------- | ---------------------------       |
| UXR Dock SDK Unity v1.5.0    | 2021.04.16 | wenbo.wang@rokid.com | Initial commit                    |
| UXR Dock SDK Unity v1.5.2    | 2021.05.31 | wenbo.wang@rokid.com | add support for Air glass         |
| UXR Dock SDK Unity v1.5.3    | 2021.06.25 | wenbo.wang@rokid.com | support crown device, support rokid gesture recognition |



## New

v1.5.3
* support rokid RG-crown device
* support rokid gesture recognition(Four types of 2D gestures at present)
* Fixed #154: add sample usage of Yidao's TP 


## Bug fixes

v1.5.3
* Fixed #155: Voice recoginzation bug for the Sample "Open" instruction.

