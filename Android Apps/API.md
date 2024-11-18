
```java
// 
// after voley post request try and error block - stringRequest
{@Nullable
@override
protected Map<String, String> getParams() throws AuthFailureError{
Map myMap = new HashMap<String, String>();
myMap.put("password", "1234");
myMap.put("email", "nurhossainrepon7248@gmail.com");

return myMap;
}}


jsonObjectReques(); // return json object data
jsonArrayRequest(); // return json array data







```

## Encryption

using base64
```java
private void encryptData() throws Exception {
String plainText = "I love you!";
byte[] text = plainText.getBytee("utf-8");
String encodeData = Base64.encodeToString(text, Base64.default);
textview.setText(encodeData);
}
```


Data encryption using crypto
```java
private void encryptData() throws Exception {
String plainText = "I love you!";
String password = "abcd1234abcd1234"; // 16 bite required

byte[] pass = password.getBytee("utf-8");
SecretKeySpec secretKeySpec = new SecretKeySepc(pass, "AES");
Cipher cipher = Cipher.getInstance("AES");
cipher.init(Cipher.ENCRYPT_MODE, secretKeySpec);
byte[] securedBytes = cipher.doFinal(plainText);


String encodeData = Base64.encodeToString(securedBytes, Base64.default);
textview.setText(encodeData);
}


```


Data decryption using crypto
```java
private void decryptData() throws Exception {
String encodedString = "asdfaasdfasdfads";
byte[] decodedBytes = Base64.decode(encodedString, Base64.DEFAULT);

String password = "abcd1234abcd1234"; // 16 bite required
byte[] pass = password.getBytee("utf-8");

SecretKeySpec secretKeySpec = new SecretKeySepc(pass, "AES");
Cipher cipher = Cipher.getInstance("AES");
cipher.init(Cipher.DECRYPT_MODE, secretKeySpec);
byte[] decryptBytes = cipher.doFinal(decodedBytes);


String plaiText = new String(decryptBytes, "utf-8");
textview.setText(plaiText);
}


```



Data decryption using crypto php
```php
$encodedData = "jalkafsdhflakdfaldsjf";
$decode = base64_decode($encodedData);
$decryptedData = openssl_decrypt($decode, 'AES-128-ECB', 'password', OPENSSL_RAW-DATA);
echo $decryptedData;

```



Data encryption using crypto php
```php
$text = "Nur Hossain";

$encryptedData = openssl_encrypt($text, 'AES-128-ECB', 'password', OPENSSL_RAW-DATA);
$encode = base64_encode(encryptedData);
echo $encode;

```