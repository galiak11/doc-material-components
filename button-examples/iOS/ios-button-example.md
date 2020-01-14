<!--docs:
title: ttons"<component name>"
layout: detail
section: components
excerpt: "iOS Buttons"
ide_version: "<cIDE name> <compatible IDE version and build number>"
material_package_version: "<compatible Material platform package version number>"
iconId:
path: /
api_doc_root:
-->

# Buttons

[Buttons](https://material.io/components/buttons/) allow users to take actions, and make choices, with a single tap.

There are four types of buttons:

1. [Text button](#text-button)
2. [Outlined button](#outlined-button)
3. [Contained button](#contained-button)
4. [Toggle button](#toggle-button) - Not Yet Supported on iOS.

**A NOTE TO AUTHOR OF THIS PAGE: (1) iOS does not have a toggle button, so this should be expalined here. (2) The toggle button image shows a UISegmentedControl, not the cards example's toggle button - which is different. (3) The card's example should go in the cards page - it doesn't belong here.**

![Example of the four button types](assets/mio-button-types.png)


## Using button

### Install `MDCButtons`

<details><summary>Expand for installation instructions for `MDCButtons`</summary>

Before using the `MDCButtons` API to implement its types you must install `MCDButtons`. In your source files import the component, and then apply your theme:
1. Install `MDCButtons`
   * Use CocoaPods to install `MDCButtons`
     1. Add the following line to your `Podfile`:
       ```java
      pod MaterialComponents/Buttons
       ```
     1. Run the installer:
       ```bash
       pod install
       ```
1. Import `MDCButtons` and MDC button theming and initialize `MDCButtons` using `alloc`/`init`. Initialize your theme  before applying it to your button.

    **Note** For more information about themes, go to the [Theming page](https://material.io/develop/ios/components/theming/) for iOS.

     **Swift** 
     ```swift
     import MaterialComponents.MaterialButtons
     import MaterialComponents.MaterialButtons_Theming
     import MaterialComponents.MaterialContainerScheme
     
     // Create the button.
     let button = MDCButton()
     // Apply a text theme.
     let containerScheme = MDCContainerScheme()
     button.applyTextTheme(withScheme: containerScheme)

     ```
     **Objective-C**
     ```objc
     #import "MaterialButtons.h"
     #import "MaterialButtons+Theming.h"
     #import "MaterialContainerScheme.h"
     
     // Create the button.
     MDCButton *button = [[MDCButton alloc] init];
     // Apply a text theme.
     MDCContainerScheme *containerScheme = [[MDCContainerScheme alloc] init];
     [button applyTextThemeWithScheme:containerScheme];
     ```
1. Apply accessibility settings
 
    To help make your buttons usable to as many users as possible, set an appropriate [`accessibilityLabel`](https://developer.apple.com/documentation/uikit/uiaccessibilityelement/1619577-accessibilitylabel) value if your button does not have a title or only has an icon:

    **Swift**
    ```swift
    button.accessibilityLabel = "Create"
    ```
    **Objective-C**
    ```objc
    button.accessibilityLabel = @"Create";
    ```

</details>

\<**NOTE** Update table values and links to appropriate API documents\>
-----

## Text button

[Text buttons](https://material.io/components/buttons/#text-button) are typically used for less-pronounced actions, including those located in dialogs and cards. In cards, text buttons help maintain an emphasis on card content.


### Text button example

Source Code APIs:

* MDCButton
    * [Class description](https://material.io/develop/ios/components/buttons/api-docs/Classes/MDCButton.html)
    * [GitHub source](https://github.com/material-components/material-components-ios/blob/develop/components/Buttons/src/MDCButton.h)
* [Themes class description](https://material.io/develop/ios/components/theming/) <!-- This is slated to be deprected, though the examples from https://material.io/develop/ios/components/buttons/api-docs/Classes/MDCButton.html appear to use this class -->

The following example shows a text button with a text label.

!["Text button example for iOS with purple text 'Text' over a white background."](assets/text-button.svg)

**Swift**

```swift
import MaterialComponents.MaterialButtons
import MaterialComponents.MaterialButtons_Theming
import MaterialComponents.MaterialContainerScheme

// Create the button.
let button = MDCButton()
// Apply a text theme.
let containerScheme = MDCContainerScheme()
button.applyTextTheme(withScheme: containerScheme)
```

**Objective-C**

```ObjC
#import "MaterialButtons.h"
#import "MaterialButtons+Theming.h"
#import "MaterialContainerScheme.h"

// Create the button.
MDCButton *button = [[MDCButton alloc] init];
// Apply a text theme.
MDCContainerScheme *containerScheme = [[MDCContainerScheme alloc] init];
[button applyTextThemeWithScheme:containerScheme];
```
<details>
<summary><b>Adding an icon to a text button</b></summary>
<br>

The following example shows a text button with an icon.

!["Text button example for Android with purple text 'Text button' and '+' icon over a white background."](assets/text-button-icon.svg)

```swift

```


```objc

```

</details>

### Anatomy and key properties

A text button has a text label, a transparent container and an optional icon.

![<Placeholder diagram of text button anatomy. Replace this text if/when there is an approved diagram\>](assets/text-button-diagram.png)

**1. Text button**
* A Text label
* B Container
* C Icon

<details>
<summary><b>Text label</b> attributes</summary>
<br>

|  | Attribute | Related method(s) | Default value |
| --- | --- | --- | --- |
| **Text label** ||  | |
| **Color** |  |  | |
| **Typography** |  |  |  |

</details>

<details>
<summary><b>Container</b> attributes</summary>
<br>

|  | Attribute | Related method(s) | Default value |
| --- | --- | --- | --- |
| **Color** |  |  | |
| **Stroke color** | |  | |
| **Stroke width** |  |  |  |
| **Shape** |  | | |
| **Elevation** | | | |
| **Ripple color** | | | | 
</details>

<details>
<summary><b>Icon</b> attributes</summary>
<br>

|  | Attribute | Related method(s) | Default value |
| --- | --- | --- | --- |
| **Icon** | | | |
| **Color** | | | |
| **Size** | | | |
| **Gravity** (position relative to text label) | | | |
| **Padding** (space between icon and text label) | | | |

</details>


## Outlined button

[Outlined buttons](https://material.io/components/buttons/#outlined-button) are medium-emphasis buttons. They contain actions that are important, but aren’t the primary action in an app.

### Outlined button example without container schemes

You can apply a theme to the button using `Themes`.

Source Code APIs:

* MDCButton
    * [Class description](https://material.io/develop/ios/components/buttons/api-docs/Classes/MDCButton.html)
    * [GitHub source](https://github.com/material-components/material-components-ios/blob/develop/components/Buttons/src/MDCButton.h)
* [Themes class description](https://material.io/develop/ios/components/theming/)  <!-- This is slated to be deprected, though the examples from https://material.io/develop/ios/components/buttons/api-docs/Classes/MDCButton.html appear to use this class -->

The following example shows an outlined button with a text label and stroked container.    

!["Outlined button example in Android with purple text surrounded by a gray outline"](assets/outlined-button.svg)

**Swift**
```swift
import MaterialComponents.MaterialButtons
import MaterialComponents.MaterialButtons_Theming
import MaterialComponents.MaterialContainerScheme

// Create the button.
let button = MDCButton()
// Apply a text theme.
let containerScheme = MDCContainerScheme()
button.applyOutlinedTheme(withScheme: containerScheme)
```

**Objective-C**
```objc

#import "MaterialButtons.h"
#import "MaterialButtons+Theming.h"
#import "MaterialContainerScheme.h"

// Create the button.
MDCButton *button = [[MDCButton alloc] init];
// Apply a text theme.
MDCContainerScheme *containerScheme = [[MDCContainerScheme alloc] init];
[button applyOutlinedThemeWithScheme:containerScheme];
```

### Outlined button example with container schemes

You can apply a theme to the button that applies to all elements in a container using `MDCContainerScheme`.

Source Code APIs:

* MDCButton
    * [Class description](https://material.io/develop/ios/components/buttons/api-docs/Classes/MDCButton.html)
    * [GitHub source](https://github.com/material-components/material-components-ios/blob/develop/components/Buttons/src/MDCButton.h)
* [Themes class description](https://material.io/develop/ios/components/theming/)  <!-- This is slated to be deprected, though the examples from https://material.io/develop/ios/components/buttons/api-docs/Classes/MDCButton.html appear to use this class -->
* [MDCContainerScheme class description](https://github.com/material-components/material-components-ios/tree/stable/components/schemes/Container)

!["Outlined button example in Android with purple text surrounded by a gray outline"](assets/outlined-button.svg)

**Swift**
```swift
import MaterialComponents.MaterialButtons
import MaterialComponents.MaterialButtons_Theming
import MaterialComponents.MaterialContainerScheme

// Create the button.
let button = MDCButton()
// Apply a text theme.
let containerScheme = MDCContainerScheme()
button.applyOutlinedTheme(withScheme: containerScheme)    // text or outline?
```

**Objective-C**
```objc
#import "MaterialButtons.h"
#import "MaterialButtons+Theming.h"
#import "MaterialContainerScheme.h"

// Create the button.
MDCButton *button = [[MDCButton alloc] init];
// Apply a text theme.
MDCContainerScheme *containerScheme = [[MDCContainerScheme alloc] init];
[button applyOutlinedThemeWithScheme:containerScheme];    // text or outline?
```

### Anatomy and key properties

An outline button has text, a container, and an optional icon.

![<Placeholder diagram of outlined button anatomy. Replace this text if/when there is an approved diagram\>](assets/outlined-button-diagram.png)

**2. Outlined button**
* A Text label
* B Container
* C Icon

<details>
<summary><b>Text label</b> attributes</summary>
<br>

|  | Attribute | Related method(s) | Default value |
| --- | --- | --- | --- |
| **Text label** | | | |
| **Color** |  | | |
| **Typography** | | | |


</details>

<details>
<summary><b>Container</b> attributes</summary>
<br>

|  | Attribute | Related method(s) | Default value |
| --- | --- | --- | --- |
| **Color** | | | |
| **Stroke color** | | | |
| **Stroke width** || | |
| **Shape** | | | |
| **Elevation** | | | |
| **Ripple color** | | | |

</details>

<details>
<summary><b>Icon</b> attributes</summary>
<br>

|  | Attribute | Related method(s) | Default value |
| --- | --- | --- | --- |
| **Icon** | | | |
| **Color** || | |
| **Size** | | | |
| **Gravity** (position relative to text label) | | | |
| **Padding** (space between icon and text label) | | | |

</details>


## Contained button

[Contained buttons](https://material.io/components/buttons/#contained-button) are high-emphasis, distinguished by their use of elevation and fill. They contain actions that are primary to your app.

### Contained button example

Source Code APIs:

* MDCButton
    * [Class description](https://material.io/develop/ios/components/buttons/api-docs/Classes/MDCButton.html)
    * [GitHub source](https://github.com/material-components/material-components-ios/blob/develop/components/Buttons/src/MDCButton.h)
* [Themes class description](https://material.io/develop/ios/components/theming/)  <!-- This is slated to be deprected, though the examples from https://material.io/develop/ios/components/buttons/api-docs/Classes/MDCButton.html appear to use this class -->

The following example shows a contained button with a text label and a filled container.

!["Contained button example for Android with the white text 'Text' on a purple background."](assets/contained-button.svg)

**Swift**
```swift
import MaterialComponents.MaterialButtons
import MaterialComponents.MaterialButtons_Theming
import MaterialComponents.MaterialContainerScheme

// Create the button.
let button = MDCButton()
// Apply a text theme.
let containerScheme = MDCContainerScheme()
button.applyContainedTheme(withScheme: containerScheme)
```

**Objective-C**
```objc
#import "MaterialButtons.h"
#import "MaterialButtons+Theming.h"
#import "MaterialContainerScheme.h"

// Create the button.
MDCButton *button = [[MDCButton alloc] init];
// Apply a text theme.
MDCContainerScheme *containerScheme = [[MDCContainerScheme alloc] init];
[button applyContainedThemeWithScheme:containerScheme];
```


### Anatomy and key attributes

A contained button has text, a container, and an optional icon.


![\<Placeholder diagram of outlined button attribute. Replace this text if/when there is an approved diagram\>](assets/contained-button-diagram.png)

**3. Contained button**
* A Text label
* B Container
* C Icon


<details>
<summary><b>Text label</b> attributes</summary>
<br>

|  | Attribute | Related method(s) | Default value |
| --- | --- | --- | --- |
| **Text label** | | | |
| **Color** |  | | |
| **Typography** | | | |


</details>

<details>
<summary><b>Container</b> attributes</summary>
<br>

|  | Attribute | Related method(s) | Default value |
| --- | --- | --- | --- |
| **Color** | | | |
| **Stroke color** | | | |
| **Stroke width** || | |
| **Shape** | | | |
| **Elevation** | | | |
| **Ripple color** | | | |

</details>

<details>
<summary><b>Icon</b> attributes</summary>
<br>

|  | Attribute | Related method(s) | Default value |
| --- | --- | --- | --- |
| **Icon** | | | |
| **Color** || | |
| **Size** | | | |
| **Gravity** (position relative to text label) | | | |
| **Padding** (space between icon and text label) | | | |

</details>



## Toggle button

[Toggle buttons](https://material.io/components/buttons/#toggle-button) can be used to select from a group of choices.

There are two types of toggle buttons:

* [Toggle button](#toggle-button)
* [Icon](#icon)

### Toggle button

The toggle button allows you to select from a group of buttons that can be set to [selective action](https://material.io/components/buttons/#toggle-button) where only one button in a group can be selected at one time.

The Material toggle bar is not supported in iOS. 

### Icon

Icons can be used as toggle buttons when they allow selection, or deselection, of a single choice, such as marking an item as a favorite.


#### Icon example

Source code APIs:

* [MDCCardCollectionCell](https://material.io/develop/ios/components/cards/api-docs/Classes/MDCCardCollectionCell.html)
* [UICollectionViewController]()
* [Themes class description](https://material.io/develop/ios/components/theming/)  <!-- This is slated to be deprected, though the examples from https://material.io/develop/ios/components/buttons/api-docs/Classes/MDCButton.html appear to use this class -->


The following example shows 4 images arranged in a 2-by-2 array with a favorite icon in the upper-right corner of each image.

<img src="assets/iOS-toggle-icon.png" alt="iOS toggle example showing 4 images in an array with a favorite icon in the upper-right corner of each image.">


It uses the class `ToggleButtonCell` &ndash; which extends the `MDCCardCollectionCell` &ndash; to display the image and the icon, and provide gesture recognition for each cell of the array.

```swift
import MaterialComponents.MaterialCards_Theming
import UIKit

class ToggleButtonCell: MDCCardCollectionCell {

  private lazy var imageView: UIImageView = {
    let imageView = UIImageView(frame: CGRect.zero)
    imageView.contentMode = .scaleAspectFill
    imageView.clipsToBounds = true
    imageView.translatesAutoresizingMaskIntoConstraints = false
    return imageView
  }()

  override init(frame: CGRect) {
    super.init(frame: frame)
    setCustomToggleButton()
  }

  required init?(coder aDecoder: NSCoder) {
    super.init(coder: aDecoder)
    setCustomToggleButton()
  }

  func setCardImage(named imageName: String) {

    let bundle = Bundle(for: ToggleButtonCell.self)
    imageView.image = UIImage(named: imageName, in: bundle, compatibleWith: nil)
    imageView.contentMode = .scaleAspectFill

    if imageView.superview == nil {
      contentView.addSubview(imageView)
      addConstrains()
    }
  }

  /// Customize the toggle button icon of the cell
  func setCustomToggleButton() {
    // Render the icon images as templates so they can be tinted.
    let bundle = Bundle(for: ToggleButtonCell.self)
    let selectedIcon = UIImage(named: "ic_favorite_24dp", in: bundle, compatibleWith: nil)?
      .withRenderingMode(.alwaysTemplate)
    let unselectedIcon = UIImage(named: "ic_favorite_border_24dp", in: bundle, compatibleWith: nil)?
      .withRenderingMode(.alwaysTemplate)

    // Set the toggle button image and tint color.
    setImage(selectedIcon, for: .selected)
    setImage(unselectedIcon, for: .normal)
  }

  func addConstrains() {
    if #available(iOS 11, *) {
      NSLayoutConstraint.activate([
        contentView.leftAnchor.constraint(equalTo: imageView.leftAnchor),
        contentView.rightAnchor.constraint(equalTo: imageView.rightAnchor),
        contentView.topAnchor.constraint(equalTo: imageView.topAnchor),
        contentView.bottomAnchor.constraint(equalTo: imageView.bottomAnchor)
      ])
    } else {
      preiOS11Constraints()
    }
  }

  func preiOS11Constraints() {
    imageView.addConstraints(
      NSLayoutConstraint.constraints(
        withVisualFormat: "H:|[view]|",
        options: [],
        metrics: nil,
        views: ["view": contentView]))
    imageView.addConstraints(
      NSLayoutConstraint.constraints(
        withVisualFormat: "V:|[view]|",
        options: [],
        metrics: nil,
        views: ["view": contentView]))
  }
}
```

The class `ToggleButtonCollectionViewController` &ndash; which extends `UICollectionViewController` &ndash; loads the images and icons in a list:

```swift
class ToggleButtonCollectionViewController: UICollectionViewController,
  UICollectionViewDelegateFlowLayout
{

  fileprivate let layout = UICollectionViewFlowLayout()
  @objc var containerScheme: MDCContainerScheming
  let padding: CGFloat = 8

  var dataSource = [
    (image: "toggle-button-image1", accessibilityLabel: "Teapot", selected: false),
    (image: "toggle-button-image4", accessibilityLabel: "Vases", selected: true),
    (image: "toggle-button-image3", accessibilityLabel: "Tape", selected: true),
    (image: "toggle-button-image2", accessibilityLabel: "Cup", selected: false),
    (image: "toggle-button-image1", accessibilityLabel: "Teapot", selected: false),
    (image: "toggle-button-image4", accessibilityLabel: "Vases", selected: false),
    (image: "toggle-button-image3", accessibilityLabel: "Tape", selected: false),
    (image: "toggle-button-image2", accessibilityLabel: "Cup", selected: false),
  ]

  init() {
    let layout = UICollectionViewFlowLayout()
    layout.minimumLineSpacing = padding
    layout.minimumInteritemSpacing = padding
    layout.sectionInset = UIEdgeInsets(top: padding, left: padding, bottom: padding, right: padding)

    containerScheme = MDCContainerScheme()

    super.init(collectionViewLayout: layout)
  }

  required init?(coder aDecoder: NSCoder) {
    fatalError("init(coder:) has not been implemented")
  }

  override func viewDidLoad() {
    super.viewDidLoad()

    collectionView.register(
      ToggleButtonCell.self, forCellWithReuseIdentifier: String(describing: ToggleButtonCell.self))
    collectionView.allowsMultipleSelection = true
    collectionView.backgroundColor = containerScheme.colorScheme.surfaceColor

    self.title = "Cards Toggle Button"
  }

  override func viewWillTransition(
    to size: CGSize, with coordinator: UIViewControllerTransitionCoordinator
  ) {
    super.viewWillTransition(to: size, with: coordinator)
    // Recalculate cell size when orientation changes
    collectionView.collectionViewLayout.invalidateLayout()
  }
}
```

The class `ToggleButtonCollectionViewController` can then be instantiated to display each image with an icon in an array:

```swift
// MARK: UICollectionViewDataSource

extension ToggleButtonCollectionViewController {

  override func numberOfSections(in collectionView: UICollectionView) -> Int {
    return 1
  }

  override func collectionView(
    _ collectionView: UICollectionView, numberOfItemsInSection section: Int
  ) -> Int {
    return dataSource.count
  }

  override func collectionView(
    _ collectionView: UICollectionView, cellForItemAt indexPath: IndexPath
  ) -> UICollectionViewCell {

    // Get our custom cell, which is a card cell subclass, with a custom toggle icon.
    let cell = collectionView.dequeueReusableCell(
      withReuseIdentifier: String(describing: ToggleButtonCell.self), for: indexPath)
    guard let cardCell = cell as? ToggleButtonCell else { return cell }

    // Get the card cell's data from the data source.
    let imagedata = dataSource[indexPath.item]

    // Set the card's image based on the datasource.
    cardCell.setCardImage(named: imagedata.image)

    // Apply the Material theme to the cards, which uses the primary color to theme the toggle
    // button color. In this example, we've overriden it with a white color.
    cardCell.applyTheme(withScheme: containerScheme)
    cardCell.setImageTintColor(.white, for: .normal) // Override the default toggle color.

    // Enable toggle button behavior in the card.
    cardCell.isSelectable = true

    // Select the card based on its state in the data source.
    cardCell.isSelected = imagedata.selected
    if imagedata.selected {
      collectionView.selectItem(at: indexPath, animated: true, scrollPosition: [])
    }

    // Ensure the card is accessible.
    cardCell.isAccessibilityElement = true
    cardCell.accessibilityLabel = imagedata.accessibilityLabel
    return cardCell
  }
}

// MARK: UICollectionViewDelegate

extension ToggleButtonCollectionViewController {

  override func collectionView(
    _ collectionView: UICollectionView, didSelectItemAt indexPath: IndexPath
  ) {
    dataSource[indexPath.item].selected = true
  }

  override func collectionView(
    _ collectionView: UICollectionView, didDeselectItemAt indexPath: IndexPath
  ) {
    dataSource[indexPath.item].selected = false
  }

  func collectionView(
    _ collectionView: UICollectionView,
    layout collectionViewLayout: UICollectionViewLayout,
    sizeForItemAt indexPath: IndexPath
  ) -> CGSize {
    let cardWidth = (collectionView.bounds.size.width - padding * 3) / 2
    return CGSize(width: cardWidth, height: cardWidth)
  }
}

// MARK: Catalog By convention

extension ToggleButtonCollectionViewController {

  @objc class func catalogMetadata() -> [String: Any] {
    return [
      "breadcrumbs": ["Cards", "Toggle Button in Cards"],
      "primaryDemo": false,
      "presentable": true,
    ]
  }
}
```

#### Anatomy and key properties

The icon button consists of two icons for 'on' and 'off'

**Icon button**
* C Icon


Diagram label | Design Attribute |  Theme value |  Property
---|---|---|---
C | Icon | N/A | 
C | Icon color | Secondary color |  

.

<details>
<summary><b>Text label</b> attributes</summary>
<br>

|  | Attribute | Related method(s) | Default value |
| --- | --- | --- | --- |
| **Text label** | | | |
| **Color** |  | | |
| **Typography** | | | |


</details>

<details>
<summary><b>Container</b> attributes</summary>
<br>

|  | Attribute | Related method(s) | Default value |
| --- | --- | --- | --- |
| **Color** | | | |
| **Stroke color** | | | |
| **Stroke width** || | |
| **Shape** | | | |
| **Elevation** | | | |
| **Ripple color** | | | |

</details>

<details>
<summary><b>Icon</b> attributes</summary>
<br>

|  | Attribute | Related method(s) | Default value |
| --- | --- | --- | --- |
| **Icon** | | | |
| **Color** || | |
| **Size** | | | |
| **Gravity** (position relative to text label) | | | |
| **Padding** (space between icon and text label) | | | |

</details>



## Theming buttons

Buttons support [Material Theming](https://material.io/components/buttons/#theming) and can be customized in terms of color, typography and shape.

### Button theming example

API and source code:

* `MaterialButton`
    * [Class description](https://)
    * [GitHub source](https://github.com/material-components/)
    
The following example shows text, outlined and contained button types with Material Theming.

!["Button theming example for <platform> with three buttons - text, outlined and contained - with green/black color theming and cut corners."](assets/button-theming.svg)

<details>
<summary><b>Implementing button theming</b></summary>
<br>

```
Include source code implementing the three buttons found in [https://github.com/mingjane-work/doc-material-components/blob/mingjane-doc-branch/button-examples/Android/android-button-example.md#theming-buttons].

Upload a screenshot of the render and update the image.
```

</details>
