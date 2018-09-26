# Multi-ColorPicker
[![API](https://img.shields.io/badge/API-15%2B-brightgreen.svg?style=flat)](https://android-arsenal.com/api?level=15)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) <br>
You can get colors from your gallery pictures or custom images just using touch with multi-selectors.

![gif0](https://user-images.githubusercontent.com/24237865/32027700-71c27e7a-ba25-11e7-80ab-37abe1a3f4b1.gif)

## Examples
![gif1](https://user-images.githubusercontent.com/24237865/32027699-7196b664-ba25-11e7-845c-31e8fede6f63.gif)
![example2-2](https://github.com/skydoves/Multi-ColorPicker/blob/master/screenshot/example2-2.jpg)

## Including in your project
#### build.gradle
```gradle
repositories {
    mavenCentral() // or jcenter() works as well
}

dependencies {
    implementation "com.github.skydoves:multicolorpicker:1.0.8"
}
```

#### or Maven
```xml
<dependency>
  <groupId>com.github.skydoves</groupId>
  <artifactId>multicolorpicker</artifactId>
  <version>1.0.8</version>
</dependency>
```

## How to use
You can use like using just ImageView and you can get colors from any images.

#### Add XML Namespace
First add below XML Namespace inside your XML layout file.

```gradle
xmlns:app="http://schemas.android.com/apk/res-auto"
```

#### ColorPickerView in layout
```gradle
<com.skydoves.multicolorpicker.MultiColorPickerView
        android:id="@+id/multiColorPickerView"
        android:layout_width="300dp"
        android:layout_height="300dp"
        app:palette="@drawable/palette"/>
```

#### Attribute in xml
```gradle
app:palette="@drawable/palette" // set palette image
```

#### get Colors from Listener
```java
multiColorPickerView.addSelector(selectorDrawable, new ColorListener() {
            @Override
            public void onColorSelected(ColorEnvelope envelope) {
                int color = envelope.getColor();
                int[] rgb = envelope.getRgb();
                String htmlCode = envelope.getHtmlCode();

                // TODO
            }
        });
```

#### MultiColorPickerView Methods
Methods | Return | Description
--- | --- | ---
addSelector(Drawable drawable, ColorListener listener) | Selector | adds a Selector and returning it
setPaletteDrawable(Drawable drawable) | void | changes palette's drawable
getMixedColor(Float ratio(0~1)) | void | returns mixed color from selectors seleted color
setSelectedAlpha(Float ratio(0~1) | void | sets active selector's alpha
getSelectorsSize() | int | returns selectors size
setFlagView(FlagView flagView) | void | sets a FlagView on colorpicker
setFlagMode(FlagMode flagmode) | void | sets FlagMode(Always, Last, None)
setFlagFlipable(boolean flipable) | void | sets flag's flip-able when flag go over top boundary

#### Selector Methods
Methods | Return | Description
--- | --- | ---
getX() | int | returns selector's X axis
getY() | int | returns selector's Y axis
getColor() | int | returns the selector's selected color
getColorHtml() | String | returns the selector's selected color html code
getColorRGB() | int[3] | returns the selector's selected color rgb array
onMove(int x, int y) | void | moves the selector's point
onMoveCenter() | void | moves the selector's point to center
onSelect() | void | selects point at selector's position (used with onMove())
onSelect(int x, int y) | void | moves and selects point

# License
```xml
Copyright 2017 skydoves

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

