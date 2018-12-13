![libdenx](https://user-images.githubusercontent.com/15522554/40986568-37d32b00-68ef-11e8-809a-d5497bb1b430.png)

Android base structure project. With this library you can write less code and develop faster.

### First use BaseActivity

BaseActivity include **onViewReady** and **getLayoutResourceId** functions. 

**onViewReady** works like onCreate. You can write your code here and you can use instead of onCreate.
**getLayoutResourceId** is used to link the class with the layout like setContentView. Actually BaseActivity uses setContentView in background.

You can use with **ButterKnife**.
```java
public class MainActivity extends BaseActivity {
    @Override
    protected void onViewReady(Bundle savedInstanceState, Intent intent) {
        super.onViewReady(savedInstanceState, intent);
    }

    @Override
    protected int getLayoutResourceId() {
        return R.layout.activity_main;
    }
}
```
#### You can add back button:
```java
addBackButton();
```
#### Volley Object Request:
```java
getJsonObject("Your Url", YourModel.class, result -> {
     //result is your response model. You can use here.       
});
 ```
#### Volley Array Request:
```java
getJsonArray("Your Url", result -> {
    // result is your response array. You can use here.
 });
 ```
 #### Check Internet Connection:
 ```java
  isNetworkConnected();
 ```
#### Show Toast Message:
```java
showMessage(int Message);
//or
showMessage(String Message);
 ```
# How to use?

This is not use alone project. You must use it like **submodule**.

```git
git submodule add https://github.com/denzcoskun/libdenx.git
```
Add libdenx to **Setting.gradle** file
```gradle
include ':app', ':libdenx'
```
Implement libdenx to **Build.gradle** file
```gradle
implementation project(path: ':libdenx')
```
#### Libraries used:
```gradle
implementation 'com.google.code.gson:gson:2.8.5'
implementation 'com.jakewharton:butterknife:8.8.1'
annotationProcessor 'com.jakewharton:butterknife-compiler:8.8.1'
implementation 'com.android.volley:volley:1.1.1'
implementation 'com.fasterxml.jackson.core:jackson-databind:2.9.7'
implementation 'com.fasterxml.jackson.core:jackson-core:2.9.7'
implementation 'com.fasterxml.jackson.core:jackson-annotations:2.9.6'
```
# License
Copyright 2018 Deniz Coşkun

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
