## Home page with navigation drawer and bottom navigation

```xml

<?xml version="1.0" encoding="utf-8"?>  
<androidx.drawerlayout.widget.DrawerLayout xmlns:android="http://schemas.android.com/apk/res/android"  
    xmlns:app="http://schemas.android.com/apk/res-auto"  
    xmlns:tools="http://schemas.android.com/tools"  
    android:id="@+id/drawerLayout"  
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
            app:navigationIcon="@drawable/menu_icon"  
            android:layout_marginLeft="20dp"  
            app:titleTextColor="@color/secondary"  
            app:navigationIconTint="@color/secondary"  
  
            >  
  
        </com.google.android.material.appbar.MaterialToolbar>  
    </com.google.android.material.appbar.AppBarLayout>  
  
            <FrameLayout                android:id="@+id/frameLayout"  
                android:layout_width="match_parent"  
                android:layout_height="match_parent"  
                android:layout_marginTop="?actionBarSize"  
                android:background="@color/white"  
                >  
  
            </FrameLayout>  
  
    </androidx.coordinatorlayout.widget.CoordinatorLayout>  
  
  
  
    <com.google.android.material.navigation.NavigationView        android:id="@+id/navigationView"  
        android:layout_width="wrap_content"  
        android:layout_height="match_parent"  
        android:layout_gravity="start"  
        app:headerLayout="@layout/navigation_header"  
        app:menu="@menu/navigation_menu"  
        app:itemTextColor="@color/primary"  
        app:itemIconSize="32dp"  
        app:itemIconTint="@color/primary"  
        android:background="@color/white"  
        />  
  
  
</androidx.drawerlayout.widget.DrawerLayout>


```

```java
 
public class Home extends AppCompatActivity {  
  
    DrawerLayout drawerLayout;  
    MaterialToolbar materialToolbar;  
    FrameLayout frameLayout;  
    NavigationView navigationView;  
  
  
    @Override  
    protected void onCreate(Bundle savedInstanceState) {  
        super.onCreate(savedInstanceState);  
        EdgeToEdge.enable(this);  
        setContentView(R.layout.activity_home);  
  
        drawerLayout = findViewById(R.id.drawerLayout);  
        materialToolbar = findViewById(R.id.materialToolbar);  
        frameLayout = findViewById(R.id.frameLayout);  
        navigationView = findViewById(R.id.navigationView);  
  
        // Toggle drawer  
        ActionBarDrawerToggle toggle = new ActionBarDrawerToggle(  
                Home.this, drawerLayout, materialToolbar, R.string.drawerClose, R.string.drawerOpen  
        );  
        drawerLayout.addDrawerListener(toggle);  
  
  
  
        //////////////////////////////////////  
        FragmentManager fragmentManager = getSupportFragmentManager();  
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();  
        fragmentTransaction.add(R.id.frameLayout, new HomeFragment());  
        fragmentTransaction.commit();  
  
        //////////////////////////////////////////////////////////////////  
        navigationView.setNavigationItemSelectedListener(new NavigationView.OnNavigationItemSelectedListener() {  
            @Override  
            public boolean onNavigationItemSelected(@NonNull MenuItem item) {  
  
                if (item.getItemId() == R.id.home){  
  
                    FragmentManager fragmentManager = getSupportFragmentManager();  
                    FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();  
                    fragmentTransaction.add(R.id.frameLayout, new HomeFragment());  
                    fragmentTransaction.commit();  
  
                } else if(item.getItemId() == R.id.trending){  
                    FragmentManager fragmentManager = getSupportFragmentManager();  
                    FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();  
                    fragmentTransaction.add(R.id.frameLayout, new TrendingFragment());  
                    fragmentTransaction.commit();  
                } else if(item.getItemId() == R.id.bookmark){  
                    FragmentManager fragmentManager = getSupportFragmentManager();  
                    FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();  
                    fragmentTransaction.add(R.id.frameLayout, new BookmarkFragment());  
                    fragmentTransaction.commit();  
                }  
  
                return true;  
            }  
        });  
  
  
  
  
  
  
  
  
  
    }  
  
  
    ////// Confirm exit /////////////////////////////////////////////////////////////  
  
    @Override  
    public void onBackPressed() {  
        //super.onBackPressed();  
        //finishAffinity();        new AlertDialog.Builder(Home.this)  
                .setTitle("Confirm Exit?")  
                .setMessage("Press 'Yes' to exit.")  
                .setNegativeButton(  
                        "No, Thanks!", new DialogInterface.OnClickListener() {  
                            @Override  
                            public void onClick(DialogInterface dialog, int which) {  
                                dialog.dismiss();  
                            }  
                        }  
                )  
                .setPositiveButton("Yes, Exit now!", new DialogInterface.OnClickListener() {  
                    @Override  
                    public void onClick(DialogInterface dialog, int which) {  
                        dialog.dismiss();  
                        finishAffinity();  
                        finish();  
                    }  
                })  
                .show();  
  
    }  
}
```

