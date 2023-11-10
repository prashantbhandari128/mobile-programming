<div align="center">

[**_``Go Back``_**](../README.md)

</div>

##  How fragment can be added to an activity?

``Fragment`` is a modular section of an activity's user interface and behavior. ``Fragments`` are often used to build flexible and reusable UI components within an activity. To add a fragment to an activity, you generally need to follow these steps:

- **``Step 1``** : Create a ``Fragment`` Class 

    **MyFragment.java**

    ```Java
    import android.os.Bundle;
    import android.view.LayoutInflater;
    import android.view.View;
    import android.view.ViewGroup;
    import androidx.fragment.app.Fragment;

    public class MyFragment extends Fragment {
        @Override
        public View onCreateView(LayoutInflater inflater, ViewGroup container, Bundle savedInstanceState) {
            return inflater.inflate(R.layout.fragment_layout, container, false);
        }
    }
    ```

- **``Step 2``** : Design the Fragment UI 

    **fragment_layout.xml**
    
    ```Xml
    <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical">
        <!-- Add your UI components here -->
    </LinearLayout>
    ```

- **``Step 3``** : Add the ``Fragment`` to the Activity Layout 
    
    **activity_main.xml** 

    ```Xml
    <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
        android:layout_width="match_parent"
        android:layout_height="match_parent">

        <!-- Other activity UI components -->

        <fragment
            android:id="@+id/myFragment"
            android:name="com.example.app.MyFragment"
            android:layout_width="match_parent"
            android:layout_height="wrap_content" />

    </RelativeLayout>
    ```

- **``Step 4``** : Manage Fragment Transactions 

    **MainActivity.java**

    ```Java
    import android.os.Bundle;
    import androidx.appcompat.app.AppCompatActivity;
    import androidx.fragment.app.FragmentManager;
    import androidx.fragment.app.FragmentTransaction;

    public class MainActivity extends AppCompatActivity {
        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);

            FragmentManager fragmentManager = getSupportFragmentManager();
            FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
            fragmentTransaction.replace(R.id.myFragment, new MyFragment());
            fragmentTransaction.commit();
        }
    }
    ```

## Develop an Android application to display 8 programming languages in ListView.

**activity_main.xml**

```Xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ListView
        android:id="@+id/languagesListView"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />
</RelativeLayout>

```

**list_item_layout.xml**

```Xml
<?xml version="1.0" encoding="utf-8"?>
<TextView xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@android:id/text1"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:padding="16dp"
    android:textAppearance="?android:attr/textAppearanceListItemSmall"
    android:textColor="#000000" />
```
**MainActivity.java**

```Java
import android.os.Bundle;
import android.widget.ArrayAdapter;
import android.widget.ListView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private String[] programmingLanguages = {
        "Java",
        "Python", 
        "C++",
        "JavaScript",
        "Swift",
        "Ruby", 
        "Kotlin", 
        "PHP"
    };

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        ListView listView = findViewById(R.id.languagesListView);
        ArrayAdapter<String> adapter = new ArrayAdapter<>(
            this,
            android.R.layout.simple_list_item_1,
            android.R.id.text1,
            programmingLanguages
        );
        listView.setAdapter(adapter);
    }
}

```

## Develop an Android application to display alert dialog box.

**activity_main.xml**

```Xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/showDialogButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Show Dialog" />

</LinearLayout>
```

**MainActivity.java**

```Java
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import androidx.appcompat.app.AlertDialog;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button showDialogButton = findViewById(R.id.showDialogButton);
        showDialogButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                showAlertDialog();
            }
        });
    }

    private void showAlertDialog() {
        AlertDialog.Builder builder = new AlertDialog.Builder(this);
        builder.setTitle("Alert Dialog")
            .setMessage("This is an example of an AlertDialog.")
            .setPositiveButton("OK", null)
            .show();
    }
}
```