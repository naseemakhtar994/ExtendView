# Include View

Have you ever wanted a more sophisticated `<include />` on your XML files?

You don't need to create a custom `ViewGroup` anymore!

## Example

`viewgroup_container.xml`
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="wrap_content">

    <!-- A top border -->
    <View
        android:layout_width="match_parent"
        android:layout_height="1px"
        android:background="#ccc" />

    <!-- Our container that will hold our content -->
    <FrameLayout android:id="@+id/container"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="#fefefe">

    </FrameLayout>

    <!-- A bottom border -->
    <View
        android:layout_width="match_parent"
        android:layout_height="1px"
        android:background="#ccc" />

    <!-- A shadow -->
    <View android:layout_width="match_parent"
        android:layout_height="2dp"
        android:background="@drawable/tab_shadow"/>

</LinearLayout>
```

And finally, inside our layout we can use the container:

`fragment_information.xml`
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout android:id="@+id/majorLayout"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical">

    <com.mauriciogiordano.includeview.IncludeView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="8dp"
        android:layout_marginBottom="8dp"
        inevent:viewGroupLayout="@layout/viewgroup_container"
        inevent:containerId="@id/container">
    
        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Hello World" />
    
    </com.mauriciogiordano.includeview.IncludeView>
    
</LinearLayout>
```