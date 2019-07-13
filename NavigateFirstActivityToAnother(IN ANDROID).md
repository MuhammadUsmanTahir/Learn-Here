# Learn-Here Navigate First Activity To Another IN ANDROID
# MainActivity

package com.example.admin.myapplication;

import android.content.Intent;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);


        Button btnNext = (Button)findViewById(R.id.Next_Activity);

        btnNext.setOnClickListener(new View.OnClickListener()
        {
         @Override
         public void onClick(View v)
         {
             //Toast.makeText(MainActivity.this, "Working Toast", Toast.LENGTH_SHORT).show();
             // Intent is bultin class is used to navigate activity from 1 to another activity and many more functions by using this intent class

             Intent i =new Intent(getApplicationContext(),Main2Activity.class);
             // Sending values from this for second activity.
             i.putExtra("username1","Jahaz is on the way1");
             i.putExtra("username2","Jahaz is on the way2");
             i.putExtra("username3","Jahaz is on the way3");
             i.putExtra("username4","Jahaz is on the way4");

             // Now Launch second activity by using builtin method of AppComActivity classs by passing intent object
             startActivity(i);
         }
        });
    }
}

# Activity_Main
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.example.admin.myapplication.MainActivity">

    <Button
        android:id="@+id/Next_Activity"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Next activity"
        tools:layout_editor_absoluteX="16dp"
        tools:layout_editor_absoluteY="16dp" />
</android.support.constraint.ConstraintLayout>

# Main2Activity
package com.example.admin.myapplication;

import android.content.Intent;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;

public class Main2Activity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);

        Button btn = (Button) findViewById(R.id.BtnPrevoius);
        // Now Accessing value from prevoius activity

        Intent i = getIntent();
        //btn.setText(i.getStringExtra("username4"));
        String U1 =i.getStringExtra("username4");
        btn.setText(U1);
        Toast.makeText(getApplicationContext(),getIntent().getStringExtra("username2"),Toast.LENGTH_LONG).show();

        btn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent i=new Intent(getApplicationContext(),MainActivity.class);
                startActivity(i);
            }
        });
    }
}

# activity_main

<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.example.admin.myapplication.Main2Activity">

    <Button
        android:id="@+id/BtnPrevoius"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Prevoius"
        tools:layout_editor_absoluteX="37dp"
        tools:layout_editor_absoluteY="40dp" />
</android.support.constraint.ConstraintLayout>




