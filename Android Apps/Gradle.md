

## Gradle.propertise
```Android
android.useAndroidX=true
android.enableJetifier=true
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