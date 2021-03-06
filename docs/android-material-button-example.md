<!--docs:
title: "Example Article: Android Button"
layout: detail
section: components
excerpt: "This is an example of the Android Material Button developer article for material.io. It uses the template from [../article-component-template.md]"
iconId:
path: /
api_doc_root:
-->

# Buttons

The buttons component of Material.io can be implemented in Android OS with `Material Button` and `MaterialButtonToggleGroup`. This button component has several built-in styles to support different levels of emphasis, as typically any UI will contain a few different buttons to indicate different actions.

For more guidance, go to the material.io [Buttons](http://material.io/components/buttons) page.

## Material button variants

1. [Text button](#text-button)
1. [Outlined button](#outlined-button)
1. [Contained button (Filled and raised)](#contained-button)
1. [Toggle  (Material button toggle group)](#material-button-toggle-group)



## Using Buttons

### Related APIs

#### Material button

 Go  to the [Android MaterialButton API](https://developer.android.com/reference/com/google/android/material/button/MaterialButton) for more details.
```xml
<com.google.android.material.button.MaterialButton
  android:<property>="<property value>"
   ...
   style="@style/widget.MaterialComponents.<style value>"
/>
```
#### Material button attributes without icons

Attribute | Description | Possible values
---|---|---
`android:id` | | `"@+id/material_button"` </br> `"@+id/disabled_material_button"` </br> `"@+id/material_unelevated_button"`
`android:layout_width` | | `"wrap_content"`
`android:layout_height` | | `"wrap_content"`
`android:enabled` | | `true`\|`false`
`android:text` | | `"@string/button_label_enabled"`</br> `"@string/button_label_disabled"`
`style`| |`"@style/Widget.MaterialComponents.Button.UnelevatedButton"` </br> `"@style/Widget.MaterialComponents.Button.TextButton"`

##### Material button attributes with icons

The .Icon style should only be used for start-gravity icon buttons. If your icon is end-gravity, you cannot use a .Icon style and must instead manually adjust your padding such that the visual adjustment is mirrored.

<img src="images/buttons-elements-icon-01.png">

Attribute | Description | Possible values
---|---|---
`android:id` |  | `"@+id/material_icon_button"` </br> `"@+id/disabled_icon_material_button"` </br> `"@+id/material_icon_unelevated_button"`
`android:layout_width` |  | `"wrap_content"`
`android:layout_height` |  | `"wrap_content"`
`android:enabled` |  | `true`\|`false`
`android:text` |  | `"@string/icon_button_label_enabled"`</br> `"@string/icon_button_label_disabled"`
`app:icon` | adds an icon to the button | `"@drawable/icon_24px"`
`style`|  | `"@style/Widget.MaterialComponents.Button.Icon"` </br> `"@style/Widget.MaterialComponents.Button.TextButton.Icon"`

#### Material Button Toggle Group
Go  to the [Android MaterialButtonToggleGroup API](https://developer.android.com/reference/com/google/android/material/button/MaterialButtonToggleGroup) for more details.

**Note** We recommend that child buttons use an outlined style. 

```xml
<com.google.android.material.button.MaterialButtonToggleGroup
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/toggle_button_group"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content">

    <com.google.android.material.button.MaterialButton
        style="?attr/materialButtonOutlinedStyle"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/button_label_private"/>
        /*...*/
    <com.google.android.material.button.MaterialButton
        style="?attr/materialButtonOutlinedStyle"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/button_label_custom"/>

</com.google.android.material.button.MaterialButtonToggleGroup>
```

#### Material button toggle group attributes

Attribute | Description | Possible values
---|---|---
`android:id` | | `"@+id/toggle_button_group"`
`android:layout_width` | | `"wrap_content"`
`android:layout_height` | | `"wrap_content"`
`android:enabled` | | `true`\|`false`
`style`| |`"@style/Widget.MaterialComponents.Button.UnelevatedButton"` </br> `"@style/Widget.MaterialComponents.Button.TextButton"`

#### Material button toggle group methods

Method | Description
---|---
`addView(View)`| Programmatically adds buttons to the toggle group
`OnButtonCheckedListener` | Listens for changes to the child buttons' checked state
`addOnButtonCheckedListener`| Adds a listener to check the state of child buttons
`removeOnButtonCheckedListener` | Removes listener that checks the sate of child buttons

Go  to the [Android MaterialButtonToggleGroup API](https://developer.android.com/reference/com/google/android/material/button/MaterialButtonToggleGroup) for more details.

**Note** We recommend that child buttons use an outlined style. For more information on button styling, see [MaterialButton](MaterialButtonExample.md)

```xml
<com.google.android.material.button.MaterialButtonToggleGroup
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/toggle_button_group"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content">

    <com.google.android.material.button.MaterialButton
        style="?attr/materialButtonOutlinedStyle"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/button_label_private"/>
        /*...*/
    <com.google.android.material.button.MaterialButton
        style="?attr/materialButtonOutlinedStyle"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/button_label_custom"/>

</com.google.android.material.button.MaterialButtonToggleGroup>
```

#### Material button toggle group attributes

Attribute | Description | Possible values
---|---|---
`android:id` | | `"@+id/toggle_button_group"`
`android:layout_width` | | `"wrap_content"`
`android:layout_height` | | `"wrap_content"`
`android:enabled` | | `true`\|`false`
`style`| |`"@style/Widget.MaterialComponents.Button.UnelevatedButton"` </br> `"@style/Widget.MaterialComponents.Button.TextButton"`

#### Material button toggle group methods

Method | Description
---|---
`addView(View)`| Programmatically adds buttons to the toggle group
`OnButtonCheckedListener` | Listens for changes to the child buttons' checked state
`addOnButtonCheckedListener`| Adds a listener to check the state of child buttons
`removeOnButtonCheckedListener` | Removes listener that checks the sate of child buttons


### Text button

Text buttons are typically used for less-pronounced actions, including those located:
* In dialogs
* In cards
In cards, text buttons help maintain an emphasis on card content.



<img src="images/text-button-usage.png">

Attribute | Attribute value | Element description
---|---|---
 android:id | `"@+id/material_text_button"` |
 style | `"@style/Widget.MaterialComponents.Button.TextButton"` </br> `"@style/Widget.MaterialComponents.Button.TextButton.Icon"` |
 android:layout_width | `"wrap_content" ` |
 android: layout_height | `"wrap_content"` |
 android:text | `"@string/text_button_label_enabled"`|

#### Text button example
```xml
 <com.google.android.material.button.MaterialButton
    android:id="@+id/material_text_button"
    style="@style/Widget.MaterialComponents.Button.TextButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="@string/text_button_label_enabled"/>
```
### Outlined button

Outlined buttons are medium-emphasis buttons. They contain actions that are important, but aren’t the primary action in an app.

<img src="images/outlined-button-usage.png">

 Attribute | Attribute value | Element description
---|---|---
 android:id | `"@+id/material_text_button"` |
 style | `"@style/Widget.MaterialComponents.Button.TextButton"` </br>`"@style/Widget.MaterialComponents.Button.OutlinedButton.Icon"` |
 android:layout_width | `"wrap_content"`|
 android: layout_height | `"wrap_content"`|
 android:text | `"@string/text_button_label_enabled"` |  

#### Outlined button example
```xml
<com.google.android.material.button.MaterialButton
    android:id="@+id/material_text_button"
    style="@style/Widget.MaterialComponents.Button.OutlinedButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="@string/outlined_button_label_enabled"/>
```
### Contained button
Contained buttons are high-emphasis, distinguished by their use of elevation and fill. They contain actions that are primary to your app.

**Note** Elevated `MaterialButtons` have a shadow that can extend outside the bounds of the button. For this reason, the wrapping parent element should set to `android:clipToPadding="false"` in cases where the button shadow could be clipped by the parent bounds.

<img src="images/contained-button-usage.png">

Attribute | Attribute value | Element description
---|---|---
android:id | `"@+id/material_button"` |
style | `"@style/Widget.MaterialComponents.Button"` </br> `"@style/Widget.MaterialComponents.Button.Icon"` </br> `"@style/Widget.MaterialComponents.Button.UnelevatedButton"` </br> `"@style/Widget.MaterialComponents.Button.UnelevatedButton.Icon"` |
android:layout_width | `"wrap_content"` |
android: layout_height | `"wrap_content"`|
android:text | `"@string/text_button_label_enabled"` |  

#### Contained button example
```xml
<com.google.android.material.button.MaterialButton
    android:id="@+id/material_button"
    style="@style/Widget.MaterialComponents.Button"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="@string/button_label_enabled"/>
```

#### Contained button example with wrapping parent element `GridLayout`

```xml
<GridLayout
      android:id="@+id/grid"
      android:layout_width="match_parent"
      android:layout_height="wrap_content"
      android:layout_gravity="center"
      android:padding="16dp"
      android:clipToPadding="false"
      android:columnCount="2">

    <com.google.android.material.button.MaterialButton
        android:id="@+id/material_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/button_label_enabled"/>

    <Space/>
  </GridLayout>
```

## Example: Contained button

<details>
  <summary><b>Add a filled and elevated button</b></summary>

    <img src="" alt="Contained button Android render without an icon">  

 The following code adds a filled and elevated button to your app. Your theme's `colorPrimary` is the default background color and your theme's `colorOnPrimary` is the default text color.
   ```xml
    <com.google.android.material.button.MaterialButton
      android:id="@+id/material_button"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:text="@string/button_label_enabled"/>
  ```
</details>

## Example: Contained button with icon
<details>
<summary><b>Add a filled and unelevated button</b></summary>

  <img src="" alt="Contained button Android render with an icon">

 The following code adds a filled and unelevated button. Your theme's `colorPrimary` is the default background color and your theme's `colorOnPrimary` is the default text color.
  ```xml
    <com.google.android.material.button.MaterialButton
      android:id="@+id/disabled_material_button"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:enabled="false"
      android:text="@string/button_label_disabled"/>
  ```

</details>

### Example: Toggle group with buttons
<details>
<summary><b>The following example shows a toggle group with outlined buttons.</b></summary>

<img src="" alt="toggle button group with outlined buttons">

```xml
\* example code here *\
```
</details>

### Example: Toggle group with icon toggle buttons over images

<details>
<summary><b>he following example shows a icon toggle group over images.</b></summary>
<img src="" alt="toggle button group with icons buttons over images">

```xml
\* example code here *\
```
</details>
