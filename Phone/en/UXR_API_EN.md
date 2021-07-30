# UXR Phone API

## 1. Motion tracking & Stereoscopic rendering API
[Google Cardboard XR Plugin for Unity API Reference](https://developers.google.com/cardboard/reference/unity) 

## 2 Touch Screen
### TouchPointer
 TouchPointer Control the ray（show and hide，SortingOrder，anchor point map）
 * Class:

    TouchPointer

* API:

  * public void SetLaserBeamActive(bool active)
	//Set the overall display

  * public void SetDotActive(bool active)
	//Set the display of the anchor part
	
  * public void SetRayActive(bool active)
	//Set the display of the ray part
  
  * public void SetFocus(bool focus)
	//Set anchor point map
	
### TouchRay
 TouchRay Gesture control ray anchor point movement and gesture detection
 * Class:

    TouchRay

* API:

  * public void TouchMove()
	//Touch event detection, move anchor

  * public void Raycast()
	//Raycast
	
  * public void FingerCheck()
	//Gesture detection
  
  * public void DrawRay()
	//Draw ray, change the start and end position of the ray

## 3 Voice Recognition
Manage rokid voice instruction function. You can add/remove voice instructions by it.  
At present, it supports Chinese, English language.  
Chinese instruct is available when system language is Chinese, and English instruct only available when system language is English.

* class:

    VoiceCommandLogic

* API:

Delete voice instructions

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




