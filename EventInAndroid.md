# Learn-Here Event in Android



# MainActivity.java
# Backend side
package com.example.admin.myapplication;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {



    TextView tv;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // GUI controls objects are type casting according their
        tv = (TextView)findViewById(R.id.tvlbl);
        Button btn = (Button)findViewById(R.id.btnshow);
            
            // Event on Click
            // Now At Set Event     // Inside brackets we use Event for Firing
            btn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                Toast.makeText(MainActivity.this, tv.getText().toString(), Toast.LENGTH_SHORT).show();

            }
        });

    }
}

# activity_main.xml 
# frontend sIde 
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.example.admin.myapplication.MainActivity">

    <TextView
        android:id="@+id/tvlbl"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/btnshow"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button"
        tools:layout_editor_absoluteX="65dp"
        tools:layout_editor_absoluteY="76dp" />

</android.support.constraint.ConstraintLayout>

# One More Powerful Example
# MainActivity.java
# Backend side

package com.example.admin.myapplication;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity
{

    Button btn;
    TextView lblMessage;
    EditText et;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // GUI controls objects are type casting according their
        btn = (Button) findViewById(R.id.btncheck);
        lblMessage = (TextView) findViewById(R.id.lblMsg);
        et = (EditText) findViewById(R.id.txtName);

        // Event on Click
        // Now At Set Event     // Inside brackets we use Event for Firing
        btn.setOnClickListener(new View.OnClickListener()
        {
            @Override
            public void onClick(View v)
            {
                String Username = et.getText().toString();
                switch (Username)
                {
                    case "Administrator":
                          lblMessage.setText("Super Account : "+Username);
                          break;
                    case "Admin":
                        lblMessage.setText("Account : "+Username);
                        break;
                    case "GUEST":
                        lblMessage.setText("Mehman ka Naam : "+Username);
                        break;
                    default:
                        lblMessage.setText("Invalid Account/Not Registered");
                }

            }
        });
    }
}

# activity_main.xml 
# frontend sIde 
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    android:orientation="vertical" >

    <TextView
        android:id="@+id/text"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/username" />

    <EditText
        android:id="@+id/txtName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName" />

    <Button
        android:id="@+id/btncheck"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/check_user" />

    <TextView
        android:id="@+id/lblMsg"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/message" />

    <!-- More GUI components go here  -->

</LinearLayout>

# MainActivity.java

package com.example.admin.myapplication;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.CheckBox;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;
import android.widget.ToggleButton;

public class MainActivity extends AppCompatActivity
{
    ToggleButton tb;
    TextView tv;
    Button btn;
    CheckBox chkbox;


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // GUI controls objects are type casting according their


        tb = (ToggleButton) findViewById(R.id.btnOnOff);
        tv = (TextView) findViewById(R.id.tvgui);
        tb.setOnClickListener(new View.OnClickListener()
        {
            @Override
            public void onClick(View v)
            {
                tv.setText(tb.getText().toString());
            }


        });

        chkbox = (CheckBox) findViewById(R.id.ichkremember);
        btn =(Button) findViewById(R.id.btnCheck);

        btn.setOnClickListener(new View.OnClickListener()
        {
            @Override
            public void onClick(View i)
            {
                if(chkbox.isChecked())
                {
                    Toast.makeText(getApplicationContext(),"Checked Now",Toast.LENGTH_LONG).show();
                }
                else
                {
                    Toast.makeText(getApplicationContext(),"Unchecked Now",Toast.LENGTH_LONG).show();
                }
            }

        });






    }


}

# main_activity.xml

<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    android:orientation="vertical" >

    <!-- More GUI components go here  -->

    <ToggleButton
        android:id="@+id/btnOnOff"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="ToggleButton" />

    <TextView
        android:id="@+id/tvgui"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="TextView" />

    <CheckBox
        android:id="@+id/ichkremember"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Remember Me" />

    <Button
        android:id="@+id/btnCheck"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Check" />
</LinearLayout>