# Home fragment
```xml
<?xml version="1.0" encoding="utf-8"?>  
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"  
    xmlns:tools="http://schemas.android.com/tools"  
    android:layout_width="match_parent"  
    android:layout_height="match_parent"  
    tools:context=".HomeFragment"  
    android:orientation="vertical"  
    android:padding="15dp"  
    android:background="@color/primary"  
    >  
  
  
    <androidx.recyclerview.widget.RecyclerView  
        android:id="@+id/recyclerView"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        />  
  
  
</LinearLayout>
```

## Quotes item
```xml
<?xml version="1.0" encoding="utf-8"?>  
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"  
    android:layout_width="match_parent"  
    android:layout_height="wrap_content"  
    xmlns:app="http://schemas.android.com/apk/res-auto"  
    android:orientation="vertical"  
    android:id="@+id/quotesItem"  
    android:padding="15dp"  
    android:layout_marginVertical="10dp"  
    android:background="@drawable/border_radius_shadow"  
    >  
    <TextView  
        android:id="@+id/quote"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:text="Man is mortal and love is imortal!"  
        android:textColor="@color/black"  
        android:textSize="18sp"  
        />  
    <TextView        android:id="@+id/authore"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:text=" - Nur hossain "  
        android:textColor="@color/black"  
        android:textSize="12sp"  
        android:gravity="end"  
        />  
  
</LinearLayout>
```


# Home fragment java code
```java

public class HomeFragment extends Fragment {  
  
RecyclerView recyclerView;  
   
  
    @Override  
    public View onCreateView(LayoutInflater inflater, ViewGroup container,  
                             Bundle savedInstanceState) {  
        // Inflate the layout for this fragment  
        View fragmentView = inflater.inflate(R.layout.fragment_home, container, false);  
  
        recyclerView = fragmentView.findViewById(R.id.recyclerView);  
  
        recycleAdapter adapter = new recycleAdapter();  
        recyclerView.setAdapter(adapter);  
        recyclerView.setLayoutManager(new LinearLayoutManager(getActivity()));  
  
        return fragmentView;  
    }  
  
    //////////////////////////////////////////////////////////////////  
    private class recycleAdapter extends RecyclerView.Adapter<recycleAdapter.recyleViewHolder>{  
  
  
        // manual create  
        private class recyleViewHolder extends RecyclerView.ViewHolder{  
            LinearLayout quotesItem;  
            TextView quote, authore;  
  
  
            public recyleViewHolder(@NonNull View itemView) {  
                super(itemView);  
                quotesItem = itemView.findViewById(R.id.quotesItem);  
                quote = itemView.findViewById(R.id.quote);  
                authore = itemView.findViewById(R.id.authore);  
            }  
        }///////  
  
  
  
  
  
        @NonNull  
        @Override        public recycleAdapter.recyleViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType) {  
  
            LinearLayout quotesItem;  
            LayoutInflater inflater = getLayoutInflater();  
            View quoteView =inflater.inflate(R.layout.quotes_item, parent, false);  
  
            quotesItem = quoteView.findViewById(R.id.quotesItem);  
            quotesItem.setOnClickListener(new View.OnClickListener() {  
                @Override  
                public void onClick(View v) {  
                    Single_quotes.quoteTitles = "Love is blind, you can find a real love once in a life";  
                    Single_quotes.quoteAuthores = "Romeo";  
                    startActivity(new Intent(getActivity(), Single_quotes.class));  
                }  
            });  
            return new recyleViewHolder(quoteView);  
        }  
  
        @Override  
        public void onBindViewHolder(@NonNull recycleAdapter.recyleViewHolder holder, int position) {  
            holder.authore.setText(" - NHRepon " + position);  
        }  
  
        @Override  
        public int getItemCount() {  
            return 15;  
        }  
    }/////////////////////  
  
  
  
  
  
}
```


