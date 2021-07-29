# 开发手册
## 一、UXR 动态权限申请
### 1、声明所需权限

`AndroidManifest.xml` 下声明所需权限
```xml
    <uses-permission android:name="android.permission.CAMERA" />
    <uses-permission android:name="android.permission.RECORD_AUDIO"/>
```

### 2、权限申请

 * 创建对应权限数组
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

## 四、UXR 手势服务

### 1、初始化

初始化 USB Camera：
```CS
UsbDeviceHelper.initUSBCamera();
```
初始化手势服务，设置手势结果返回的回调，参数为接收消息的游戏物体和方法
```CS
RKGestureHelper.init("RKGesure", "gestureCallback");
```


### 2、处理 Camera 数据

在 Unity 的 Update 中，处理 Camera 数据：
```CS
    void Update()
    {
        ...
        RKGestureHelper.handleFrame();
    }
```

### 3、获取手势数据

在对象 `RKGesure` 的 `gestureCallback` 方法下接收手势数据：
```CS
    public void gestureCallback(string strGestureJson)
    {
        GestureBean bean = JsonUtility.FromJson<GestureBean>(strGestureJson);
        Debug.Log("RKGesture::gesture x1 = " + bean.x1 + "bean gesture type = " + bean.gesture_type);
    }
```

### 4、释放
结束时释放手势服务，释放 USB 设备
```CS
    private void OnDestroy()
    {
        ...
        RKGestureHelper.release();
        UsbDeviceHelper.release();
    }
```