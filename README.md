# ImageGallery 
---------
<!--[![Build Status](https://api.travis-ci.org/ChristianLJ/MaterialEditText.svg)](https://travis-ci.org/ChristianLJ/MaterialEditText)-->
[![License](https://img.shields.io/badge/license-Apache%202-4EB1BA.svg?style=flat-square)](https://opensource.org/licenses/Apache2)

ImageGallery is an image gallery for Android. With this image gallery you can easly add a gallery to your app. 

The gallery accepts a `List<String>` or a `String[]` containing image URL's and uses Picasso to load them.

ImageGallery is licensed under the friendly [Apache2 licence].

### Documentation
Various documentation is available:

#### Default config:
```groovy
android {
    compileSdkVersion 25
    buildToolsVersion "25.1.0"
    defaultConfig {
        minSdkVersion 17
        targetSdkVersion 25
    }
}
```
##### Supported languages:
- All using a LanguageHelper. Defaults to english. See the example.

#### Screenshots:
<img src="https://raw.githubusercontent.com/ChristianLJ/ImageGallery/master/documentation/s1.png" width="290">
<img src="https://raw.githubusercontent.com/ChristianLJ/ImageGallery/master/documentation/s2.png" width="290">
### Example:
Add the view to your app:
```xml
<app.ltaps.imagegallery.ImageGallery
    android:id="@+id/imageGallery"
    android:layout_width="match_parent"
    android:layout_height="match_parent" />
```

Init and use the view from your app:
```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);

    ImageGallery imageGallery = (ImageGallery) findViewById(R.id.imageGallery);
    imageGallery
        .setImages(getImages())
        //.setImages(getImagesAsArray())
        .setLanguageHelper(new LanguageHelper(this)
            .setNoImagesAvailable("No images are available!")
            .setOutOf("out of"))
        .setOnLargeImageClickCallback(new OnClickCallback() {
            @Override
            public void OnClick(String currentImageUrl) {
                Toast.makeText(getApplicationContext(), "Clicked image", Toast.LENGTH_LONG).show();
            }
        })
        .start();
}
```


### Releases
[Release 0.7] is the current latest release. This release is considered a beta release.


**Gradle configuration:**

Add the following to your build.gradle:
```groovy
allprojects {
    repositories {
        maven { url "https://jitpack.io" }
    }
}

...

dependencies {
    ...
    compile 'com.github.ChristianLJ:ImageGallery:0.7'
    ...
}
```


### Support
Please use GitHub issues and Pull Requests for support.


### History
Issue tracking and active development is at GitHub.
