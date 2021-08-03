# 快速构建 - Dock

本文展示如何利用 【UXR Dock SDK】 快速建立 XR 应用工程。  
通过以下操作可快速实现**双目 3D 场景渲染**、**3DoF 头动跟踪**。



## 1、建立开发环境
<table>
	<tr>
		<td>类别</td>
		<td>具体要求</td>
		<td>备注</td>
	</tr>
	<tr>
		<td rowspan='2'>软件要求</td>
		<td rowspan='2' >Unity3D</td>
		<td>支持2019.3.15f1 ~ 2020.1版本</td>
	</tr>
	<tr>
		<td>请使用 Unity3D 对应兼容的 JDK, Android SDK, NDK 进行开发</td>
	</tr>
	<tr>
		<td rowspan='2'>硬件要求</td>
		<td>Rokid Yidao Dock + Air</td>
		<td>Dock 系统版本2.3.1-20210623-100003+</td>
	</tr>
	<tr>
		<td>Rokid X-Craft</td>
		<td>RG-crown,系统版本1.3.5-20210618-502103+</td>
	</tr>
</table>

## 2、创建Unity新工程、导入SDK

2.1、打开 **Unity** ,建立一个新的3D工程.

2.2、**Unity**中打开**Window > Package Manager**.

2.3、点击 **+**， 选择 **Add package from disk**.

2.4、下载并解压 **UXR SDK**, 选择其中的 **package.json** 文件，然后**SDK**将被导入.

2.5、进入到 **Google Cardboard XR Plugin for Unity package**,在 **Samples** 部分, 选择 **Import into Project**.   

**Unity sample assets** 将被导入到 **Assets/Samples/Google Cardboard/`<version>`/Hello Cardboard/Assets**.  

2.6、进入到 **Assets/Samples/Google Cardboard/`<version>`/Hello Cardboard/Assets/Scenes**, 选择 **Add Open Scenes**, 选择并打开 **HelloCardboard sample scene**

**Tips: `<version>` 是 X.Y.Z 版本号 (例如, 1.1.0)**

## 3、配置Android工程

3.1、**打开 File > Build Settings**.

  选择 Android 然后选择 Switch Platform.  
  选择 Add Open Scenes 然后选择 HelloCardboard.  

3.2、**Player Settings**  
  Resolution and Presentation.  
  
  打开 Project Settings > Player > Resolution and Presentation.  
  设置 Default Orientation 为 Landscape Left.  
  禁用 Optimized Frame Pacing.  

3.3、**Other Settings**  
  打开 Project Settings > Player > Other Settings.  

  Graphics APIs 选择 OpenGLES2, 或 OpenGLES3, 或两者都选.  
  Scripting Backend 选择 IL2CPP.  
  Target Architectures 选择 ARMv7和/或 ARM64.  
  Internet Access选择 Require.  
  设置 Package Name.  


3.4、**Publishing Settings**  
  打开 Project Settings > Player > Publishing Settings.

  Build部分选择 Custom Main Gradle Template.  
  在 Assets/Plugins/Android/mainTemplate.gradle的dependencies 部分增加如下内容:

  implementation 'com.android.support:appcompat-v7:28.0.0'  
  implementation 'com.android.support:support-v4:28.0.0'  
  implementation 'com.google.android.gms:play-services-vision:15.0.2'  
  implementation 'com.google.protobuf:protobuf-lite:3.0.0'  


如果Target API Level 设为 API Level 29 或 Automatic (highest installed)，还需如下设置：

 Build部分选择 'Custom Main Manifest'.  
 Assets/Plugins/Android/AndroidManifest.xml的application 标签下增加如下内容:

  `<application android:requestLegacyExternalStorage="true" ... >`  
    ...  
  `</application>`

3.5、**XR Plug-in Management 设置**  
  打开 Project Settings > XR Plug-in Management.

  Plug-in 项目下选择 Cardboard XR Plugin.

3.6、**编译应用**  
  打开 File > Build Settings.

  选择 Build, 或 指定设备并选择 Build and Run.

