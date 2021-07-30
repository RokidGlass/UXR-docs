# 开发手册
## 一、UXR 动态权限申请
### 1、声明所需权限

`AndroidManifest.xml` 中声明所需权限，例如
```xml
    <uses-permission android:name="android.permission.CAMERA" />
    <uses-permission android:name="android.permission.RECORD_AUDIO"/>
```

### 2、权限申请

 * 创建对应权限的数组，例如
```CS
    string[] permissions = new string[] {
        "android.permission.CAMERA",
        "android.permission.RECORD_AUDIO"};
```
 * 权限申请
```CS
DynamicPermissionHelper.requestPermission(permissions, "RKGesure", "permissionCallback");
```

### 3、获取申请结果

在对象 `RequestPermission的permissionCallback` 方法下接收权限申请结果，返回为 `string` 类型的 "true" 或 "false" :
```CS
    //result:{success: "true" fail: "false"}
    public void permissionCallback(string result)
    {
        Debug.Log("test::result = " + result);
    }

```

## 二、UXR USB 权限申请

针对用到 Camera 或 IMU 数据的场景，需要初始化 USB 设备以及申请 USB 权限

### 1、初始化

初始化 USB 设备：
```CS
UsbDeviceHelper.initUSBCamera();
```
调用上述方法后，应用会弹出 USB 权限和 Camera 权限申请弹窗，需要用户点击确认后才能继续后续流程。

### 2、释放

释放 USB 设备：
```CS
UsbDeviceHelper.release();
```

## 三、UXR 语音识别  
   目前支持中文、英文语音指令，使用语音指令前，需确保Rokid Air app已打开并且存活  
      中文指令在系统语言为中文时有效；  
      英文指令在系统语言为英文时有效；


