<div align="center">

[**_``Go Back``_**](../README.md)

# Designing the User Interface

</div>

## Android Layout and Types (Linear, Relative, Table, Absaolute, Constraint)
-----------------------------------------------------------------------------
A ``Layout`` defines the structure for a user interface in your app, such as in an activity. All elements in the layout are built using a hierarchy of ``View`` and ``ViewGroup`` objects. 

Android Layout is used to define the user interface that holds the UI controls or widgets that will appear on the screen of an android application or activity screen. Generally, every application is a combination of ``View`` and ``ViewGroup``. As we know, an android application contains a large number of activities and we can say each activity is one page of the application. So, each activity contains multiple user interface components and those components are the instances of the ``View`` and ``ViewGroup``. All the elements in a layout are built using a hierarchy of ``View`` and ``ViewGroup`` objects.

- **``View``** : A ``View`` is defined as the user interface which is used to create interactive UI components such as ``TextView``, ``ImageView``, ``EditText``, ``RadioButton``, etc., and is responsible for event handling and drawing. They are Generally Called ``Widgets``.
s
- **``ViewGroup``** : A ``ViewGroup`` act as a base class for layouts and layouts parameters that hold other ``Views`` or ``ViewGroups`` and to define the layout properties. They are Generally Called ``layouts``.

On the ``Android`` platform, you define an Activity's UI using a hierarchy of ``View`` and ``ViewGroup`` nodes, as shown in the diagram below. 

<div align="center">

!["Android View Hierarchy"](img/android-view-hierarchy.ppm)

</div>

The Android framework will allow us to use UI elements or widgets in two ways:  

- Use UI elements in the ``XML`` file.
- Create ``View`` and ``ViewGroup`` objects (and manipulate their properties) programmatically in ``Java``.

### **Types of Android Layout:**

#### LinearLayout:
``LinearLayout`` arranges its child views either horizontally or vertically in a single line. You can specify the orientation using the android:orientation attribute in XML It's a simple and efficient way to create linear arrangements.

**Attributes:**

- **``android:orientation``**: This attribute specifies the orientation of the linear layout, which can be either **horizontal** or **vertical**.
- **``android:layout_weight``**: This attribute allows you to distribute space among child views within the linear layout. Views with higher weights receive more space.
- **``android:gravity``**: This attribute specifies the gravity or alignment of child views within the linear layout.

#### RelativeLayout:
``RelativeLayout`` allows you to position child views relative to each other or to the parent container. It's highly flexible and useful for creating complex layouts. Views can be positioned above, below, to the left, or to the right of other views.

**Attributes:**

- **``android:layout_alignParentTop``**, **``android:layout_alignParentBottom``**, **``android:layout_alignParentLeft``**, **``android:layout_alignParentRight``**: These attributes allow you to position a child view relative to its parent's edges.
- **``android:layout_above``**, **``android:layout_below``**, **``android:layout_toLeftOf``**, **``android:layout_toRightOf``**: These attributes specify the relative positioning of a child view with respect to other child views.
- **``android:layout_centerHorizontal``**, **``android:layout_centerVertical``**, **``android:layout_centerInParent``**: These attributes are used to center child views within the parent layout.
- **``android:layout_alignBaseline``**: It aligns a child view's baseline with the baseline of another view.

#### TableLayout:
``TableLayout`` arranges its child views in rows and columns, similar to an HTML table. It's useful for creating tabular layouts.

**Attributes:**

- **``android:stretchColumns``**: This attribute specifies which columns should stretch to fill available space evenly.
- **``android:layout_column``**: Used in child views to specify which column they should be placed in.
- **``android:layout_span``**: This attribute allows a child view to span multiple columns or rows in the table.

#### AbsoluteLayout:
An ``AbsoluteLayout`` lets you specify exact locations (x/y coordinates) of its children. Absolute layouts are less flexible and harder to maintain than other types of layouts without absolute positioning.

**Attributes:**

- **``android:layout_x``**: This specifies the **x-coordinate** of the view.
- **``android:layout_y``**: This specifies the **y-coordinate** of the view.

#### ConstraintLayout:
``ConstraintLayout`` is a more powerful and flexible layout that allows you to create complex UIs with a flat view hierarchy. It uses constraints to define relationships between views, making it suitable for responsive designs and dynamic UIs.

**Attributes:**

