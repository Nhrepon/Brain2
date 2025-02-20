
# Step 01
go to settings.gradle
```grovy
pluginManagement {
  repositories {
    google()
    mavenCentral()
    gradlePluginPortal()
  }
}

dependencyResolutionManagement {
  repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
  repositories {
    google()
    mavenCentral()
  }
}

rootProject.name = "My Application"
include ':app'
```

# Step 2
go to build.gradle
```grovy
dependencies {
  implementation 'com.google.android.gms:play-services-ads:23.6.0'
}
```

# Step 3
go to manifest
```json
<manifest>
  <application>
    <!-- Sample AdMob app ID: ca-app-pub-3940256099942544~3347511713 -->
    <meta-data
        android:name="com.google.android.gms.ads.APPLICATION_ID"
        android:value="ca-app-pub-xxxxxxxxxxxxxxxx~yyyyyyyyyy"/>

<!-- For apps targeting Android 13 or higher & GMA SDK version 20.3.0 or lower -->
   <uses-permission android:name="com.google.android.gms.permission.AD_ID"/>
  </application>
</manifest>
```



```

```
