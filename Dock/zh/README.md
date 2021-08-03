
# UXR Dock SDK

## 一、简介
1、UXR Dock SDK是一套适用于 Rokid AR 设备的 Unity SDK，可以帮助开发者创作眼镜上的 XR 应用。

2、UXR 基于 Google Cardboard，包含如下特性：
   * 头部追踪
   * 双目立体渲染
   * 语音识别
   * 手势识别

3、基于这些特性，可以开发全新的 XR 应用，也可以为已有应用添加 XR 效果。

4、UXR Dock SDK 通过如下 Unity Sample 场景展示了以上特性的使用
   * 头部追踪场景  `展示 3DoF 头部追踪和 Glass 双目立体渲染的功能` 
   * 语音识别场景  `展示语音识别功能（中英文离线语音指令）`
   * 手势识别场景  `展示手势识别功能（当前支持识别四种 2D 手势）`

## 二、环境准备

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
		<td>请搭配 Unity3D 兼容的 JDK, Android SDK, NDK 进行开发</td>
	</tr>
	<tr>
		<td rowspan='2'>硬件要求</td>
		<td>Rokid Yidao Dock + Air</td>
		<td>Dock 系统版本：2.3.1-20210629-100002+</td>
	</tr>
	<tr>
		<td>Rokid X-Craft</td>
		<td>RG-crown 系统版本：2.0.0-20210702-502107 +</td>
	</tr>
</table>

## 三、快速上手
如何使用 UXR Dock SDK:

* 请阅读并按照以下链接所述步骤搭建UXR Unity开发环境  
 [快速构建](./Quickstart_UXR_Unity_Dock.md) 

* UXR API 参考文档  
 [UXR API ](./UXR_Dock_API.md) 

## 四、最佳实践
UXR Dock SDK 及 Sample 工程(v1.5.5)：  
[下载地址](https://ota-g.rokidcdn.com/toB/Rokid_Glass/SDK/UXR_SDK/Unity/forDock/RokidUXR_Unity_ForDock_1.5.5.zip)

## 五、UXR版本说明

* UXR SDK 版本说明文档  
 [UXR 版本说明](./ReleaseNotes.md) 
