# Lab4
------
## picture

- [运行截图1][1]
- [运行截图2][2]
- [运行截图3][3]
- [运行截图4][4]
- [操作视频][5]

------
## Code
------
* MainActivity.java
```java
package com.example.toast;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.util.Log;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    // 声明日志输出的 tag
    private static final String LOG_TAG =
            MainActivity.class.getSimpleName();

    public static final String COUNT_MESSAGE = "com.example.toast.count.message";

    static private int mCount = 0;
    private TextView mShowCount;
    private Button zeroButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        mShowCount = (TextView) findViewById(R.id.show_count);
        zeroButton = (Button) findViewById(R.id.button_zero);
        setNumber();
    }

    public void showToast(View view) {
        Log.d(LOG_TAG, "showToast clicked!");
        // homework1
//        Toast toast = Toast.makeText(this, R.string.toast_message,
//                Toast.LENGTH_SHORT);
//        toast.show();

        // homework2
        Intent intent = new Intent(this, SayHelloActivity.class);
        String countMessage = mShowCount.getText().toString();
        intent.putExtra(COUNT_MESSAGE, countMessage);
        startActivity(intent);
    }

    private void setNumber() {
        // 通过数值来设置按钮和显示数字的颜色
        assert mShowCount != null;  // 保证 mShowCount 不会为 null
        mShowCount.setText(String.valueOf(mCount));
        if (mCount == 0) zeroButton.setBackgroundColor(getColor(R.color.gray));
        else zeroButton.setBackgroundColor(getColor(R.color.design_default_color_primary));
        if (mCount % 2 == 0) {
            mShowCount.setBackgroundColor(getColor(R.color.lightyellow));
            mShowCount.setTextColor(getColor(R.color.design_default_color_primary));
        }
        else {
            mShowCount.setBackgroundColor(getColor(R.color.lightpurple));
            mShowCount.setTextColor(getColor(R.color.white));
        }
    }

    public void countUp(View view) {
        Log.d(LOG_TAG, "countUp clicked!");
        // 增加 1
        ++mCount;
        setNumber();
    }

    public void setZero(View view) {
        Log.d(LOG_TAG, "setZero clicked!");
        // 设置为 0
        mCount = 0;
        setNumber();
    }
}
```
SayHelloActivity.java
```java
package com.example.toast;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.widget.TextView;

public class SayHelloActivity extends AppCompatActivity {

    private TextView mShowCountTextView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_say_hello);
        Intent intent = getIntent();
        mShowCountTextView = findViewById(R.id.textView_show_count);
        String countMessage = intent.getStringExtra(MainActivity.COUNT_MESSAGE);
        mShowCountTextView.setText(countMessage);
    }
}
```

activity_main.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">
    <TextView
        android:id="@+id/text_header_reply"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginLeft="8dp"
        android:layout_marginTop="16dp"
        android:text="@string/text_header_reply"
        android:textAppearance="@style/TextAppearance.AppCompat.Medium"
        android:textStyle="bold"
        android:visibility="invisible"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/text_message_reply"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginLeft="8dp"
        android:layout_marginTop="8dp"
        android:visibility="invisible"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/text_header_reply" />
    <Button
        android:id="@+id/button_main"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="16dp"
        android:layout_marginRight="16dp"
        android:text="Send"
        android:onClick="launchSecondActivity"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintRight_toRightOf="parent" />

    <EditText
        android:id="@+id/editText_main"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginBottom="16dp"
        android:layout_marginEnd="8dp"
        android:layout_marginStart="8dp"
        android:ems="10"
        android:hint="Enter Your Message Here"
        android:inputType="textLongMessage"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toStartOf="@+id/button_main"
        app:layout_constraintStart_toStartOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>




```



  [1]: https://github.com/lone-dreamer/IMD1813003/blob/master/lab4/homework/1.png
  [2]: https://github.com/lone-dreamer/IMD1813003/blob/master/lab4/homework/2.png
  [3]: https://github.com/lone-dreamer/IMD1813003/blob/master/lab4/homework/3.png
  [4]: https://github.com/lone-dreamer/IMD1813003/blob/master/lab4/homework/4.png
  [5]: https://github.com/lone-dreamer/IMD1813003/blob/master/lab4/homework/homework.mp4