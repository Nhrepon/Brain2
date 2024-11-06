
# Image View
```xml
<ImageView  
    android:layout_width="wrap_content"  
    android:layout_height="300dp"  
    android:src="@drawable/neural"  
    android:scaleType="centerCrop"  
    />


```



# Recycler view
```java
package com.nhrepon.neuralquotes;  
  
import android.content.Intent;  
import android.os.Bundle;  
  
import androidx.annotation.NonNull;  
import androidx.fragment.app.Fragment;  
import androidx.recyclerview.widget.LinearLayoutManager;  
import androidx.recyclerview.widget.RecyclerView;  
  
import android.view.LayoutInflater;  
import android.view.View;  
import android.view.ViewGroup;  
import android.widget.LinearLayout;  
import android.widget.TextView;  
  
  
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