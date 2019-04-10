# activity-stack-task
Understand Tasks and Back Stack

1、 https://developer.android.com/guide/components/activities/tasks-and-back-stack 是对Android activity task和stack的理解

2、深入理解activity的四种启动模式，standard、singleTop、singleTask、singleinstance

3、taskaffinity 栈亲和性的理解
任务栈标示，搭配singleTask或者Intent.FLAG_ACTIVITY_NEW_TASK 可以显示不同于启动activity的TaskRecord。

4、allowTaskReparent为true的理解。a 应用的A activity设置为该属性；当应用b启动 a应用A activity时，A activity跟b应用的启动activity属于同一个TaskRecord

5、adb shell dumpsys activity activities任务栈打印。

ACTIVITY MANAGER ACTIVITIES (dumpsys activity activities)
Display #0 (activities from top to bottom):
  Stack #1:
  mFullscreen=true
  isSleeping=false
  mBounds=null
    Task id #93
    mFullscreen=true
    mBounds=null
    mMinWidth=-1
    mMinHeight=-1
    mLastNonFullscreenBounds=null
    * TaskRecord{e5bdf0e #93 A=com.amazon.yao U=0 StackId=1 sz=1}
      userId=0 effectiveUid=u0a82 mCallingUid=u0a82 mUserSetupComplete=true mCallingPackage=com.yao.activity
      affinity=com.amazon.yao
      intent={flg=0x10000000 cmp=com.yao.activity/.ActivityE}
      realActivity=com.yao.activity/.ActivityE
      autoRemoveRecents=false isPersistable=true numFullscreen=1 taskType=0 mTaskToReturnTo=0
      rootWasReset=false mNeverRelinquishIdentity=true mReuseTask=false mLockTaskAuth=LOCK_TASK_AUTH_PINNABLE
      Activities=[ActivityRecord{6465198 u0 com.yao.activity/.ActivityE t93}]
      askedCompatMode=false inRecents=true isAvailable=true
      lastThumbnail=null lastThumbnailFile=/data/system_ce/0/recent_images/93_task_thumbnail.png
      stackId=1
      hasBeenVisible=true mResizeMode=RESIZE_MODE_RESIZEABLE_VIA_SDK_VERSION mSupportsPictureInPicture=false isResizeable=true firstActiveTime=1554878411089 lastActiveTime=1554878411119 (inactive for 20s)
      * Hist #0: ActivityRecord{6465198 u0 com.yao.activity/.ActivityE t93}
          packageName=com.yao.activity processName=com.yao.activity
          launchedFromUid=10082 launchedFromPackage=com.yao.activity userId=0
          app=ProcessRecord{6b8e832 5670:com.yao.activity/u0a82}
          Intent { flg=0x10000000 cmp=com.yao.activity/.ActivityE }
          frontOfTask=true task=TaskRecord{e5bdf0e #93 A=com.amazon.yao U=0 StackId=1 sz=1}
          taskAffinity=com.amazon.yao
          realActivity=com.yao.activity/.ActivityE
          baseDir=/data/app/com.yao.activity-tjVkMlwzbP4WBxrAkGHxPQ==/base.apk
          dataDir=/data/user/0/com.yao.activity
          stateNotNeeded=false componentSpecified=true mActivityType=0
          compat={560dpi} labelRes=0x7f0b0027 icon=0x7f0a0001 theme=0x7f0c0005
          mLastReportedConfigurations:
           mGlobalConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
           mOverrideConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          CurrentConfiguration={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          taskDescription: iconFilename=null label="null" primaryColor=ff008577
            backgroundColor=fffafafa
            statusBarColor=ff00574b
            navigationBarColor=ff000000
          launchFailed=false launchCount=1 lastLaunchTime=-20s110ms
          haveState=false icicle=null
          state=RESUMED stopped=false delayedResume=false finishing=false
          keysPaused=false inHistory=true visible=true sleeping=false idle=true mStartingWindowState=STARTING_WINDOW_SHOWN
          fullscreen=true noDisplay=false immersive=false launchMode=2
          frozenBeforeDestroy=false forceNewConfig=false
          mActivityType=APPLICATION_ACTIVITY_TYPE
          waitingVisible=false nowVisible=true lastVisibleTime=-19s196ms
          resizeMode=RESIZE_MODE_RESIZEABLE_VIA_SDK_VERSION
          mLastReportedMultiWindowMode=false mLastReportedPictureInPictureMode=false
    Task id #90
    mFullscreen=true
    mBounds=null
    mMinWidth=-1
    mMinHeight=-1
    mLastNonFullscreenBounds=null
    * TaskRecord{de86d2f #90 A=com.yao.activity U=0 StackId=1 sz=6}
      userId=0 effectiveUid=u0a82 mCallingUid=u0a24 mUserSetupComplete=true mCallingPackage=com.google.android.apps.nexuslauncher
      affinity=com.yao.activity
      intent={act=android.intent.action.MAIN cat=[android.intent.category.LAUNCHER] flg=0x10200000 cmp=com.yao.activity/.MainActivity}
      realActivity=com.yao.activity/.MainActivity
      autoRemoveRecents=false isPersistable=true numFullscreen=6 taskType=0 mTaskToReturnTo=1
      rootWasReset=true mNeverRelinquishIdentity=true mReuseTask=false mLockTaskAuth=LOCK_TASK_AUTH_PINNABLE
      Activities=[ActivityRecord{73699f u0 com.yao.activity/.MainActivity t90}, ActivityRecord{d6bcc11 u0 com.yao.activity/.Main2Activity t90}, ActivityRecord{f50405 u0 com.yao.activity/.ActivityB t90}, ActivityRecord{e5279b9 u0 com.yao.activity/.ActivityC t90}, ActivityRecord{ed146ae u0 com.yao.activity/.ActivityA t90}, ActivityRecord{97f2fe3 u0 com.yao.activity/.ActivityF t90}]
      askedCompatMode=false inRecents=true isAvailable=true
      lastThumbnail=null lastThumbnailFile=/data/system_ce/0/recent_images/90_task_thumbnail.png
      stackId=1
      hasBeenVisible=true mResizeMode=RESIZE_MODE_RESIZEABLE_VIA_SDK_VERSION mSupportsPictureInPicture=false isResizeable=true firstActiveTime=1554878360651 lastActiveTime=1554878411102 (inactive for 20s)
      * Hist #5: ActivityRecord{97f2fe3 u0 com.yao.activity/.ActivityF t90}
          packageName=com.yao.activity processName=com.yao.activity
          launchedFromUid=10082 launchedFromPackage=com.yao.activity userId=0
          app=ProcessRecord{6b8e832 5670:com.yao.activity/u0a82}
          Intent { cmp=com.yao.activity/.ActivityF bnds=[352,706][548,902] }
          frontOfTask=false task=TaskRecord{de86d2f #90 A=com.yao.activity U=0 StackId=1 sz=6}
          taskAffinity=com.amazon.yao
          realActivity=com.yao.activity/.ActivityF
          baseDir=/data/app/com.yao.activity-tjVkMlwzbP4WBxrAkGHxPQ==/base.apk
          dataDir=/data/user/0/com.yao.activity
          stateNotNeeded=false componentSpecified=true mActivityType=0
          compat={560dpi} labelRes=0x7f0b0027 icon=0x7f0a0001 theme=0x7f0c0005
          mLastReportedConfigurations:
           mGlobalConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
           mOverrideConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          CurrentConfiguration={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          taskDescription: iconFilename=null label="null" primaryColor=ff008577
            backgroundColor=fffafafa
            statusBarColor=ff00574b
            navigationBarColor=ff000000
          launchFailed=false launchCount=0 lastLaunchTime=-47s64ms
          haveState=true icicle=Bundle[mParcelledData.dataSize=1512]
          state=STOPPED stopped=true delayedResume=false finishing=false
          keysPaused=false inHistory=true visible=false sleeping=false idle=true mStartingWindowState=STARTING_WINDOW_REMOVED
          fullscreen=true noDisplay=false immersive=false launchMode=0
          frozenBeforeDestroy=false forceNewConfig=false
          mActivityType=APPLICATION_ACTIVITY_TYPE
          waitingVisible=false nowVisible=false lastVisibleTime=-22s179ms
          resizeMode=RESIZE_MODE_RESIZEABLE_VIA_SDK_VERSION
          mLastReportedMultiWindowMode=false mLastReportedPictureInPictureMode=false
      * Hist #4: ActivityRecord{ed146ae u0 com.yao.activity/.ActivityA t90}
          packageName=com.yao.activity processName=com.yao.activity
          launchedFromUid=10082 launchedFromPackage=com.yao.activity userId=0
          app=ProcessRecord{6b8e832 5670:com.yao.activity/u0a82}
          Intent { cmp=com.yao.activity/.ActivityA }
          frontOfTask=false task=TaskRecord{de86d2f #90 A=com.yao.activity U=0 StackId=1 sz=6}
          taskAffinity=com.yao.activity
          realActivity=com.yao.activity/.ActivityA
          baseDir=/data/app/com.yao.activity-tjVkMlwzbP4WBxrAkGHxPQ==/base.apk
          dataDir=/data/user/0/com.yao.activity
          stateNotNeeded=false componentSpecified=true mActivityType=0
          compat={560dpi} labelRes=0x7f0b0027 icon=0x7f0a0001 theme=0x7f0c0005
          mLastReportedConfigurations:
           mGlobalConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
           mOverrideConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          CurrentConfiguration={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          taskDescription: iconFilename=null label="null" primaryColor=ff008577
            backgroundColor=fffafafa
            statusBarColor=ff00574b
            navigationBarColor=ff000000
          launchFailed=false launchCount=0 lastLaunchTime=-58s304ms
          haveState=true icicle=Bundle[mParcelledData.dataSize=1512]
          state=STOPPED stopped=true delayedResume=false finishing=false
          keysPaused=false inHistory=true visible=false sleeping=false idle=true mStartingWindowState=STARTING_WINDOW_NOT_SHOWN
          fullscreen=true noDisplay=false immersive=false launchMode=0
          frozenBeforeDestroy=false forceNewConfig=false
          mActivityType=APPLICATION_ACTIVITY_TYPE
          waitingVisible=false nowVisible=false lastVisibleTime=-57s717ms
          resizeMode=RESIZE_MODE_RESIZEABLE_VIA_SDK_VERSION
          mLastReportedMultiWindowMode=false mLastReportedPictureInPictureMode=false
      * Hist #3: ActivityRecord{e5279b9 u0 com.yao.activity/.ActivityC t90}
          packageName=com.yao.activity processName=com.yao.activity
          launchedFromUid=10082 launchedFromPackage=com.yao.activity userId=0
          app=ProcessRecord{6b8e832 5670:com.yao.activity/u0a82}
          Intent { cmp=com.yao.activity/.ActivityC }
          frontOfTask=false task=TaskRecord{de86d2f #90 A=com.yao.activity U=0 StackId=1 sz=6}
          taskAffinity=com.yao.activity
          realActivity=com.yao.activity/.ActivityC
          baseDir=/data/app/com.yao.activity-tjVkMlwzbP4WBxrAkGHxPQ==/base.apk
          dataDir=/data/user/0/com.yao.activity
          stateNotNeeded=false componentSpecified=true mActivityType=0
          compat={560dpi} labelRes=0x7f0b0027 icon=0x7f0a0001 theme=0x7f0c0005
          mLastReportedConfigurations:
           mGlobalConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
           mOverrideConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          CurrentConfiguration={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          taskDescription: iconFilename=null label="null" primaryColor=ff008577
            backgroundColor=fffafafa
            statusBarColor=ff00574b
            navigationBarColor=ff000000
          launchFailed=false launchCount=0 lastLaunchTime=-1m1s135ms
          haveState=true icicle=Bundle[mParcelledData.dataSize=1512]
          state=STOPPED stopped=true delayedResume=false finishing=false
          keysPaused=false inHistory=true visible=false sleeping=false idle=true mStartingWindowState=STARTING_WINDOW_NOT_SHOWN
          fullscreen=true noDisplay=false immersive=false launchMode=1
          frozenBeforeDestroy=false forceNewConfig=false
          mActivityType=APPLICATION_ACTIVITY_TYPE
          waitingVisible=false nowVisible=false lastVisibleTime=-1m0s573ms
          resizeMode=RESIZE_MODE_RESIZEABLE_VIA_SDK_VERSION
          mLastReportedMultiWindowMode=false mLastReportedPictureInPictureMode=false
      * Hist #2: ActivityRecord{f50405 u0 com.yao.activity/.ActivityB t90}
          packageName=com.yao.activity processName=com.yao.activity
          launchedFromUid=10082 launchedFromPackage=com.yao.activity userId=0
          app=ProcessRecord{6b8e832 5670:com.yao.activity/u0a82}
          Intent { flg=0x10000000 cmp=com.yao.activity/.ActivityB }
          frontOfTask=false task=TaskRecord{de86d2f #90 A=com.yao.activity U=0 StackId=1 sz=6}
          taskAffinity=com.yao.activity
          realActivity=com.yao.activity/.ActivityB
          baseDir=/data/app/com.yao.activity-tjVkMlwzbP4WBxrAkGHxPQ==/base.apk
          dataDir=/data/user/0/com.yao.activity
          stateNotNeeded=false componentSpecified=true mActivityType=0
          compat={560dpi} labelRes=0x7f0b0027 icon=0x7f0a0001 theme=0x7f0c0005
          mLastReportedConfigurations:
           mGlobalConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
           mOverrideConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          CurrentConfiguration={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          taskDescription: iconFilename=null label="null" primaryColor=ff008577
            backgroundColor=fffafafa
            statusBarColor=ff00574b
            navigationBarColor=ff000000
          launchFailed=false launchCount=0 lastLaunchTime=-1m2s942ms
          haveState=true icicle=Bundle[mParcelledData.dataSize=1512]
          state=STOPPED stopped=true delayedResume=false finishing=false
          keysPaused=false inHistory=true visible=false sleeping=false idle=true mStartingWindowState=STARTING_WINDOW_NOT_SHOWN
          fullscreen=true noDisplay=false immersive=false launchMode=2
          frozenBeforeDestroy=false forceNewConfig=false
          mActivityType=APPLICATION_ACTIVITY_TYPE
          waitingVisible=false nowVisible=false lastVisibleTime=-1m2s320ms
          resizeMode=RESIZE_MODE_RESIZEABLE_VIA_SDK_VERSION
          mLastReportedMultiWindowMode=false mLastReportedPictureInPictureMode=false
      * Hist #1: ActivityRecord{d6bcc11 u0 com.yao.activity/.Main2Activity t90}
          packageName=com.yao.activity processName=com.yao.activity
          launchedFromUid=10082 launchedFromPackage=com.yao.activity userId=0
          app=ProcessRecord{6b8e832 5670:com.yao.activity/u0a82}
          Intent { cmp=com.yao.activity/.Main2Activity }
          frontOfTask=false task=TaskRecord{de86d2f #90 A=com.yao.activity U=0 StackId=1 sz=6}
          taskAffinity=com.yao.activity
          realActivity=com.yao.activity/.Main2Activity
          baseDir=/data/app/com.yao.activity-tjVkMlwzbP4WBxrAkGHxPQ==/base.apk
          dataDir=/data/user/0/com.yao.activity
          stateNotNeeded=false componentSpecified=true mActivityType=0
          compat={560dpi} labelRes=0x7f0b0027 icon=0x7f0a0001 theme=0x7f0c0005
          mLastReportedConfigurations:
           mGlobalConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
           mOverrideConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          CurrentConfiguration={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          taskDescription: iconFilename=null label="null" primaryColor=ff008577
            backgroundColor=fffafafa
            statusBarColor=ff00574b
            navigationBarColor=ff000000
          launchFailed=false launchCount=0 lastLaunchTime=-1m8s52ms
          haveState=true icicle=Bundle[mParcelledData.dataSize=1512]
          state=STOPPED stopped=true delayedResume=false finishing=false
          keysPaused=false inHistory=true visible=false sleeping=false idle=true mStartingWindowState=STARTING_WINDOW_NOT_SHOWN
          fullscreen=true noDisplay=false immersive=false launchMode=0
          frozenBeforeDestroy=false forceNewConfig=false
          mActivityType=APPLICATION_ACTIVITY_TYPE
          waitingVisible=false nowVisible=false lastVisibleTime=-1m7s422ms
          resizeMode=RESIZE_MODE_RESIZEABLE_VIA_SDK_VERSION
          mLastReportedMultiWindowMode=false mLastReportedPictureInPictureMode=false
      * Hist #0: ActivityRecord{73699f u0 com.yao.activity/.MainActivity t90}
          packageName=com.yao.activity processName=com.yao.activity
          launchedFromUid=10024 launchedFromPackage=com.google.android.apps.nexuslauncher userId=0
          app=ProcessRecord{6b8e832 5670:com.yao.activity/u0a82}
          Intent { act=android.intent.action.MAIN cat=[android.intent.category.LAUNCHER] flg=0x10200000 cmp=com.yao.activity/.MainActivity bnds=[316,675][585,1024] }
          frontOfTask=true task=TaskRecord{de86d2f #90 A=com.yao.activity U=0 StackId=1 sz=6}
          taskAffinity=com.yao.activity
          realActivity=com.yao.activity/.MainActivity
          baseDir=/data/app/com.yao.activity-tjVkMlwzbP4WBxrAkGHxPQ==/base.apk
          dataDir=/data/user/0/com.yao.activity
          stateNotNeeded=false componentSpecified=true mActivityType=0
          compat={560dpi} labelRes=0x7f0b0027 icon=0x7f0a0001 theme=0x7f0c0005
          mLastReportedConfigurations:
           mGlobalConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
           mOverrideConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          CurrentConfiguration={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          taskDescription: iconFilename=null label="null" primaryColor=ff008577
            backgroundColor=fffafafa
            statusBarColor=ff00574b
            navigationBarColor=ff000000
          launchFailed=false launchCount=0 lastLaunchTime=-1m10s499ms
          haveState=true icicle=Bundle[mParcelledData.dataSize=1208]
          state=STOPPED stopped=true delayedResume=false finishing=false
          keysPaused=false inHistory=true visible=false sleeping=false idle=true mStartingWindowState=STARTING_WINDOW_REMOVED
          fullscreen=true noDisplay=false immersive=false launchMode=0
          frozenBeforeDestroy=false forceNewConfig=false
          mActivityType=APPLICATION_ACTIVITY_TYPE
          waitingVisible=false nowVisible=false lastVisibleTime=-1m9s374ms
          resizeMode=RESIZE_MODE_RESIZEABLE_VIA_SDK_VERSION
          mLastReportedMultiWindowMode=false mLastReportedPictureInPictureMode=false
    Task id #86
    mFullscreen=true
    mBounds=null
    mMinWidth=-1
    mMinHeight=-1
    mLastNonFullscreenBounds=null
    * TaskRecord{e1c47ba #86 A=com.yao.activity U=0 StackId=1 sz=1}
      userId=0 effectiveUid=u0a82 mCallingUid=u0a82 mUserSetupComplete=true mCallingPackage=com.yao.activity
      affinity=com.yao.activity
      intent={flg=0x10000000 cmp=com.yao.activity/.ActivityD}
      realActivity=com.yao.activity/.ActivityD
      autoRemoveRecents=false isPersistable=true numFullscreen=1 taskType=0 mTaskToReturnTo=1
      rootWasReset=false mNeverRelinquishIdentity=true mReuseTask=false mLockTaskAuth=LOCK_TASK_AUTH_PINNABLE
      Activities=[ActivityRecord{db7809b u0 com.yao.activity/.ActivityD t86}]
      askedCompatMode=false inRecents=false isAvailable=true
      lastThumbnail=null lastThumbnailFile=/data/system_ce/0/recent_images/86_task_thumbnail.png
      stackId=1
      hasBeenVisible=true mResizeMode=RESIZE_MODE_RESIZEABLE_VIA_SDK_VERSION mSupportsPictureInPicture=false isResizeable=true firstActiveTime=1554869388992 lastActiveTime=1554869391235 (inactive for 9039s)
      * Hist #0: ActivityRecord{db7809b u0 com.yao.activity/.ActivityD t86}
          packageName=com.yao.activity processName=com.yao.activity
          launchedFromUid=10082 launchedFromPackage=com.yao.activity userId=0
          app=null
          Intent { flg=0x10000000 cmp=com.yao.activity/.ActivityD }
          frontOfTask=true task=TaskRecord{e1c47ba #86 A=com.yao.activity U=0 StackId=1 sz=1}
          taskAffinity=com.yao.activity
          realActivity=com.yao.activity/.ActivityD
          baseDir=/data/app/com.yao.activity-tjVkMlwzbP4WBxrAkGHxPQ==/base.apk
          dataDir=/data/user/0/com.yao.activity
          stateNotNeeded=false componentSpecified=true mActivityType=0
          compat={560dpi} labelRes=0x7f0b0027 icon=0x7f0a0001 theme=0x7f0c0005
          mLastReportedConfigurations:
           mGlobalConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
           mOverrideConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          CurrentConfiguration={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          taskDescription: iconFilename=null label="null" primaryColor=ff008577
            backgroundColor=fffafafa
            statusBarColor=ff00574b
            navigationBarColor=ff000000
          launchFailed=false launchCount=0 lastLaunchTime=-2h30m42s193ms
          haveState=true icicle=Bundle[mParcelledData.dataSize=1512]
          state=DESTROYED stopped=true delayedResume=false finishing=false
          keysPaused=false inHistory=true visible=false sleeping=false idle=true mStartingWindowState=STARTING_WINDOW_REMOVED
          fullscreen=true noDisplay=false immersive=false launchMode=3
          frozenBeforeDestroy=false forceNewConfig=false
          mActivityType=APPLICATION_ACTIVITY_TYPE
          waitingVisible=false nowVisible=false lastVisibleTime=-2h30m41s321ms
          resizeMode=RESIZE_MODE_RESIZEABLE_VIA_SDK_VERSION
          mLastReportedMultiWindowMode=false mLastReportedPictureInPictureMode=false

    Running activities (most recent first):
      TaskRecord{e5bdf0e #93 A=com.amazon.yao U=0 StackId=1 sz=1}
        Run #6: ActivityRecord{6465198 u0 com.yao.activity/.ActivityE t93}
      TaskRecord{de86d2f #90 A=com.yao.activity U=0 StackId=1 sz=6}
        Run #5: ActivityRecord{97f2fe3 u0 com.yao.activity/.ActivityF t90}
        Run #4: ActivityRecord{ed146ae u0 com.yao.activity/.ActivityA t90}
        Run #3: ActivityRecord{e5279b9 u0 com.yao.activity/.ActivityC t90}
        Run #2: ActivityRecord{f50405 u0 com.yao.activity/.ActivityB t90}
        Run #1: ActivityRecord{d6bcc11 u0 com.yao.activity/.Main2Activity t90}
        Run #0: ActivityRecord{73699f u0 com.yao.activity/.MainActivity t90}

    mResumedActivity: ActivityRecord{6465198 u0 com.yao.activity/.ActivityE t93}
    mLastPausedActivity: ActivityRecord{97f2fe3 u0 com.yao.activity/.ActivityF t90}

  Stack #0:
  mFullscreen=true
  isSleeping=false
  mBounds=null
    Task id #18
    mFullscreen=true
    mBounds=null
    mMinWidth=-1
    mMinHeight=-1
    mLastNonFullscreenBounds=null
    * TaskRecord{fa7d5f3 #18 I=com.google.android.apps.nexuslauncher/.NexusLauncherActivity U=0 StackId=0 sz=1}
      userId=0 effectiveUid=u0a24 mCallingUid=u0a29 mUserSetupComplete=true mCallingPackage=com.android.systemui
      intent={act=android.intent.action.MAIN cat=[android.intent.category.HOME] flg=0x10000100 cmp=com.google.android.apps.nexuslauncher/.NexusLauncherActivity}
      realActivity=com.google.android.apps.nexuslauncher/.NexusLauncherActivity
      autoRemoveRecents=false isPersistable=true numFullscreen=1 taskType=1 mTaskToReturnTo=0
      rootWasReset=false mNeverRelinquishIdentity=true mReuseTask=false mLockTaskAuth=LOCK_TASK_AUTH_PINNABLE
      Activities=[ActivityRecord{7cd0921 u0 com.google.android.apps.nexuslauncher/.NexusLauncherActivity t18}]
      askedCompatMode=false inRecents=true isAvailable=true
      lastThumbnail=null lastThumbnailFile=/data/system_ce/0/recent_images/18_task_thumbnail.png
      stackId=0
      hasBeenVisible=true mResizeMode=RESIZE_MODE_RESIZEABLE mSupportsPictureInPicture=false isResizeable=true firstActiveTime=1554793451340 lastActiveTime=1554878408617 (inactive for 22s)
      * Hist #0: ActivityRecord{7cd0921 u0 com.google.android.apps.nexuslauncher/.NexusLauncherActivity t18}
          packageName=com.google.android.apps.nexuslauncher processName=com.google.android.apps.nexuslauncher
          launchedFromUid=0 launchedFromPackage=null userId=0
          app=ProcessRecord{384daeb 15662:com.google.android.apps.nexuslauncher/u0a24}
          Intent { act=android.intent.action.MAIN cat=[android.intent.category.HOME] flg=0x10000100 cmp=com.google.android.apps.nexuslauncher/.NexusLauncherActivity }
          frontOfTask=true task=TaskRecord{fa7d5f3 #18 I=com.google.android.apps.nexuslauncher/.NexusLauncherActivity U=0 StackId=0 sz=1}
          taskAffinity=null
          realActivity=com.google.android.apps.nexuslauncher/.NexusLauncherActivity
          baseDir=/system/priv-app/NexusLauncherPrebuilt/NexusLauncherPrebuilt.apk
          dataDir=/data/user/0/com.google.android.apps.nexuslauncher
          stateNotNeeded=true componentSpecified=false mActivityType=1
          compat={560dpi} labelRes=0x7f0c008c icon=0x7f02002b theme=0x7f120002
          mLastReportedConfigurations:
           mGlobalConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
           mOverrideConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          CurrentConfiguration={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          taskDescription: iconFilename=null label="null" primaryColor=fff5f5f5
            backgroundColor=fffafafa
            statusBarColor=0
            navigationBarColor=0
          launchFailed=false launchCount=0 lastLaunchTime=-11h58m24s892ms
          haveState=true icicle=Bundle[mParcelledData.dataSize=3920]
          state=STOPPED stopped=true delayedResume=false finishing=false
          keysPaused=false inHistory=true visible=false sleeping=false idle=true mStartingWindowState=STARTING_WINDOW_NOT_SHOWN
          fullscreen=true noDisplay=false immersive=false launchMode=2
          frozenBeforeDestroy=false forceNewConfig=false
          mActivityType=HOME_ACTIVITY_TYPE
          waitingVisible=false nowVisible=false lastVisibleTime=-23s262ms
          connections=[]
          resizeMode=RESIZE_MODE_RESIZEABLE
          mLastReportedMultiWindowMode=false mLastReportedPictureInPictureMode=false

    Running activities (most recent first):
      TaskRecord{fa7d5f3 #18 I=com.google.android.apps.nexuslauncher/.NexusLauncherActivity U=0 StackId=0 sz=1}
        Run #0: ActivityRecord{7cd0921 u0 com.google.android.apps.nexuslauncher/.NexusLauncherActivity t18}

    mLastPausedActivity: ActivityRecord{7cd0921 u0 com.google.android.apps.nexuslauncher/.NexusLauncherActivity t18}

  Stack #5:
  mFullscreen=true
  isSleeping=false
  mBounds=null
    Task id #23
    mFullscreen=true
    mBounds=null
    mMinWidth=-1
    mMinHeight=-1
    mLastNonFullscreenBounds=null
    * TaskRecord{173e0ae #23 A=com.android.systemui U=0 StackId=5 sz=1}
      userId=0 effectiveUid=u0a29 mCallingUid=u0a29 mUserSetupComplete=true mCallingPackage=com.android.systemui
      affinity=com.android.systemui
      intent={flg=0x10804000 cmp=com.android.systemui/.recents.RecentsActivity}
      realActivity=com.android.systemui/.recents.RecentsActivity
      autoRemoveRecents=false isPersistable=false numFullscreen=1 taskType=2 mTaskToReturnTo=1
      rootWasReset=false mNeverRelinquishIdentity=true mReuseTask=false mLockTaskAuth=LOCK_TASK_AUTH_PINNABLE
      Activities=[ActivityRecord{612b379 u0 com.android.systemui/.recents.RecentsActivity t23}]
      askedCompatMode=false inRecents=true isAvailable=true
      lastThumbnail=null lastThumbnailFile=/data/system_ce/0/recent_images/23_task_thumbnail.png
      stackId=5
      hasBeenVisible=true mResizeMode=RESIZE_MODE_RESIZEABLE mSupportsPictureInPicture=false isResizeable=true firstActiveTime=1554798333586 lastActiveTime=1554878401118 (inactive for 30s)
      * Hist #0: ActivityRecord{612b379 u0 com.android.systemui/.recents.RecentsActivity t23}
          packageName=com.android.systemui processName=com.android.systemui
          launchedFromUid=10029 launchedFromPackage=com.android.systemui userId=0
          app=ProcessRecord{7407e82 15204:com.android.systemui/u0a29}
          Intent { flg=0x10804000 cmp=com.android.systemui/.recents.RecentsActivity }
          frontOfTask=true task=TaskRecord{173e0ae #23 A=com.android.systemui U=0 StackId=5 sz=1}
          taskAffinity=com.android.systemui
          realActivity=com.android.systemui/.recents.RecentsActivity
          baseDir=/system/priv-app/SystemUIGoogle/SystemUIGoogle.apk
          dataDir=/data/user_de/0/com.android.systemui
          stateNotNeeded=true componentSpecified=true mActivityType=2
          compat={560dpi} labelRes=0x7f110061 icon=0x7f08020c theme=0x7f1200fe
          mLastReportedConfigurations:
           mGlobalConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
           mOverrideConfig={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          CurrentConfiguration={1.0 310mcc260mnc [en_US] ldltr sw411dp w411dp h659dp 560dpi nrml port finger qwerty/v/v -nav/h appBounds=Rect(0, 0 - 1440, 2392) s.6}
          taskDescription: iconFilename=null label="null" primaryColor=ff212121
            backgroundColor=ff303030
            statusBarColor=0
            navigationBarColor=0
          launchFailed=false launchCount=0 lastLaunchTime=-10h37m3s132ms
          haveState=true icicle=Bundle[mParcelledData.dataSize=1320]
          state=STOPPED stopped=true delayedResume=false finishing=false
          keysPaused=false inHistory=true visible=false sleeping=false idle=true mStartingWindowState=STARTING_WINDOW_NOT_SHOWN
          fullscreen=true noDisplay=false immersive=false launchMode=3
          frozenBeforeDestroy=false forceNewConfig=false
          mActivityType=RECENTS_ACTIVITY_TYPE
          waitingVisible=false nowVisible=false lastVisibleTime=-34s431ms
          resizeMode=RESIZE_MODE_RESIZEABLE
          mLastReportedMultiWindowMode=false mLastReportedPictureInPictureMode=false

    Running activities (most recent first):
      TaskRecord{173e0ae #23 A=com.android.systemui U=0 StackId=5 sz=1}
        Run #0: ActivityRecord{612b379 u0 com.android.systemui/.recents.RecentsActivity t23}

    mLastPausedActivity: ActivityRecord{612b379 u0 com.android.systemui/.recents.RecentsActivity t23}

  ResumedActivity: ActivityRecord{6465198 u0 com.yao.activity/.ActivityE t93}
  mFocusedStack=ActivityStack{7e62e3e stackId=1, 3 tasks} mLastFocusedStack=ActivityStack{7e62e3e stackId=1, 3 tasks}
  mCurTaskIdForUser={0=93}
  mUserStackInFront={}
  mStacks={0=ActivityStack{4e6106b stackId=0, 1 tasks}, 1=ActivityStack{7e62e3e stackId=1, 3 tasks}, 5=ActivityStack{cb7c7c8 stackId=5, 1 tasks}}
  mLockTaskModeState=NONE  mLockTaskPackages (userId:packages)=
    0:[]
 mLockTaskModeTasks[]
  KeyguardController:
    mKeyguardShowing=false
    mKeyguardGoingAway=false
    mOccluded=false
    mDismissingKeyguardActivity=null
    mDismissalRequested=false
    mVisibilityTransactionDepth=0 

