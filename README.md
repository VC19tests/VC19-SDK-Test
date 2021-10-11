# VC19-SDK-Test

**Unofficial 'raw' Code for VerificaC19 Android SDK tests**

Whether you cloned or downloaded the 'zipped' sources you will either find the sources in the chosen checkout-directory or get a zip file with the source code, which you can expand to a folder of your choice.

In order to successfully build and run a VC19 project with SDK, you must get also a [SDK active branch of VerificaC19](https://github.com/ministero-salute/it-dgc-verificaC19-android/branches/active) + the [DGCA Core](https://github.com/eu-digital-green-certificates/dgca-app-core-android). 

All 3 projects should be located at the same folder level. 

```
android-app
|___it-dgc-verificaC19-android-branch
|___dgca-app-core-android
|___VC19-Sdk-Test
```

---------------------------------------------

**Arrangements in order to build VerificaC19 branches with SDK dependency**

- **1.** Rename the VC19-SDK-Test folder to it-dgc-verificac19-sdk-android. 

Otherwise, you can edit gradle.settings in order to declare both DGCA core & VC19-SDK-Test projects.

```
include ':app'
include ':dgc-sdk'
include ':decoder'
rootProject.name = "dgp-whitelabel-android"
project(':dgc-sdk').projectDir = new File("../VC19-SDK-Test/sdk")
project(':decoder').projectDir = new File("../dgca-app-core-android/decoder") 
```

- **2.** Edit FirstActivity.kt & VerificationFragment.kt in order to disable VC19 SDK version checks & avoid exceptions because of NOT_GREEN_PASS / NOT_EU_DCC flag changes.

You can find the required commits/changes [HERE](https://github.com/VC19bkp/it-dgc-verificaC19-android-SDKtest/commit/1c09aa810212afad1972bfe7a4c87af1369330a2).

---------------------------------------------

**Sample VC19 app built with SDK dependency (based on 1.1.2 release - develop-candidate branch)**

- [VirusTotal Analysis](https://www.virustotal.com/gui/file/7c212e218647f4cbbadb24a752999ea339587ee42223e704ef4206a345ae184f)

- [APKLab submission](https://apklab.io/apk.html?hash=7c212e218647f4cbbadb24a752999ea339587ee42223e704ef4206a345ae184f)

- [Pithus Report](https://beta.pithus.org/report/7c212e218647f4cbbadb24a752999ea339587ee42223e704ef4206a345ae184f)

- Built Universal APK
[app-release_VC19_1.1.2_SDK_Test.zip](https://github.com/VC19tests/VC19-SDK-Test/files/7324467/app-release_VC19_1.1.2_SDK_Test.zip)
