## Glide
```java
Glide.with(this).load(quoteImage)  
        .placeholder(R.drawable.women_bg) // Add a placeholder image  
        .error(R.drawable.bgimage)  
        .into(singleQuoteImg);
```

## Picasso
```java
Picasso.get().load(quoteImage).into(new Target() {  
    @Override  
    public void onBitmapLoaded(Bitmap bitmap, Picasso.LoadedFrom from) {  
        singleQuoteImg.setImageDrawable(new BitmapDrawable(bitmap));  
        //singleQuoteImg.setBackgroundDrawable(new BitmapDrawable(bitmap));  
    }  
  
    @Override  
    public void onBitmapFailed(Exception e, Drawable errorDrawable) {  
        Toast.makeText(getApplicationContext(), "Error : loading wallpaper", Toast.LENGTH_SHORT).show();  
    }  
  
    @Override  
    public void onPrepareLoad(Drawable placeHolderDrawable) {  
  
    }});  
Picasso.get().load(quoteImage).into(singleQuoteImg);
```