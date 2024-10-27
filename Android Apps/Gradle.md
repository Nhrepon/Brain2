

## Gradle.propertise
```Android
android.useAndroidX=true
android.enableJetifier=true

// R8 code shrinker
android.enableR8=true

```


## Setting.gradle
```Android
pluginManagement {
    repositories {
        gradlePluginPortal()
        google()
        mavenCentral()
    }
}
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
        maven{url('https://jcenter.bintray.com')}
    }
}
rootProject.name = "PDF Reader & Viewer"
include ':app'

```

# Shrink resources
Build.gradle
```java
android {    
buildTypes {
release { 

minifyEnabled true
shrinkResources true 

}} 
}
```

```kotlin
android {    
buildTypes {        
getByName("release") {    

isMinifyEnabled = true 
isShrinkResources = true  

		}}
}
```