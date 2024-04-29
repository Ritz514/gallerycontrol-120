# Ex.No:8 To create a gallery control using android studio to display images or photos.


## AIM:

To create a gallery control using android studio to display images or photos.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:
Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as “gallerycontrol″ and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Get images details and Add images in MainActivity file.

Step 7: Save and run the application.



## PROGRAM:
/*
Program to print the text “GalleryControl”.
Developed by: Reethika
Registeration Number : 212221040120
*/

activity_main.xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="36dp"
        app:layout_constraintBottom_toTopOf="@+id/languagesGallery"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.466"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:srcCompat="@tools:sample/avatars" />

    <Gallery
        android:id="@+id/languagesGallery"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:animationDuration="2000"
        android:padding="10dp"
        android:spacing="5dp"
        android:unselectedAlpha="50"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"></Gallery>

</androidx.constraintlayout.widget.ConstraintLayout>

MainActivity.java
package com.example.gallery_control;


import android.os.Bundle;
import android.widget.Gallery;
import android.widget.ImageView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    Gallery simpleGallery;
    CustomizedGalleryAdapter customGalleryAdapter;
    ImageView selectedImageView;

    int[] images = {
            R.drawable.india,
            R.drawable.china,
            R.drawable.australia,
            R.drawable.america
    };

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        simpleGallery = (Gallery) findViewById(R.id.languagesGallery);

        selectedImageView = (ImageView) findViewById(R.id.imageView);

        customGalleryAdapter = new CustomizedGalleryAdapter(getApplicationContext(), images);

        simpleGallery.setAdapter(customGalleryAdapter);

        simpleGallery.setOnItemClickListener((parent, view, position, id) -> {
            selectedImageView.setImageResource(images[position]);
        });
    }
}
CustomizedGalleryAdapter.java
package com.example.gallery_control;
import android.content.Context;
import android.view.View;
import android.view.ViewGroup;
import android.widget.BaseAdapter;
import android.widget.Gallery;
import android.widget.ImageView;

public class CustomizedGalleryAdapter extends BaseAdapter {

    private final Context context;
    private final int[] images;

    public CustomizedGalleryAdapter(Context c, int[] images) {
        context = c;
        this.images = images;
    }

    public int getCount() {
        return images.length;
    }

    public Object getItem(int position) {
        return position;
    }

    public long getItemId(int position) {
        return position;
    }

    public View getView(int position, View convertView, ViewGroup parent) {

        ImageView imageView = new ImageView(context);

        imageView.setImageResource(images[position]);

        imageView.setLayoutParams(new Gallery.LayoutParams(200, 200));
        return imageView;
    }
}



## OUTPUT

![323451122-11d41c52-0428-4674-![323452021-dc8ceb36-dc31-471a-ae32-866f58f21ef8](https://github.com/Ritz514/gallerycontrol-120/assets/142646304/d8834826-aa7a-484a-bb50-60127d55d8ab)
b101-0e52443e3f86](https://github.com/Ritz514/gallerycontrol-120/assets/142646304/69f1b2bc-09d3-4383-b3a8-8c473b87f3ab)

![323451592-7e47e429-8b5d-4871-adb5-3b8ec559b153](https://github.com/Ritz514/gallerycontrol-120/assets/142646304/77111cc0-1419-40d5-8602-5229ef4c3d5d)

![323451221-9f6e961e-cf49-49ad-9b6f-dba0550cea4e](https://github.com/Ritz514/gallerycontrol-120/assets/142646304/53204783-a966-40de-9355-58716914f523)



## RESULT
Thus a Simple Android Application to create a gallery control using android studio to display images or photos is developed and executed successfully.

