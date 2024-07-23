## Home page with navigation drawer and bottom navigation

```xml
<?xml version="1.0" encoding="utf-8"?>  
<androidx.drawerlayout.widget.DrawerLayout xmlns:android="http://schemas.android.com/apk/res/android"  
    xmlns:app="http://schemas.android.com/apk/res-auto"  
    xmlns:tools="http://schemas.android.com/tools"  
    android:id="@+id/DrawerLayout"  
    android:layout_width="match_parent"  
    android:layout_height="match_parent"  
    tools:context=".Home"  
    tools:openDrawer="start"  
    >  
      
    <androidx.coordinatorlayout.widget.CoordinatorLayout  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        >  
    <com.google.android.material.appbar.AppBarLayout  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content">  
  
        <com.google.android.material.appbar.MaterialToolbar  
            android:id="@+id/materialToolbar"  
            android:layout_width="match_parent"  
            android:layout_height="?attr/actionBarSize"  
            app:menu="@menu/toolbar"  
            app:title="@string/app_name"  
            android:layout_marginTop="20dp"  
            >  
  
        </com.google.android.material.appbar.MaterialToolbar>  
    </com.google.android.material.appbar.AppBarLayout>  
  
  
        <RelativeLayout            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:layout_marginTop="?actionBarSize"  
            >  
  
            <androidx.recyclerview.widget.RecyclerView  
                android:id="@+id/recyclerView"  
                android:layout_width="match_parent"  
                android:layout_height="match_parent"  
                android:layout_marginBottom="?actionBarSize"  
                android:background="@color/white"  
                />  
  
            <com.google.android.material.bottomnavigation.BottomNavigationView                android:id="@+id/bottomNavigationView"  
                android:layout_width="match_parent"  
                android:layout_height="wrap_content"  
                android:layout_alignParentBottom="true"  
                app:menu="@menu/bottom_menu"  
                app:itemIconSize="32dp"  
                app:itemIconTint="@color/white"  
                />  
        </RelativeLayout>  
  
  
    </androidx.coordinatorlayout.widget.CoordinatorLayout>  
  
  
  
    <com.google.android.material.navigation.NavigationView        android:id="@+id/navigationView"  
        android:layout_width="wrap_content"  
        android:layout_height="match_parent"  
        android:layout_gravity="start"  
        android:background="#D3D3D3"  
        app:headerLayout="@layout/navigation_header"  
        app:menu="@menu/navigation_menu"  
        app:itemTextColor="@color/black"  
        app:itemIconTint="@color/black"  
  
        />  
  
  
</androidx.drawerlayout.widget.DrawerLayout>
```


