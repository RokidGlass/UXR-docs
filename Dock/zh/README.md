
# UXR Dock SDK

# 简介
* UXR Dock SDK是一套适用于Rokid Yidao 主机的SDK，可帮助开发者创作眼镜上的XR应用。UXR基于Google Cardboard，包含如下特性
    * 头部追踪
    * 双目立体渲染
    * 语音识别
    * 手势识别

* 借助这些功能，可以开发全新的XR应用，也可以为已有应用添加XR效果。

* UXR Unity SDK通过如下Unity Sample 场景展示了以上功能的使用:
    * 头部追踪场景  `展示3 dof头部追踪和glass双目立体渲染的功能` 
    * 语音识别场景  `展示语音识别功能（中英文离线语音指令）`
	* 手势识别场景  `展示手势识别功能（当前支持识别四种2D手势）`

# 环境准备
  * 硬件环境
    *  Rokid dock(支持Rokid Yidao 主机,系统版本2.3.1-20210623-100003+) + Rokid glass(支持Rokid Air眼镜)
    *  Rokid X-Craft(RG-crown,系统版本1.3.5-20210618-502103+)
  * 软件环境
    *  Unity3D (支持2019.3.15f1 ~ 2020.1版本）
    *  Unity3D打包Android应用依赖的JDK, Android SDK, NDK

# 快速上手
如何开始使用UXR Unity SDK:

* 请阅读并按照以下链接所述步骤设置
 [Quickstart\_UXR\_Unity\_CN](./Quickstart_UXR_Unity_CN.md) 

# API 说明

详见 [UXR\_API\_CN](./UXR_API_CN.md) 


# 最佳实践
Unity SDK及Sample工程下载地址：  
``https://ota-g.rokidcdn.com/toB/Rokid_Glass/SDK/UXR_SDK/Unity/forDock/RokidUXR_Unity_ForDock_1.5.3.zip``


# ChangeLog

| 版本记录                      | 修订日期     | 撰稿人/修订人          | 变更记录及说明  |
| --------                     | ---------- | -------------------- | ------------- |
| UXR Dock SDK Unity v1.5.0    | 2021.04.16 | wenbo.wang@rokid.com | 首次创建文档    |
| UXR Dock SDK Unity v1.5.2    | 2021.05.31 | wenbo.wang@rokid.com | 新增支持Air眼镜 |
| UXR Dock SDK Unity v1.5.3    | 2021.06.25 | wenbo.wang@rokid.com | 新增支持X-Craft设备，支持手势识别 |


## 新特性

v1.5.3
* 新增支持X-Craft设备(RG-crown, 系统版本 1.3.5-20210618-502103+)
* 新增手势识别功能（当前支持识别四种2D手势）
* #154: 增加Yidao dock TP按键使用示例


## Bug 解决

v1.5.3
* #155: 解决Sample中“打开”语音指令作用域错误bug.

