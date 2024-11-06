




## Value passing
To go one activity to another activity with value.
```java
activity1:
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


activity2 create:
public static String quoteTitles = "av";  
public static String quoteAuthores = "ad";
```