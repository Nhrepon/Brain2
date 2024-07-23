## Menu > navigation_menu.xml
```xml
<?xml version="1.0" encoding="utf-8"?>  
<menu xmlns:android="http://schemas.android.com/apk/res/android">  
    <group>  
        <item  
            android:id="@+id/home"  
            android:icon="@drawable/home"  
            android:title="Home"  
            />  
        <item            android:id="@+id/trending"  
            android:icon="@drawable/home"  
            android:title="Trending"  
            />  
  
        <item            android:id="@+id/bookmark"  
            android:icon="@drawable/home"  
            android:title="Bookmark"  
            />  
    </group>  
    <group>        <item  
            android:id="@+id/status"  
            android:icon="@drawable/home"  
            android:title="Status"  
            />  
    </group>  
</menu>
```



## Menu > toolbar.xml
```xml
<?xml version="1.0" encoding="utf-8"?>  
<menu xmlns:android="http://schemas.android.com/apk/res/android"  
    xmlns:app="http://schemas.android.com/apk/res-auto">  
    <item  
        android:id="@+id/status"  
        android:icon="@drawable/home"  
        android:title="Status"  
        app:showAsAction="ifRoom"  
        />  
  
    <item        android:id="@+id/status1"  
        android:icon="@drawable/home"  
        android:title="Status"  
        app:showAsAction="ifRoom"  
        />  
  
    <item        android:id="@+id/status2"  
        android:icon="@drawable/home"  
        android:title="Status"  
        app:showAsAction="ifRoom"  
        />  
</menu>
```


## Menu > bottom_menu.xml
```xml
<?xml version="1.0" encoding="utf-8"?>  
<menu xmlns:android="http://schemas.android.com/apk/res/android">  
  
    <item android:id="@+id/home"  
        android:icon="@drawable/home"  
        android:iconTint="@color/black"  
        android:title="Home" />  
    <item android:id="@+id/search"  
        android:icon="@drawable/account"  
        android:iconTint="@color/black"  
        android:title="Search"  
        />  
    <item android:id="@+id/add"  
        android:icon="@drawable/account"  
        android:iconTint="@color/black"  
        android:title="TODO" />  
  
</menu>
```


