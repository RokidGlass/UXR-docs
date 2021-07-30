# UXR Phone API

## 一、头动跟踪与双目渲染API
 此处可参考 [**Google Cardboard XR Unity API 参考**](https://developers.google.com/cardboard/reference/unity) 

## 二、TouchPointer 控制射线整体（显示隐藏，渲染队列，锚中状态锚点贴图改变）
 * 类:

    TouchPointer

* API:

    | 变量                                       |定义|
    --------------------------------------------|-----------------|
    |public void SetLaserBeamActive(bool active)|设置整体显示       |
    |public void SetDotActive(bool active)      |设置射线锚点部分显示 |
    |public void SetRayActive(bool active)      |设置光束部分显示    |
    |public void SetFocus(bool focus)           |设置锚点贴图       |
	
	
## 三、TouchRay 手势 控制射线锚点移动 + 手势检测
* 类:

    TouchRay

* API:

    | 变量                      |定义                   |
    ---------------------------|-----------------------|
    |public void TouchMove()   |Touch事件检测，移动锚点   |
    |public void Raycast()     |发射射线，射线检测        |
    |public void FingerCheck() |手势检测                |
    |public void DrawRay()     |绘制射线，改变射线起始位置 |
	
 
## 四、动态权限申请

* 类

  DynamicPermissionHelper 动态权限申请辅助类 [动态权限获取](./UXR_Developer_Manual.md)

* API:

  * public static void requestPermission(string[] permissions, string callbackObj, string callbackMethod) 请求指定权限，通过指定的物体callbackObj和方法callbackMethod返回，callbackMethod接收string类型，成功返回"true"，失败返回"false".

## 五、USB设备管理

* 类

  UsbDeviceHelper USB设备辅助类

* API:

     | 变量                              |定义           |
     -----------------------------------|---------------|
     |public static void initUSBCamera()|初始化USB设备，若未授予USB权限，应用会弹出USB权限和Camera权限申请弹窗|
     |public static void release()      |释放USB设备|
   

## 六、语音识别
Rokid 离线语音指令，可通过其添加、删除特定的语音指令。  

   目前支持中文、英文语音指令；  
      中文指令在系统语言为中文时有效；  
      英文指令在系统语言为英文时有效；

* **类:VoiceCommandLogic**

* API:
        
**1、删除指令**

变量                                                       |定义                                              |示例
----------------------------------------------------------|--------------------------------------------------|---
 public void RemoveInstructZH(string name)                |删除一条中文语音指令                                 |RemoveInstructZH("下一个")
 public void RemoveInstruct(int languageEnum,string name) |删除一条语音指令  参数: languageEnum: 0 - 中文, 1 - 英文 | RemoveInstruct(1,"next")
 public void ClearUserInstruct()                          |删除app内设置的所有指令                               |
   
**2、单条指令**

变量                                                       |定义                                              |示例
----------------------------------------------------------|--------------------------------------------------|---
public void AddInstrucEntityZH(string name, string pinyin, string gameobj,string unitycallbackfunc,string tmp) |增加一条中文语音指令 |AddInstrucEntityZH("下一个", pinyin, "VoiceRecognizer","unitydoNext","xyg")
public void AddInstrucEntityZH(string name, string pinyin, bool showTips, bool ignoreHelp, bool ignoreToast, string gameobj, string unitycallbackfunc, string tmp) |增加一条中文语音指令 |AddInstrucEntityZH("下一个", pinyin,ture,true,true,"VoiceRecognizer","unitydoNext","xyg")
public void AddInstrucEntity(int languageEnum,string name, string gameobj,string unitycallbackfunc,string tmp) |增加一条语音指令 参数: languageEnum: 0 - 中文, 1 - 英文 |AddInstrucEntity(1,"next", "VoiceRecognizer","unitydoNext","xyg")
public void AddInstrucEntity(int languageEnum, string name, bool showTips, bool ignoreHelp, bool ignoreToast, string gameobj, string unitycallbackfunc, string tmp)|增加一条语音指令  参数:  languageEnum: 0 - 中文, 1 - 英文 |AddInstrucEntity(1,"next",true,true,true, "VoiceRecognizer","unitydoNext","xyg")

**3、一组指令**

变量                                                       |定义                                              |示例
----------------------------------------------------------|--------------------------------------------------|---
public void AddInstrucListZH(string prefix, string subfix, string helpContent, int startNo, int endNo, string gameobj, string InstructListCallback)|增加一组中文语音指令|AddInstrucListZH("打开第", "个", “打开第x个”,1,5, "VoiceRecognizer","InstructListCallback")
public void AddInstrucList(int languageEnum, string prefix, string subfix, string helpContent, int startNo, int endNo, string gameobj, string InstructListCallback) |增加一组语音指令  参数:languageEnum: 0 - 中文, 1 - 英文|AddInstrucList(1,"打开第", "个", “打开第x个”,1,5, "VoiceRecognizer","InstructListCallback") 
public void InstructListCallback(string ekey)|多条指令注册的回调|public void InstructListCallback(string ekey)   `{  string[] keyArray = ekey.Split('-');  int index = int.Parse(keyArray[1]);  Debug.Log("-UXR- unityInstructListFun: " + keyArray[0] + ", index:" + index);   }`



    
