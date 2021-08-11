# 快速构建 - Phone

本文展示如何利用 【UXR Unity SDK】 快速建立 XR 应用工程。  
通过以下操作可快速实现，进行**双目 3D 场景渲染**、**3DoF 头动跟踪**。



## 1. 建立开发环境
类别    |项目                           |备注
-------|------------------------------|---------------------
硬件要求|Rokid Air + 适配的 Android 手机 |适配的 Android 手机：黑鲨手机3S SHARK KLE-A0、黑鲨手机4 SHARK PRS-A0
软件要求|Unity3D开发工具                |支持Unity 2019.3.15f1 ~ 2020.1版本，请搭配兼容的 JDK, Android SDK, NDK 进行开发
软件要求|Rokid Air App                 |先下载Air App并安装到手机上


## 2. 创建 Unity 新工程、导入 SDK

* 2.1 打开 **Unity**,建立一个新的 3D 工程.
* 2.2 **Unity** 中打开 **Window > Package Manager**.
* 2.3 点击 **+**， 选择 **Add package from disk**.
* 2.4 下载并解压 **UXR SDK**, 选择其中的 **package.json** 文件，然后 **SDK** 将被导入.
* 2.5 进入到 **Google Cardboard XR Plugin for Unity package**， 在 **Samples** 部分, 选择 **Import into Project**.  
   **Unity sample assets** 将被导入到 **Assets/Samples/Google Cardboard/`<version>`/Hello Cardboard/Assets**.
* 2.6 进入到 **Assets/Samples/Google Cardboard/`<version>`/Hello Cardboard/Assets/Scenes**, 选择 **Add Open Scenes**, 选择并打开 **HelloCardboard sample scene**.

**Tips: `<version>` 是 X.Y.Z 版本号 (例如, 1.1.0)**

## 3. 配置 Android 工程

* 3.1 **打开 File > Build Settings**

  选择 Android 然后选择 Switch Platform.  
  选择 Add Open Scenes 然后选择 HelloCardboard.

* 3.2 **Player Settings**  
Resolution and Presentation  
打开 Project Settings > Player > Resolution and Presentation.  
设置 Default Orientation 为 Landscape Left.  
禁用 Optimized Frame Pacing.

* 3.3 **Other Settings**  
打开 Project Settings > Player > Other Settings.  

Graphics APIs 选择 OpenGLES2, 或 OpenGLES3, 或两者都选.  
Scripting Backend 选择 IL2CPP.  
Target Architectures 选择 ARMv7和/或 ARM64.  
Internet Access 选择 Require.  
设置 Package Name.  


* 3.4 **Publishing Settings**  
打开 Project Settings > Player > Publishing Settings.

Build 部分选择 Custom Base Gradle Template.  
在 Assets/Plugins/Android/baseProjectTemplate.gradle的repositories 部分增加如下内容(文件中有两处需要添加，添加到已有的jcenter()下面):
```CS
  maven { url 'https://maven.rokid.com/repository/maven-public/' }
```

Build 部分选择 Custom Main Gradle Template.  
在 Assets/Plugins/Android/mainTemplate.gradle的dependencies 部分增加如下内容:
```CS
  implementation 'com.android.support:appcompat-v7:28.0.0'  
  implementation 'com.android.support:support-v4:28.0.0'  
  implementation 'com.google.android.gms:play-services-vision:15.0.2'  
  implementation 'com.google.protobuf:protobuf-javalite:3.8.0'  
  implementation 'com.rokid.alliance.usbcamera2:usbcamera:2.0.0'
  implementation 'com.rokid.ai.glass:instructsdk:1.6.1'
```


Build部分选择 'Custom Main Manifest'.  
在Assets/Plugins/Android/AndroidManifest.xml的 activity 标签行，修改android:name为com.rokid.uxrmobile.UXRMobileUPActivity，如下:  
```CS
    <activity android:name="com.rokid.uxrmobile.UXRMobileUPActivity"
              android:theme="@style/UnityThemeSelector">
```

然后在AndroidManifest.xml中声明App所需权限，例如
```CS
    <uses-feature android:name="android.hardware.sensor.accelerometer" android:required="true"/>
    <uses-feature android:name="android.hardware.sensor.gyroscope" android:required="true"/>
    <uses-feature android:name="android.hardware.usb.host"/>
    
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.CAMERA" />
    <uses-permission android:name="android.permission.RECORD_AUDIO"/>
```

**如果Target API Level 设为 API Level 29 或 Automatic (highest installed)**，还需如下设置：  
 AndroidManifest.xml的 application 标签下增加如下内容:

  `<application android:requestLegacyExternalStorage="true" ... >`  
    ...  
  `</application>`

* 3.5 **XR Plug-in Management** 设置  
打开 Project Settings > XR Plug-in Management.

  Plug-in 项目下选择 Cardboard XR Plugin.

* 3.6 **编译应用**  
打开 File > Build Settings.

  选择 Build, 生成app后安装到手机, 再通过Rokid Air App打开它.

