Convert image to byte string
```java
BitmapDrawable bitmapDrawable = imageView.getDrawable();
Bitmap bitmap = bitmapDrawable.getBitmap();

ByteArrayOutputStream outputStream = new ByteArrayOutputStream();
bitmap.compress(Bitmap.compressFormat.jpeg, 50, outputStream);

byte[] imageBytes = outputStream.toByteArray();
String image64 = Base64.encodeToString(imageBytes, Base64.DEFAULT);

textView.setText(image64);



```

Decode using php
```php
header('content-type':image/jpg);

$image64 = 'decoded data';

$decodedData = base64_decode($image64);

echo $decodedData;
```


Store image using php
```php
$image64 = $_POST('image');
$decodedImage = base64_decode($image64);
$fileName = time().'-'.rand(1000, 100000).'.jpg';
$filePath = 'uploads/'.$fileName;
if(file_put_contents($filePath, $decodedImage)){
echo 'file upload success';
}else{
echo 'failed';
}
```




Select image from gallery
```java
imageView.setOnClickListener(new View.OnClickListener() {  
    @Override  
    public void onClick(View v) {  
        Intent intent = new Intent(Intent.ACTION_PICK);  
        intent.setType("image/*");  
        galleryLuncher.lunch(intent);  
    }  
});




ActivityResultLauncher galleryLuncher =  
        registerForActivityResult(new ActivityResultContracts.StartActivityForResult(),  
                new ActivityResultCallback<ActivityResult>() {  
    @Override  
    public void onActivityResult(ActivityResult result) {  
        if(result.getResultCode() == Activity.RESULT_OK){  
            Intent intent = result.getData();  
            Uri uri = intent.getData();  
  
            try {  
                Bitmap bitmap = MediaStore.Images.Media.getBitmap(getContentResolver(), uri);  
                imageView.setImageBitmap(bitmap);  
                  
            } catch (IOException e) {  
                throw new RuntimeException(e);  
            }  
  
  
  
        }  
    }  
});


```

Check camera permission
```java
 private boolean checkCameraPermission(){  
    boolean hasPermission=false;  
    if(ContextCompat.checkSelfPermission(this, Manifest.permission.CAMERA ) == PackageManager.PERMISSION_GRANTED){  
        hasPermission = true;  
    }else {  
        hasPermission = false;  
        String[] permission = {Manifest.permission.CAMERA};  
        ActivityCompat.requestPermissions(this, permission, 101);  
    }  
  
    return hasPermission;  
}
```



Select image from Camera
```java
imageView.setOnClickListener(new View.OnClickListener() {  
    @Override  
    public void onClick(View v) {  
        if (checkCameraPermission()){  
    Intent intent = new Intent(MediaStore.ACTION_IMAGE_CAPTURE);  
    cameraLuncher.lunch(intent);  
}  
    }  
});




ActivityResultLauncher cameraLuncher =  
        registerForActivityResult(new ActivityResultContracts.StartActivityForResult(),  
                new ActivityResultCallback<ActivityResult>() {  
    @Override  
    public void onActivityResult(ActivityResult result) {  
        if(result.getResultCode() == Activity.RESULT_OK){  
            Intent intent = result.getData();  
            Bundle bundle = intent.getExtras();
            Bitmap bitmap = (Bitmap)bundle.get("data");
            imageView.setImageBitmap(bitmap);
        }  
    }  
});


```