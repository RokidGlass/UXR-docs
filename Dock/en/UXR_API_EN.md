# Rokid UXR Dock SDK for Unity
====================================  
Copyright 2020 Rokid


## API reference

### Motion tracking & Stereoscopic rendering API
[Google Cardboard XR Plugin for Unity API Reference](https://developers.google.com/cardboard/reference/unity) 

### UXRManager
The UXRManager prefab manages some glass event and status notification, and you can also do some controls via it.

* Class:

    UXRController

* API:

  * public void MessageUSBDeviceATTACHED(string glassName)  
 when USB glass plugin, ACTION_USB_DEVICE_ATTACHED event broadcast received, this function will be called

  * public  void MessageUSBDeviceDETACHED(string glassName)  
 when USB glass plugout, ACTION_USB_DEVICE_DETACHED event broadcast received, this function will be called

  * public static int getUSBEventStatus()  
 get USB glass plugin/plugout event status
 return value: -1: unknown; 1: ATTACHED; 0: DETACHED

### Voice Recognition
Manage rokid voice instruction function. You can add/remove voice instructions by it.  
At present, it supports Chinese, English language.  
Chinese instruct only available when system language is Chinese, and English instruct only available when system language is English.

* class:

    VoiceCommandLogic

* API:

Delete instructions

  * public  void RemoveInstructZH(string name)  
  Delete a Chinese voice command  
  eg, RemoveInstructZH("下一个")
 
   * public  void RemoveInstruct(int languageEnum,string name)  
  Delete a voice command  
  Parameters: 
  languageEnum: 0 - zh, 1 - en  
  eg, RemoveInstruct(1,"next")

  * public void ClearUserInstruct()  
  Delete all instructions set in the app


Add single instruction

  * public void AddInstrucEntityZH(string name, string pinyin, string gameobj,string unitycallbackfunc,string tmp)  
  Add a Chinese voice command   
  eg, AddInstrucEntityZH("下一个", pinyin, "VoiceRecognizer","unitydoNext","xyg")
 
  * public void AddInstrucEntityZH(string name, string pinyin, bool showTips, bool ignoreHelp, bool ignoreToast, string gameobj, string unitycallbackfunc, string tmp)  
  Add a Chinese voice command    
  eg, AddInstrucEntityZH("下一个", pinyin,ture,true,true,"VoiceRecognizer","unitydoNext","xyg")


  * public void AddInstrucEntity(int languageEnum,string name, string gameobj,string unitycallbackfunc,string tmp)  
  Add a voice command    
  Parameters: 
  languageEnum: 0 - zh, 1 - en  
  eg, AddInstrucEntity(1,"next", "VoiceRecognizer","unitydoNext","xyg")

  * public void AddInstrucEntity(int languageEnum, string name, bool showTips, bool ignoreHelp, bool ignoreToast, string gameobj, string unitycallbackfunc, string tmp)  
  Add a voice command  
  Parameters: 
  languageEnum: 0 - zh, 1 - en    
  eg, AddInstrucEntity(1,"next",true,true,true, "VoiceRecognizer","unitydoNext","xyg")


Add a set of instructions

  * public void AddInstrucListZH(string prefix, string subfix, string helpContent, int startNo, int endNo, string gameobj, string InstructListCallback)  
  Add a set of Chinese voice commands  
  eg, AddInstrucListZH("打开第", "个", “打开第x个”,1,5, "VoiceRecognizer","InstructListCallback")

  * public void AddInstrucList(int languageEnum, string prefix, string subfix, string helpContent, int startNo, int endNo, string gameobj, string InstructListCallback)  
  Add a set of voice commands
  Parameters:  
  languageEnum: 0 - zh, 1 - en   
  eg, AddInstrucList(1,"打开第", "个", “打开第x个”,1,5, "VoiceRecognizer","InstructListCallback")

  * public void InstructListCallback(string ekey)  
  Callback registered by multiple instructions  
  eg, public void InstructListCallback(string ekey)  
      {  
		string[] keyArray = ekey.Split('-');  
        int index = int.Parse(keyArray[1]);  
        Debug.Log("-UXR- unityInstructListFun: " + keyArray[0] + ", index:" + index);  
      }  

### Gesture Recognition
UXRGes prefab manages notifications of recognized gesture status, display the position of the recognized hand and the type of recognized gesture  
[supported gesture](https://github.com/RokidGlass/UXR-docs/tree/dev_dock_153/Dock/mm) 

* class:
    UXRGesController
    
* API:
 * private void GesInit()  
 Initialize gesture service，com.rokid.uxrplugin.activity.UXRUnityActivity has been processed, Unity does not need to call 
 
  * private void GesConnect()  
 Connect gesture service，com.rokid.uxrplugin.activity.UXRUnityActivity has been processed, Unity does not need to call
 
  * private void GesDisconnect()  
 Disconnect gesture service，com.rokid.uxrplugin.activity.UXRUnityActivity has been processed, Unity does not need to call
 
  * private void GesStart()
 Start gesture service
 
  * private void GesStop()
 Stop gesture service
 
 
 * class:
     RKGestureEvent
     
* API:  
	int GesType//Gesture type  
	float normPosX//Screen normalized coordinate X axis  
	float normPosY//Screen normalized coordinate Y axis  
	int screenPosX//Reserved parameter, screen pixel coordinate X axis  
	int screenPosY//Reserved parameter, screen pixel coordinate Y axis


