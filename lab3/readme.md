# Lab3
------
# picture

- [运行截图1][1]
- [运行截图2][2]
- [运行截图3][3]
- [layout截图4][4]
- [layout截图5][5]
- [操作视频][6]

------
# Code
------
* MainActivity.java
```java
package com.example.Toast;
import androidx.appcompat.app.AppCompatActivity;

import android.app.Activity;
import android.content.pm.ActivityInfo;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {
    static private int mCount = 0;
    private TextView mShowCount;
    private Button zeroButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        //setRequestedOrientation(ActivityInfo.SCREEN_ORIENTATION_PORTRAIT);//竖屏
        //setRequestedOrientation(ActivityInfo.SCREEN_ORIENTATION_LANDSCAPE);//横屏
        mShowCount = (TextView) findViewById(R.id.show_count);
        zeroButton = (Button) findViewById(R.id.button_zero);
        setNumber();
    }

    public void showToast(View view) {
        Toast toast = Toast.makeText(this, R.string.toast_message,
                Toast.LENGTH_SHORT);
        toast.show();
    }

    private void setNumber() {
        assert mShowCount != null;
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
        // 增加 1
        ++mCount;
        setNumber();
    }

    public void setZero(View view) {
        // 设置为 0
        mCount = 0;
        setNumber();
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

    <Button
        android:id="@+id/button_toast"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginTop="8dp"
        android:layout_marginEnd="8dp"
        android:background="@color/design_default_color_primary"
        android:text="@string/button_label_toast"
        android:textColor="@android:color/white"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        android:onClick="showToast" />

    <Button
        android:id="@+id/button_count"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginEnd="8dp"
        android:layout_marginBottom="8dp"
        android:background="@color/design_default_color_primary"
        android:onClick="countUp"
        android:text="@string/button_label_count"
        android:textColor="@android:color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toStartOf="@+id/button_zero"
        app:layout_constraintStart_toStartOf="parent" />

    <TextView
        android:id="@+id/show_count"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:layout_marginStart="8dp"
        android:layout_marginTop="8dp"
        android:layout_marginEnd="8dp"
        android:layout_marginBottom="8dp"
        android:background="@color/lightyellow"
        android:gravity="center"
        android:text="@string/count_initial_value"
        android:textAlignment="center"
        android:textColor="@color/design_default_color_primary"
        android:textSize="160sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toTopOf="@+id/button_zero"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/button_toast" />

    <Button
        android:id="@+id/button_zero"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginEnd="8dp"
        android:layout_marginBottom="8dp"
        android:background="@color/design_default_color_primary"
        android:onClick="setZero"
        android:text="@string/button_label_zero"
        android:textColor="@android:color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.495"
        app:layout_constraintStart_toEndOf="@+id/button_count" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
string.xml
```xml
<resources>
    <string name="app_name">Toast</string>
    <string name="button_label_toast">Toast</string>
    <string name="button_label_count">Count</string>
    <string name="button_label_zero">Zero</string>
    <string name="count_initial_value">0</string>
    <string name="toast_message">Hello Toast!</string>
</resources>
```

land\activity_main.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/button_toast"
        android:layout_width="264dp"
        android:layout_height="112dp"
        android:background="@color/design_default_color_primary"
        android:onClick="showToast"
        android:text="@string/button_label_toast"
        android:textColor="@android:color/white"
        android:textSize="60sp"
        tools:layout_editor_absoluteX="8dp"
        tools:layout_editor_absoluteY="93dp" />

    <Button
        android:id="@+id/button_count"
        android:layout_width="264dp"
        android:layout_height="112dp"
        android:background="@color/design_default_color_primary"
        android:onClick="countUp"
        android:text="@string/button_label_count"
        android:textColor="@android:color/white"
        app:layout_constraintBottom_toTopOf="@+id/button_zero"
        app:layout_constraintTop_toBottomOf="@+id/button_toast"
        tools:layout_editor_absoluteX="6dp"
        tools:textSize="60sp" />

    <TextView
        android:id="@+id/show_count"
        android:layout_width="981dp"
        android:layout_height="798dp"
        android:background="@color/lightyellow"
        android:gravity="center"
        android:text="@string/count_initial_value"
        android:textAlignment="center"
        android:textColor="@color/design_default_color_primary"
        android:textSize="240sp"
        android:textStyle="bold"
        tools:layout_editor_absoluteX="297dp"
        tools:layout_editor_absoluteY="1dp" />

    <Button
        android:id="@+id/button_zero"
        android:layout_width="264dp"
        android:layout_height="112dp"
        android:background="@color/design_default_color_primary"
        android:onClick="setZero"
        android:text="@string/button_label_zero"
        android:textColor="@android:color/white"
        tools:layout_editor_absoluteX="6dp"
        tools:layout_editor_absoluteY="527dp"
        tools:textSize="60sp" />

    <androidx.constraintlayout.widget.Guideline
        android:id="@+id/guideline"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        app:layout_constraintGuide_begin="266dp" />
</androidx.constraintlayout.widget.ConstraintLayout>

```


  [1]: https://github.com/lone-dreamer/IMD1813003/blob/master/lab3/1.png
  [2]: https://github.com/lone-dreamer/IMD1813003/blob/master/lab3/2.png
  [3]: https://github.com/lone-dreamer/IMD1813003/blob/master/lab3/3.png
  [4]: https://github.com/lone-dreamer/IMD1813003/blob/master/lab3/4.png
  [5]: https://github.com/lone-dreamer/IMD1813003/blob/master/lab3/5.png
  [6]: https://github.com/lone-dreamer/IMD1813003/blob/master/lab3/toast.mp4