- **``app:layout_constraintTop_toTopOf``**, **``app:layout_constraintBottom_toBottomOf``**, **``app:layout_constraintStart_toStartOf``**, **``app:layout_constraintEnd_toEndOf``**: These attributes specify the constraints that position child views relative to the parent layout or other child views.
- **``app:layout_constraintHorizontal_bias``**, **``app:layout_constraintVertical_bias``**: These attributes control the positioning of a view within its constraints by specifying a bias value between ``0`` and ``1``.
- **``app:layout_constraintDimensionRatio``**: It defines the aspect ratio of a view.
- **``app:layout_constraintHorizontal_chainStyle``**, **``app:layout_constraintVertical_chainStyle``**: These attributes control how chains of views are aligned and distributed within a ConstraintLayout.
- **``app:layout_constraintGuide_percent``**: You can use this attribute to create guidelines in the layout that help position child views.

## Layout Attributes
---------------------
Each layout has a set of attributes which define the visual properties of that layout. There are few common attributes among all the layouts and their are other attributes which are specific to that layout. Following are common attributes and will be applied to all the layouts:

- **``android:id``** : Used to specify the id of the view.
- **``android:layout_width``** : Used to declare the width of ``View`` and ``ViewGroup`` elements in the layout.
- **``android:layout_height``** : Used to declare the height of ``View`` and ``ViewGroup`` elements in the layout.
- **``android:layout_marginLeft``** : Used to declare the extra space used on the ``left`` side of ``View`` and ``ViewGroup`` elements.
- **``android:layout_marginRight``** : Used to declare the extra space used on the ``right`` side of ``View`` and ``ViewGroup`` elements.
- **``android:layout_marginTop``** : Used to declare the extra space used in the ``top`` side of ``View`` and ``ViewGroup`` elements.
- **``android:layout_marginBottom``** : Used to declare the extra space used in the ``bottom`` side of ``View`` and ``ViewGroup`` elements.
- **``android:layout_gravity``** : Used to define how child Views are positioned in the layout.

## Android Widget (TextView, EditText, CheckBox, RadioButton, Spinner) and its Attributes
------------------------------------------------------------------------------------------

In the context of ``Android`` development, **Widgets** refer to the **UI elements** or components that users can interact with on the screen. Widgets are the building blocks of the user interface and are used to create various visual and interactive elements in an Android app. They can range from simple UI elements like buttons and text views to more complex components like lists, grids, and progress bars. 

### Button: 
The ``Button`` widget is used to trigger actions when clicked by the user.

**Attributes:**
- **``android:id``**: Unique identifier for the button.
- **``android:text``**: Text displayed on the button.
- **``android:onClick``**: Method name in the activity that will be executed when the button is clicked.
- **``android:background``**: Background drawable or color of the button.
- **``android:layout_width``**, **``android:layout_height``**: Dimensions of the button.

### TextView:
**TextView** is used to display text or a combination of text and other content within an Android app's user interface

**Attributes:**
- **``android:text``**: Specifies the text content to be displayed within the TextView. You can provide plain text or string resource references.
- **``android:textSize``**: Defines the size of the text displayed in the TextView. It can be specified in units such as ``sp`` or ``dp``.
- **``android:textColor``**: Determines the color of the text within the TextView. You can use color resource references or predefined color values.
- **``android:gravity``**: Specifies the alignment of the text within the ``TextView``, including values like **left**, **right**, **center**, and others.
- **``android:layout_width``**, **``android:layout_height``**: Dimensions of the TextView.

### EditText: 
The ``EditText`` widget is used for user input, such as typing text or numbers.

**Attributes:**
- **``android:id``**: Unique identifier for the EditText.
- **``android:hint``**: Hint text displayed before the user starts typing.
- **``android:inputType``**: Type of input (text, number, email, etc.).
- **``android:maxLines``**: Maximum number of lines of text.
- **``android:layout_width``**, **``android:layout_height``**: Dimensions of the EditText.

### CheckBox:
The ``CheckBox`` widget allows users to select multiple options from a set of choices.

**Attributes:**
- **``android:id``**: Unique identifier for the CheckBox.
- **``android:text``**: Text displayed next to the checkbox.
- **``android:checked``**: Initial checked state of the CheckBox.
- **``android:layout_width``**, **``android:layout_height``**: Dimensions of the CheckBox.

### RadioButton 
The ``RadioButton`` widget allows users to select single-choice option within a group of options.

