
# Ex.No:07 Design an application that draws basic graphical primitives on the screen.


## AIM:

To create and design an android application that draws basic graphical primitives on the screen using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as “graphical″ and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Draw basic object details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to create and design an android application that draws basic graphical primitives on the screen.
Developed by: GANESH PRABHU J
Registeration Number : 212223220023
*/
```
### activity_main.xml
```java
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/imageView1"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

### MainActivity.java
```java
package com.example.graphics;

import androidx.appcompat.app.AppCompatActivity;
import android.graphics.Bitmap;
import android.graphics.Canvas;
import android.graphics.Color;
import android.graphics.LinearGradient;
import android.graphics.Paint;
import android.graphics.Shader;
import android.graphics.drawable.BitmapDrawable;
import android.os.Bundle;
import android.widget.ImageView;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Bitmap bg = Bitmap.createBitmap(720, 1280, Bitmap.Config.ARGB_8888);

        ImageView imageView = findViewById(R.id.imageView1);
        imageView.setBackground(new BitmapDrawable(getResources(), bg));

        Canvas canvas = new Canvas(bg);
        canvas.drawColor(Color.LTGRAY);

        Paint paint = new Paint();
        paint.setTextSize(50);

        paint.setColor(Color.BLACK);
        paint.setShader(null);
        canvas.drawText("Circle", 120, 150, paint);

        paint.setShader(new LinearGradient(
                50, 350, 350, 350,
                Color.BLUE, Color.CYAN,
                Shader.TileMode.MIRROR
        ));
        canvas.drawCircle(200, 350, 150, paint);

        paint.setShader(null);
        paint.setColor(Color.BLACK);
        canvas.drawText("Rectangle", 420, 150, paint);

        paint.setShader(new LinearGradient(
                400, 200, 650, 700,
                Color.RED, Color.YELLOW,
                Shader.TileMode.MIRROR
        ));
        canvas.drawRect(400, 200, 650, 700, paint);

        paint.setShader(null);
        paint.setColor(Color.BLACK);
        canvas.drawText("Square", 120, 800, paint);

        paint.setShader(new LinearGradient(
                50, 850, 350, 1150,
                Color.MAGENTA, Color.rgb(255, 105, 180),
                Shader.TileMode.MIRROR
        ));
        canvas.drawRect(50, 850, 350, 1150, paint);

        paint.setShader(null);
        paint.setColor(Color.BLACK);
        paint.setStrokeWidth(0);
        canvas.drawText("Line", 500, 800, paint);

        paint.setStrokeWidth(10);
        paint.setShader(new LinearGradient(
                520, 850, 520, 1150,
                Color.GREEN, Color.BLACK,
                Shader.TileMode.MIRROR
        ));
        canvas.drawLine(520, 850, 520, 1150, paint);
    }
}
```
## OUTPUT
<img width="1920" height="1080" alt="Screenshot (1025)" src="https://github.com/user-attachments/assets/48dd3a51-2a57-407a-b317-3072c1e095a7" />


## RESULT
Thus a Simple Android Application to create and design an android application that draws basic graphical primitives on the screen using Android Studio is developed and executed successfully.
