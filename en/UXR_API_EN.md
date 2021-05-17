# Rokid UXR SDK for Unity
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
The VoiceRecognizer prefab manages rokid voice instruction function. You can add/remove voice instructions by it.  
At present, it supports Chinese, English language.  
Chinese instruct only available when system language is Chinese, and English instruct only available when system language is English.

* class:

    VoiceRecognizer

* API:

  * public  void unityremoveInstructZH(string name)  
 remove a Chinese instruct  
 eg, unityremoveInstructZH("下一个")

  * public void unityclearUserInstruct()  
 clear all the instructs set by user

  * public void unityaddInstrucEntityZH(string name, string pinyin, string gameobj,string unitycallbackfunc,string tmp)  
 add a Chinese instruct，use default config  
 eg, unityaddInstrucEntityZH("下一个", pinyin, "VoiceRecognizer","unitydoNext","xyg")


  * public void unityaddInstrucEntityZH(string name, string pinyin, bool showTips, bool ignoreHelp,bool ignoreToast, string gameobj,string unitycallbackfunc,string tmp)  
 add a Chinese instruct, with specfic confic  
 eg, unityaddInstrucEntityZH("下一个", pinyin, true,true,true, "VoiceRecognizer","unitydoNext","xyg")


  * public void unityaddInstrucListZH(string prefix, string subfix, string helpContent, int startNo, int endNo, string gameobj, string unitycallbackfunc)  
 add a Chinese instructList  
 eg, unityaddInstrucListZH("打开第", "个", “打开第x个”,1,5, "VoiceRecognizer","unityInstructListFun")


  * public void unityaddInstrucEntity(int languageEnum, string name, string pinyin, string gameobj,string unitycallbackfunc,string tmp)  
 add an instruct，use default config
 para: 
  languageEnum: 0 - zh, 1 - en  
 eg, unityaddInstrucEntity(0, "下一个", pinyin, "VoiceRecognizer","unitydoNext","xyg")

  * public void unityaddInstrucEntity(int languageEnum, string name, string pinyin, bool showTips, bool ignoreHelp,bool ignoreToast, string gameobj,string unitycallbackfunc,string tmp)  
 add an instruct，use defspecficault config  
 para:   
  languageEnum: 0 - zh, 1 - en  
 eg, unityaddInstrucEntity(0, "下一个", pinyin, true,true,true, "VoiceRecognizer","unitydoNext","xyg")

  * public void unityaddInstrucList(int languageEnum,string prefix, string subfix, string helpContent, int startNo, int endNo, string gameobj, string unitycallbackfunc)  
 add an instructList  
 eg, unityaddInstrucList(0,"打开第", "个", “打开第x个”,1,5, "VoiceRecognizer","unityInstructListFun")