**Attributes:**
- **``android:id``**: Unique ID for referencing.
- **``android:text``**: Text displayed next to checkbox.
- **``android:checked``**: Initial checked state.
- **``android:layout_width``**, **``android:layout_height``**: Dimensions.
- **``android:layout_gravity``**, **``android:layout_weight``**: Layout positioning.
- **``android:enabled``**: Enable/disable.
- **``android:clickable``**, **``android:focusable``**: Clickable and focusable behavior.

### Spinner:
The Spinner widget displays a dropdown menu of selectable items.

**Attributes:**
- **``android:id``**: Unique identifier for the Spinner.
- **``android:entries``**: Array resource or values to populate the spinner items.
- **``android:prompt``**: Text displayed as the prompt for the Spinner.
- **``android:layout_width``**, **``android:layout_height``**: Dimensions of the Spinner.

### ImageView:
The ``ImageView`` widget is used to display images.

**Attributes:**
- **``android:id``**: Unique identifier for the ImageView.
- **``android:src``**: Image resource to display in the ImageView.
- **``android:scaleType``**: How the image should be scaled within the ImageView.
- **``android:layout_width``**, **``android:layout_height``**: Dimensions of the ImageView.
- **``android:layout_gravity``**: Alignment of the ImageView within its parent.

## Event Handeling
-------------------
``Events`` are the actions performed by the user in order to interact with the application.

Events are a useful way to collect data about a user's interaction with interactive components of Applications. Like button presses or screen touch etc. The Android framework maintains an event queue as ``first-in, first-out (FIFO)`` basis. You can capture these events in your program and take appropriate action as per requirements.

There are following three concepts related to Android Event Management:

- **Event Listeners** : An event listener is an interface in the View class that contains a single callback method. These methods will be called by the Android framework when the View to which the listener has been registered is triggered by user interaction with the item in the UI.

- **Event Listeners Registration** : ``Event Registration`` is the process by which an Event Handler gets registered with an Event Listener so that the handler is called when the Event Listener fires the event.

- **Event Handlers** : When an event happens and we have registered an event listener for the event, the event listener calls the Event Handlers, which is the method that actually handles the event.

### **Event Listeners & Event Handlers**

