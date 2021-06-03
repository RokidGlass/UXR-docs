# Rokid UXR Phone SDK for Unity
====================================
Copyright 2021 Rokid


## API 参考

### 头动跟踪与双目渲染API
 [Google Cardboard XR Unity API 参考](https://developers.google.com/cardboard/reference/unity) 

### TouchPointer
 TouchPointer 控制射线整体（显示隐藏，渲染队列，锚中状态锚点贴图改变）
 * 类:

    TouchPointer

* API:

  * public void SetLaserBeamActive(bool active)
	设置整体显示

  * public void SetDotActive(bool active)
	设置射线锚点部分显示
	
  * public void SetRayActive(bool active)
	设置光束部分显示
  
  * public void SetFocus(bool focus)
	设置锚点贴图
	
### TouchRay
 TouchRay 手势 控制射线锚点移动 + 手势检测
 * 类:

    TouchRay

* API:

  * public void TouchMove()
	Touch事件检测，移动锚点

  * public void Raycast()
	发射射线，射线检测
	
  * public void FingerCheck()
	手势检测
  
  * public void DrawRay()
	绘制射线，改变射线起始位置
 