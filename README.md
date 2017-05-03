# UMISuper
Fix issues on my UMI Super

## Broken Screen 
Solution: Resize the physical screen

Steps:
-Install Android Tools https://developer.android.com/studio/index.html#command-tools
-cd Downloads\platform-tools\bin
-Download SDK - sdkmanager.bat --list
-sdkmanager.bat "platforms;android-25"
-sdkmanager.bat "platform-tools"
-cd C\Downloads\sdk-tools-windows-3859397\platform-tools
-Display Current size : adb shell wm size
Physical size: 1080x1920

-Set Size: adb shell wm size 900x1920 -> Didn't work as the launcher fails

-Get all info: adb shell dumpsys display
 mBaseDisplayInfo=DisplayInfo{"Built-in Screen", uniqueId "local:0", app 1080 x 1920, real 1080 x 1920, largest app 1080 x 1920, smallest app 1080 x 1920, mode 1, defaultMode 1, modes [{id=1, width=1080, height=1920, fps=54.040005}], colorTransformId 1, defaultColorTransformId 1, supportedColorTransforms [{id=1, colorTransform=0}], hdrCapabilities android.view.Display$HdrCapabilities@9787559, rotation 0, density 480 (480.0 x 480.0) dpi, layerStack 0, appVsyncOff 8300000, presDeadline 11204810, type BUILT_IN, state OFF, FLAG_SECURE, FLAG_SUPPORTS_PROTECTED_BUFFERS}
    mOverrideDisplayInfo=DisplayInfo{"Built-in Screen", uniqueId "local:0", app 1080 x 1824, real 1080 x 1920, largest app 1776 x 1752, smallest app 1080 x 1008, mode 1, defaultMode 1, modes [{id=1, width=1080, height=1920, fps=54.040005}], colorTransformId 1, defaultColorTransformId 1, supportedColorTransforms [{id=1, colorTransform=0}], hdrCapabilities android.view.Display$HdrCapabilities@9787559, rotation 0, density 480 (480.0 x 480.0) dpi, layerStack 0, appVsyncOff 8300000, presDeadline 11204810, type BUILT_IN, state ON, FLAG_SECURE, FLAG_SUPPORTS_PROTECTED_BUFFERS}
    
    -Set Overscan: adb shell wm overscan 0,0,0,100


:)
