# Quickstart for Rokid UXR SDK for Unity

This guide shows you how to use the UXR Unity SDK to create your own XR experiences.


You can use the SDK on Rokid AR Glass platform. The glass can display 3D scenes with stereoscopic rendering,
 track and react to head movements.




## 1. Set up your development environment
 Software requirements:  

  * Unity3D (2019.3.15f1 ~ 2020.1)  
Make sure to include Android  Build Support during installation.


## 2. Import the SDK and create a new project
Follow these steps to import the Unity SDK and create a new project.

* 2.1 Open Unity and create a new 3D project.
* 2.2 In Unity, go to Window > Package Manager.
* 2.3 Click + and select Add package from disk.
* 2.4 Download the UXR SDK plugin and decompress it, then select the package.json file under SDK dir.  
The package should be added to the installed packages.
* 2.5 Navigate to the Google Cardboard XR Plugin for Unity package. In the Samples section, choose Import into Project.  
The sample assets should be loaded into Assets/Samples/Google Cardboard/<version>/Hello Cardboard/Assets.
* 2.6 Navigate to Assets/Samples/Google Cardboard/<version>/Hello Cardboard/Assets/Scenes, select Add Open Scenes, and choose HelloCardboard to open the sample scene.

Note: <version> is the X.Y.Z semantic version number of the released package (for example, 1.1.0).

## 3. Configuring Android project settings

* 3.1 Navigate to File > Build Settings.

  Select Android and choose Switch Platform.  
  Select Add Open Scenes and choose HelloCardboard.

* 3.2 Player Settings  
Resolution and Presentation  
Navigate to Project Settings > Player > Resolution and Presentation.  
Set the Default Orientation to Landscape Left.  
Disable Optimized Frame Pacing.

* 3.3 Other Settings  
Navigate to Project Settings > Player > Other Settings.  

Select OpenGLES2, or OpenGLES3, or both in Graphics APIs.  
Select IL2CPP in Scripting Backend.  
Select desired architectures by choosing ARMv7, ARM64, or both in Target Architectures.  
Select Require in Internet Access.  
Specify your company domain under Package Name.  


* 3.4 Publishing Settings  
Navigate to Project Settings > Player > Publishing Settings.

Select Custom Main Gradle Template in the Build section.  
Add the following lines to the dependencies section of Assets/Plugins/Android/mainTemplate.gradle:

  implementation 'com.android.support:appcompat-v7:28.0.0'  
  implementation 'com.android.support:support-v4:28.0.0'  
  implementation 'com.google.android.gms:play-services-vision:15.0.2'  
  implementation 'com.google.protobuf:protobuf-lite:3.0.0'  

If Target API Level is set to API Level 29 or Automatic (highest installed) (resulting in API Level 29), the following steps are also required:

Select 'Custom Main Manifest' in the Build section.  
Add the following attribute to the application tag of Assets/Plugins/Android/AndroidManifest.xml:

  `<application android:requestLegacyExternalStorage="true" ... >`  
    ...  
  `</application>`

* 3.5 XR Plug-in Management Settings  
Navigate to Project Settings > XR Plug-in Management.

  Select Cardboard XR Plugin under Plug-in Providers.

* 3.6 Build your project  
Navigate to File > Build Settings.

  Select Build, or choose a device and select Build and Run.

