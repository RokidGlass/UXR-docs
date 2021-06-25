# Rokid UXR Dock SDK for Unity
====================================  
Copyright 2020 Rokid


## API 参考

### 头动跟踪与双目渲染API
 [Google Cardboard XR Unity API 参考](https://developers.google.com/cardboard/reference/unity) 

### UXRManager
UXRManager prefab 管理眼镜事件及状态的通知，也可以通过其执行一些控制命令.
  
* 类:
    UXRController

* API:

  * public void MessageUSBDeviceATTACHED(string glassName)  
 当USB Glass插入Dock后，UXR接收到系统发出的ACTION_USB_DEVICE_ATTACHED广播, 该函数会被执行

  * public  void MessageUSBDeviceDETACHED(string glassName)  
 当USB Glass从Dock拔出后, UXR接收到系统发出的ACTION_USB_DEVICE_DETACHED 广播, 该函数会被执行

  * public static int getUSBEventStatus()  
 获取当前USB Glass的插拔广播状态  
 返回值: -1: 未知; 1: ATTACHED; 0: DETACHED

### Voice Recognition
管理 rokid 离线语音指令，可通过其添加、删除特定的语音指令.  
目前支持中文、英文语音指令.  
中文指令在系统语言为中文时有效；  
英文指令在系统语言为英文时有效；

* 类:
   VoiceCommandLogic

* API:

删除指令

  * public  void RemoveInstructZH(string name)  
  删除一条中文语音指令  
  eg, RemoveInstructZH("下一个")
 
   * public  void RemoveInstruct(int languageEnum,string name)  
  删除一条语音指令  
  参数: 
  languageEnum: 0 - 中文, 1 - 英文  
  eg, RemoveInstruct(1,"next")

  * public void ClearUserInstruct()  
  删除app内设置的所有指令


单条指令

  * public void AddInstrucEntityZH(string name, string pinyin, string gameobj,string unitycallbackfunc,string tmp)  
  增加一条中文语音指令  
  eg, AddInstrucEntityZH("下一个", pinyin, "VoiceRecognizer","unitydoNext","xyg")
 
  * public void AddInstrucEntityZH(string name, string pinyin, bool showTips, bool ignoreHelp, bool ignoreToast, string gameobj, string unitycallbackfunc, string tmp)  
  增加一条中文语音指令  
  eg, AddInstrucEntityZH("下一个", pinyin,ture,true,true,"VoiceRecognizer","unitydoNext","xyg")


  * public void AddInstrucEntity(int languageEnum,string name, string gameobj,string unitycallbackfunc,string tmp)  
  增加一条语音指令  
  参数: 
  languageEnum: 0 - 中文, 1 - 英文  
  eg, AddInstrucEntity(1,"next", "VoiceRecognizer","unitydoNext","xyg")

  * public void AddInstrucEntity(int languageEnum, string name, bool showTips, bool ignoreHelp, bool ignoreToast, string gameobj, string unitycallbackfunc, string tmp)  
  增加一条语音指令 
  参数: 
  languageEnum: 0 - 中文, 1 - 英文   
  eg, AddInstrucEntity(1,"next",true,true,true, "VoiceRecognizer","unitydoNext","xyg")


一组指令

  * public void AddInstrucListZH(string prefix, string subfix, string helpContent, int startNo, int endNo, string gameobj, string InstructListCallback)  
  增加一组中文语音指令  
  eg, AddInstrucListZH("打开第", "个", “打开第x个”,1,5, "VoiceRecognizer","InstructListCallback")

  * public void AddInstrucList(int languageEnum, string prefix, string subfix, string helpContent, int startNo, int endNo, string gameobj, string InstructListCallback)  
  增加一组语音指令
  参数:  
  languageEnum: 0 - 中文, 1 - 英文  
  eg, AddInstrucList(1,"打开第", "个", “打开第x个”,1,5, "VoiceRecognizer","InstructListCallback")

  * public void InstructListCallback(string ekey)  
  多条指令注册的回调  
  eg, public void InstructListCallback(string ekey)  
      {
		string[] keyArray = ekey.Split('-');  
        int index = int.Parse(keyArray[1]);  
        Debug.Log("-UXR- unityInstructListFun: " + keyArray[0] + ", index:" + index);  
      }


### Gesture Recognition
UXRGes prefab 管理识别手势状态的通知，显示识别到手的位置以及识别到的手势类型  
[手势类型示意图](https://github.com/RokidGlass/UXR-docs/tree/dev_dock_153/Dock/mm) 

* 类:
    UXRGesController
    
* API:
 * private void GesInit()  
 初始化手势服务，com.rokid.uxrplugin.activity.UXRUnityActivity已处理，Unity不用调
 
  * private void GesConnect()  
 连接手势服务，com.rokid.uxrplugin.activity.UXRUnityActivity已处理，Unity不用调
 
  * private void GesDisconnect()  
 断开手势服务，com.rokid.uxrplugin.activity.UXRUnityActivity已处理，Unity不用调
 
  * private void GesStart()  
 开启手势服务
 
  * private void GesStop()  
 关闭手势服务
 
 
 * 类:
     RKGestureEvent
     
* API:  
	int GesType//手势类型  
	float normPosX//屏幕归一化坐标X轴  
	float normPosY//屏幕归一化坐标Y轴  
	int screenPosX//预留屏幕像素坐标X轴  
	int screenPosY//预留屏幕像素坐标Y轴
