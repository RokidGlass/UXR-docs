
# UXR Phone SDK

## 一、简介
*  1、UXR Phone SDK 是一套适用于 Rokid Glass + 兼容手机的 Unity SDK，可以帮助开发者创作眼镜上的 XR 应用。  

*  2、UXR 基于 Google Cardboard，包含如下特性：  
   * 头部追踪
   * 双目立体渲染
   * 语音识别
   * 手机触屏交互

* 3、借助这些功能，可以开发全新的XR应用，也可以为已有应用添加XR效果。  

* 4、UXR Phone SDK通过如下 Unity Sample 场景展示了以上功能的使用:  
    * 头部追踪场景  `展示 3DoF 头部追踪和 Glass 双目立体渲染的功能` 
    * 语音识别场景  `展示语音识别功能（中英文离线语音指令，使用前需确保Rokid Air app已打开并且存活）` 



## 二、环境准备

类别    |项目                           |备注
-------|------------------------------|---------------------
硬件要求|Rokid Air + 适配的 Android 手机 |适配的 Android 手机：黑鲨手机3S SHARK KLE-A0、黑鲨手机4 SHARK PRS-A0
软件要求|Unity3D开发工具                |支持Unity 2019.3.15f1 ~ 2020.1版本，请搭配兼容的 JDK, Android SDK, NDK 进行开发
软件要求|Rokid Air App v1.0.7          |先下载Air App并安装到手机上，然后通过Air app打开UXR应用
 
## 三、快速上手
如何开始使用 UXR Phone SDK:

* 请阅读并按照以下链接所述步骤设置UXR Unity开发环境  
 [快速构建](./Quickstart_UXR_Unity_Phone.md) 

* UXR SDK API参考文档  
 [UXR API](./UXR_Phone_API.md) 

* UXR SDK 开发指南  
 [开发指南](./UXR_Developer_Manual.md) 

## 四、最佳实践

UXR Phone SDK 及 Sample 工程(v1.6.3)：  
[下载地址](https://ota-g.rokidcdn.com/toB/Rokid_Glass/SDK/UXR_SDK/Unity/forPhone/RokidUXR_Unity_ForPhone_1.6.3.zip)

## 五、版本说明

### v1.6.3
#### 新特性
* 新增Unity Camera 视角reset功能示例
* 支持离线语音识别 v1.6.1
* 升级兼容GlassSDK v2.0.6 
* 合入Cardboard v1.5.0 补丁
#### 已知问题
* Sample中频繁进入、退出头控场景，可能导致内存及稳定性问题
* 通过Air App v1.0.7第一次打开UXR 应用时，可能异常开启到手机屏幕。可结束该应用并重新通过Air App打开。


| 版本记录                       | 修订日期     | 撰稿人/修订人          | 变更记录及说明   |
| --------                      | ---------- | -------------------- | ---------------|
| UXR Phone SDK Unity v1.6.3    | 2021.07.29 | wenbo.wang@rokid.com | 新增支持语音识别  |
| UXR Phone SDK Unity v1.6.0    | 2021.05.31 | wenbo.wang@rokid.com | 首次创建文档     |



