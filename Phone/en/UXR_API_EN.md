# Rokid UXR Phone SDK for Unity
====================================
Copyright 2021 Rokid


## API reference

### Motion tracking & Stereoscopic rendering API
[Google Cardboard XR Plugin for Unity API Reference](https://developers.google.com/cardboard/reference/unity) 

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



