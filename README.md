
# Ex.No:6 Design an android application Send SMS using Intent.


## AIM:

To create and design an android application Send SMS using Intent using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as smsintent and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Send SMS and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to create and design an android application Send SMS using Intent.
Developed by: POOJASRI L
Registeration Number : 212223220076
*/
```
## activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="20dp">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="SMS APPLICATION"
        android:textSize="24sp"
        android:textStyle="bold"
        android:textColor="#9C27B0"
        android:layout_marginBottom="30dp"/>

    <EditText
        android:id="@+id/editPhone"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Phone Number"
        android:inputType="phone"
        android:textColor="#000000"/>

    <EditText
        android:id="@+id/editMessage"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Message"
        android:inputType="textMultiLine"
        android:textColor="#000000"
        android:layout_marginTop="20dp"/>

    <Button
        android:id="@+id/btnSend"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Send SMS"
        android:layout_marginTop="30dp"/>

</LinearLayout>
```
## MainActivity.java
```
package com.example.smsapplication;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText editPhone, editMessage;
    Button btnSend;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editPhone = findViewById(R.id.editPhone);
        editMessage = findViewById(R.id.editMessage);
        btnSend = findViewById(R.id.btnSend);

        btnSend.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                String phone = editPhone.getText().toString();
                String message = editMessage.getText().toString();

                Intent intent = new Intent(Intent.ACTION_SENDTO);

                intent.setData(Uri.parse("smsto:" + phone));

                intent.putExtra("sms_body", message);

                startActivity(intent);
            }
        });
    }
}

```
## AndroidManifest.xml
```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android">

    <application
        android:allowBackup="true"
        android:label="@string/app_name"
        android:supportsRtl="true"
        android:theme="@style/Theme.SmsApplication">

        <activity
            android:name=".MainActivity"
            android:exported="true">

            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>

        </activity>

    </application>

</manifest>

```

## OUTPUT

<img width="1918" height="1078" alt="expt 3" src="https://github.com/user-attachments/assets/05bdce2b-e5d1-443c-8899-b82b240a4985" />

<img width="1917" height="1073" alt="ex 3 a" src="https://github.com/user-attachments/assets/05a42af7-4284-4d17-8fa7-3dd4935bfe13" />

<img width="1918" height="1078" alt="ex 3 b" src="https://github.com/user-attachments/assets/e76c873a-1f8a-4a99-a3dc-7aa1043ab6cf" />

<img width="1918" height="1078" alt="ex 3 c" src="https://github.com/user-attachments/assets/c2683db5-839e-4ebb-8aee-fd2252c4b1c1" />



## RESULT
Thus a Simple Android Application create and design an android application Send SMS using Intent using Android Studio is developed and executed successfully.