|         Event Handler       |                                                                                          Event Listener & Description                                                                                                               |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|**``onClick()``**            | ``OnClickListener()``:This is called when the user either clicks or touches or focuses upon any widget like button, text, image etc. You will use ``onClick()`` event handler to handle such event.                                 |
|**``onLongClick()``**        | ``OnLongClickListener()``:This is called when the user either clicks or touches or focuses upon any widget like button, text, image etc. for one or more seconds. You will use ``onLongClick()`` event handler to handle such event.|
|**``onFocusChange()``**      | ``OnFocusChangeListener()``:This is called when the widget looses its focus ie. user goes away from the view item. You will use ``onFocusChange()`` event handler to handle such event.                                             |
|**``onKey()``**              | ``OnKeyListener()``:This is called when the user is focused on the item and presses or releases a hardware key on the device. You will use ``onKey()`` event handler to handle such event.                                          |
|**``onTouch()``**            | ``OnTouchListener()``:This is called when the user presses the key, releases the key, or any movement gesture on the screen. You will use ``onTouch()`` event handler to handle such event.                                         |
|**``onMenuItemClick()``**    | ``OnMenuItemClickListener()``:This is called when the user selects a menu item. You will use ``onMenuItemClick()`` event handler to handle such event.                                                                              |
|**``onCreateContextMenu()``**| ``OnCreateContextMenuItemListener()``:This is called when the context menu is being built(as the result of a sustained "long click)                                                                                                 |

Following example will demonstrate ``onClick()`` event. For this we are creating a ``Button`` and while clicking ``Button`` a ``Toast`` message will be displayed on screen.

```Xml
<Button
    android:layout_width="wrap_content" 
    android:layout_height="wrap_content"
    android:text="Click Me"
    android:layout_centerInParent="true"
    android:id="@+id/testbutton"
/>
```

```Java
Button btn=findViewById(R.id.testbutton);
//adding click event and listener
btn.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View view) {
        //displaying message
        Toast.makeText(getApplicationContext(),"Button Clicked!",Toast.LENGTH_SHORT).show();
    }
});
```

## Working with String, String Array and Color
----------------------------------------------

### **Strings:**

Strings are used for displaying text in your app's user interface. You can store them in a dedicated ``strings.xml`` resource file for easy localization and maintenance.

#### Creating Strings:

To create a string resource, add an entry in the ``strings.xml`` file located in the ``res/values`` directory. Here's an example:

```Xml
<resources>
    <string name="app_name">My App</string>
    <string name="welcome_message">Welcome to my app!</string>
</resources>
```

#### Accessing Strings:
In your Java code, you can access string resources using ``R.string.resource_name``, like this:

```Java
String appName = getString(R.string.app_name);
String welcomeMessage = getString(R.string.welcome_message);
```

### **String Array:**

String arrays allow you to store multiple related strings in a single resource. They are helpful for managing lists, menu items, and other groups of strings.

#### Creating String Arrays:
Define a string array in ``strings.xml``:

```Xml
<resources>
    <string-array name="colors">
        <item>Red</item>
        <item>Green</item>
        <item>Blue</item>
    </string-array>
</resources>
```
### Accessing String Arrays:
In code, retrieve string arrays using ``R.array.array_name``:

```Java
String[] colors = getResources().getStringArray(R.array.colors);
```

### **Colors:**

Colors are used to set the color of UI elements like text, backgrounds, and shapes.

#### Creating Colors:
Define color resources in ``colors.xml`` (located in ``res/values``):

```Xml
<resources>
    <color name="red">#FF0000</color>
    <color name="green">#00FF00</color>
    <color name="blue">#0000FF</color>
</resources>
```

#### Accessing Colors:
In XML layout files, you can set colors directly using ``@color/color_name``. In code, use ``ContextCompat.getColor()`` to retrieve colors:

```Java
int redColor = ContextCompat.getColor(this, R.color.red);
int greenColor = ContextCompat.getColor(this, R.color.green);
```

## Working with Resources and Drawable
---------------------------------------
Working with resources and drawables is fundamental in Android app development, as it allows you to include images, icons, and other assets in your app. Here's a brief overview of how to work with these resources:

### **Drawable Resources:**
Drawables are used to represent images and icons in Android applications. They can be included in different drawable resource folders for different screen densities and sizes.

#### Adding Drawable Resources:
- Place your image files (e.g., PNG, JPEG, SVG) in the appropriate drawable resource folders, such as ``res/drawable-mdpi``, ``res/drawable-hdpi``, ``res/drawable-xhdpi``, etc., based on screen density.
- You can also include vector drawable XML files in the ``res/drawable`` folder for vector graphics.

#### Accessing Drawable Resources:
- In XML layout files, you can set the drawable attribute to reference a drawable resource using ``@drawable/drawable_name``.
- In Java, use ``R.drawable.drawable_name`` to access drawable resources.

### **String Resources (as References)**:
You can use string resources to reference drawable names dynamically, which is useful when you need to load images programmatically based on conditions.

#### Referencing Drawable Names with Strings:
- Define string resources that correspond to drawable names in ``strings.xml``. For example:
    ```Xml
    <resources>
        <string name="image_name">my_image</string>
    </resources>
    ```
- In your code, retrieve the string resource and use it to reference a drawable dynamically:
    ```Java
    String imageName = getString(R.string.image_name);
    int drawableResId = getResources().getIdentifier(imageName, "drawable", getPackageName());
    Drawable drawable = ContextCompat.getDrawable(this, drawableResId);
    ```

### **Drawable States and Selector Drawables:**
You can create drawable resources that represent different states of UI elements, such as **normal**, **pressed**, or **focused** states. This is often used for buttons, checkboxes, and other interactive components.

#### Creating Selector Drawables:

- Create an ``XML`` file in the ``res/drawable`` folder that defines the different states and the corresponding drawable resources. This XML file is known as a selector drawable.

- Here's an example of a selector drawable for a button with different states:

    ```Xml
    <selector xmlns:android="http://schemas.android.com/apk/res/android">
        <item android:drawable="@drawable/button_pressed" android:state_pressed="true" />
        <item android:drawable="@drawable/button_focused" android:state_focused="true" />
        <item android:drawable="@drawable/button_normal" />
    </selector>
    ```

- Use this selector drawable as the background of your UI element.

## Adding icon to a Android Project
------------------------------------
- Open the ``AndroidManifest.xml`` file, typically located in the ``app/src/main`` directory.

- Inside the ``<application>`` element, add the ``android:icon`` attribute and specify the icon's filename without the file extension. For example:

```Xml
<application android:icon="@drawable/ic_launcher">
```