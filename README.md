# MultiStateView
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-MultiStateView-brightgreen.svg?style=flat)](http://android-arsenal.com/details/1/1726)
Android View that displays different content based on its state.<br>
Based off of [MeetMe/MultiStateView](https://github.com/MeetMe/Android-MultiStateView)

The four different states the view can be in are:
- Content
- Empty
- Error
- Loading

![screenshot](https://github.com/Kennyc1012/MultiStateView/blob/master/art/content.png)
![screenshot](https://github.com/Kennyc1012/MultiStateView/blob/master/art/loading.png)
![screenshot](https://github.com/Kennyc1012/MultiStateView/blob/master/art/empty.png)
![screenshot](https://github.com/Kennyc1012/MultiStateView/blob/master/art/error.png)


# Using MultiStateView
MultiStateView can be used the same as any other view by adding it as a layout file via XML
```xml
<com.kennyc.view.MultiStateView xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/multiStateView"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    app:msv_errorView="@layout/error_view"
    app:msv_emptyView="@layout/empty_view"
    app:msv_loadingView="@layout/loading_view"
    app:msv_viewState="loading">
    
      <ListView
        android:id="@+id/list"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:listitem="@android:layout/simple_list_item_1" />

</com.kennyc.view.MultiStateView>
```
The attributes to set for MultiStateView are
```xml
<attr name="msv_loadingView" format="reference" />
<attr name="msv_emptyView" format="reference" />
<attr name="msv_errorView" format="reference" />
<attr name="msv_viewState" format="enum">
<attr name="msv_animateViewChanges" format="boolean" />
```

msv_loadingView is the view to be used for the [LOADING ViewState](https://github.com/Kennyc1012/MultiStateView/blob/master/library/src/main/java/com/kennyc/view/MultiStateView.java#L34)<br>
msv_emptyView is the view to be used for the [EMPTY ViewSate](https://github.com/Kennyc1012/MultiStateView/blob/master/library/src/main/java/com/kennyc/view/MultiStateView.java#L32)<br>
msv_errorView is the view to be used for the [ERROR ViewState](https://github.com/Kennyc1012/MultiStateView/blob/master/library/src/main/java/com/kennyc/view/MultiStateView.java#L30)<br>
msv_viewState is the [ViewState](https://github.com/Kennyc1012/MultiStateView/blob/master/library/src/main/java/com/kennyc/view/MultiStateView.java#L38) for the MultiStateView<br>
The [CONTENT ViewState](https://github.com/Kennyc1012/MultiStateView/blob/master/library/src/main/java/com/kennyc/view/MultiStateView.java#L28) is determined by whatever is inside of the tags via XML. <b>NOTE**</b> a Content view must be set for the view to function, this is by design. 

To switch the state of MultiStateView, simply call
```java 
public void setViewState(@ViewState int state)
```

You can also get the View for the accompanying ViewState by calling
```java
public View getView(@ViewState int state)
```

#Including in your project
To include MultiStateView in your project, make the following changes to your build.gradle file

## Add repository 
```groovy
repositories {
    maven { url 'https://jitpack.io' }
}
```
## Add dependency
```groovy
dependencies {
    compile 'com.github.Kennyc1012:MultiStateView:1.3.0'
}
```

#Contribution
Pull requests are welcomed and encouraged. If you experience any bugs, please file an [issue](https://github.com/Kennyc1012/MultiStateView/issues)

License
=======

    Copyright 2015 Kenny Campagna

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