# Single
```xml
<?xml version="1.0" encoding="utf-8"?>  
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"  
    xmlns:app="http://schemas.android.com/apk/res-auto"  
    xmlns:tools="http://schemas.android.com/tools"  
    android:id="@+id/main"  
    android:layout_width="match_parent"  
    android:layout_height="match_parent"  
    tools:context=".Single_quotes"  
    android:orientation="vertical">  
  
    <RelativeLayout  
        android:layout_width="match_parent"  
        android:layout_height="match_parent"  
        >  
  
  
  
  
  
    <LinearLayout  
        android:layout_width="match_parent"  
        android:layout_height="match_parent"  
        android:layout_gravity="center"  
        android:background="@drawable/women_bg"  
        android:gravity="center"  
        android:orientation="vertical"  
        android:padding="25dp">  
  
        <TextView  
            android:id="@+id/quoteTitle"  
            android:layout_width="wrap_content"  
            android:layout_height="wrap_content"  
            android:layout_marginVertical="10dp"  
            android:background="@drawable/border_radius_shadow"  
            android:fontFamily="@font/comic"  
            android:paddingHorizontal="20dp"  
            android:paddingVertical="9dp"  
            android:text="@string/app_name"  
            android:textColor="@color/secondary"  
            android:textSize="48sp"  
  
            />  
  
        <TextView            android:id="@+id/quoteAuthore"  
            android:layout_width="wrap_content"  
            android:layout_height="wrap_content"  
            android:layout_gravity="end"  
            android:layout_marginRight="5dp"  
            android:background="@drawable/border_radius_shadow"  
            android:fontFamily="@font/comic"  
            android:paddingHorizontal="8dp"  
            android:paddingVertical="3dp"  
            android:text="@string/app_name"  
            android:textColor="@color/secondary"  
            android:textSize="14sp" />  
  
  
  
    </LinearLayout>  
  
  
        <LinearLayout            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:layout_alignParentBottom="true"  
            android:orientation="vertical"  
            android:gravity="end"  
            android:padding="10dp"  
            >  
            <com.google.android.material.floatingactionbutton.FloatingActionButton  
                android:layout_width="wrap_content"  
                android:layout_height="wrap_content"  
                android:layout_marginBottom="?attr/actionBarSize"  
                />  
  
        </LinearLayout>  
    </RelativeLayout>  
  
  
</LinearLayout>
```


```java
  
public class Single_quotes extends AppCompatActivity {  
  
    public static String quoteTitles = "av";  
    public static String quoteAuthores = "ad";  
    TextView quoteTitle, quoteAuthore;  
  
    @Override  
    protected void onCreate(Bundle savedInstanceState) {  
        super.onCreate(savedInstanceState);  
        EdgeToEdge.enable(this);  
        setContentView(R.layout.activity_single_quotes);  
  
        quoteTitle = findViewById(R.id.quoteTitle);  
        quoteAuthore = findViewById(R.id.quoteAuthore);  
  
        quoteTitle.setText(quoteTitles);  
        quoteAuthore.setText(" - "+quoteAuthores);  
  
    }  
}
```