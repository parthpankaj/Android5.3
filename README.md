# Android5.3
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/activity_main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingBottom="@dimen/activity_vertical_margin"
    android:paddingLeft="@dimen/activity_horizontal_margin"
    android:paddingRight="@dimen/activity_horizontal_margin"
    android:paddingTop="@dimen/activity_vertical_margin"
    tools:context="com.example.pankaj.menu53.MainActivity">

    <TextView
        android:text="Rahul"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentTop="true"
        android:layout_marginTop="13dp"
        android:id="@+id/textView" />

    <TextView
        android:text="1213456789"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/textView"
        android:layout_alignParentStart="true"
        android:layout_marginStart="13dp"
        android:layout_marginTop="25dp"
        android:id="@+id/textView4" />

    <TextView
        android:text="pankaj"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/textView4"
        android:layout_alignStart="@+id/textView4"
        android:layout_marginTop="22dp"
        android:id="@+id/textView5" />

    <TextView
        android:text="123456789"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/textView5"
        android:layout_alignStart="@+id/textView5"
        android:layout_marginTop="36dp"
        android:id="@+id/textView6" />

    <TextView
        android:text="kamal"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/textView6"
        android:layout_alignEnd="@+id/textView6"
        android:layout_marginTop="25dp"
        android:id="@+id/textView7" />

    <TextView
        android:text="5467894231"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerVertical="true"
        android:layout_alignStart="@+id/textView6"
        android:id="@+id/textView8" />

    <Button
        android:text="Task"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/textView8"
        android:layout_marginTop="28dp" />

</RelativeLayout>
----------
package com.example.pankaj.menu53;

import android.app.Activity;
import android.os.Bundle;
import android.view.ContextMenu;
import android.view.MenuItem;
import android.view.View;
import android.view.ContextMenu.ContextMenuInfo;
import android.widget.Button;
import android.widget.Toast;

public class MainActivity extends Activity {
    /** Called when the activity is first created. */
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button btn = (Button) findViewById(R.id.btn);
        registerForContextMenu(btn);
    }
    @Override
    public void onCreateContextMenu(ContextMenu menu, View v,
                                    ContextMenuInfo menuInfo) {
        super.onCreateContextMenu(menu, v, menuInfo);
        menu.setHeaderTitle("Context Menu");
        menu.add(0, v.getId(), 0, "Call");
        menu.add(0, v.getId(), 0, "SMS");
    }
    @Override
    public boolean onContextItemSelected(MenuItem item) {
        if (item.getTitle() == "Call") {
            Toast.makeText(this, "Action 1 invoked", Toast.LENGTH_SHORT).show();
        } else if (item.getTitle() == "SMS") {
            Toast.makeText(this, "Action 2 invoked", Toast.LENGTH_SHORT).show();
        }
            return false;
    }

}
