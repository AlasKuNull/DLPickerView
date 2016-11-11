# DLPickerView

 `DLPickerView`'s usage is the same as `UIPickerView`, you can use it to replace `UIPickerView` and it works as if you are still using `UIPickerView`. But instead of just like `UIPickerView`, I make `DLPickerView` more easy to custom and add many new features to it. In other words, **I define `UIPickerView` once again.**

<p align="center"><img src ="./Demo.gif" /></p>

# Features

 `DLPickerView` has these features that `UIPickerView` doesn't have:

 1. You can make a component scroll cyclically, which means the bottom cell follows by the beginning cell, and the beginning cell is after the bottom cell. And this is not a fake effect, it is really scroll cyclically.
 2. You can make a component scroll within a specific range. And user can't scroll or select the cell out of the range.
 3. You can make a different layout of components, for example, components can be listed vertically, not only horizontally.
 4. You can use `DLPickerView` like `UITableView`, and just inherit `DLPickerViewCell` to implement your own customized cell class.
 5. You can disable the scroll sound effect if you want, and you can also custom the scroll sound effect.
 6. You can custom the scrol effect, so it scrolls not only like wheel, but can also be the style you want. And make some visual effects to the cell based on the cell's position.
 7. You can adjust the scale value of center indicator view by setting `magnifyingViewScale` or implement method in `DLPickerViewDelegate`.
 8. You can set night mode if you want.
 9. You can make a component has infinite rows and memory usage is really small
 10. If you have some other ideas about the `DLPickerView`, please let me know.

# Some using advices
 
 1. If you change some properties, make sure to invoke `reloadComponent` or `reloadAllComponent` methods.
 2. If you use different row height for a component, be sure to set `showsSelectionIndicator` to false, because it will look better.
 3. The custom indicator view for different components has not been currently finished developing, and I am think about how many people want this? I think system-provide-style is good enough.
 4. When you add `DLPickerView` to the `ViewController`'view, sometime you should set `automaticallyAdjustsScrollViewInsets` to false, if the appearance doesn't show right.
 5. I will be very grateful if someone reports bugs to me.

# How do I implement `DLPickerView`

If you read the source code, you will notice that `DLPickerView` is based on `DLTableView`. Yes, in order to implement `DLPickerView`, I also re-implement `UITableView` based on `UIScrollView` which is called `DLTableView`. `DLTableView` doesn't fully support API like `UITableView` and `DLTableView` has no section header and footer. But `DLTableView` also has many features that `UITabelView` doesn't have. And I think `DLTableView` can be used in most cases. Check it if you are interested in this class. And I will continue to improve `DLTableView`, make its usage like `UITableView` and has features that `UITableView` doesn't have.

Implement `DLPickerView` is really simple based on `DLTabelView`. 

## Requirements

It requires `Xcode` 8.0+ and `Swift` 3.0.

Your project deployment target must be `iOS 8.0+`

## Installation

You can use it manually just draging [`DLPickerView`](https://github.com/danleechina/DLPickerView/master/) file to your project. Because it was writted by `Swift`, if you are using `Objective C`, make sure to add bridge file to your project.

## Usage

Clone the repo. Click `DLPickerView.xcodeproj` file to launch `Xcode`.

```
let cyclePickerView = DLPickerView()
cyclePickerView.delegate = self
cyclePickerView.dataSource = self
cyclePickerView.frame = CGRect(x: 10, y: 70, width: self.view.frame.width - 20, height: self.view.frame.width - 20)
cyclePickerView.reloadAllComponents()
self.view.addSubview(cyclePickerView)

```

You should implement `DLPickerViewDataSource` and `DLPickerViewDelegate`

1. `DLPickerViewDataSource` is the same as `DLPickerViewDataSource `.

2. `DLPickerViewDelegate` has all the methods that `UIPickerViewDelegate` provided. And it also has many other methods that `UIPickerViewDelegate` doesn't have. And I wrote many comments before every method, read these when you want to know how to implement `DLPickerViewDelegate`. Checkout these methods if you want a different picker view.

3. Please also checkout out the public properties of `DLPickerView`. These properties are also like `UIPickerView` provided for us, but I add some other properties to make customing picker view more convenient and more customizable.



## Contributors

Author: [@粉碎音箱的音乐(weibo)](http://weibo.com/u/1172595722) 

Blog: [Blog](http://danleechina.github.io/)

## Starring is caring

Please star if you think it is helpful to you. Thank you. 😄
