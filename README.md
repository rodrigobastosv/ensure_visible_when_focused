<a href="https://www.buymeacoffee.com/rodrigobastosv" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>

#  Introduction

I was having a hard time scrolling to a specific wdget in a scenario where I had a very large form, with lots of form fields.

I found an issue with no concrete answer https://github.com/flutter/flutter/issues/58877

After digging a litlle deeper I found a solution to this problem https://www.didierboelens.com/2018/04/hint-4 -ensure-a-textfield-or-textformfield-is-visible-in-the-viewport-when-has-the-focus/. Hence the idea of ​​creating and making this widget available.

This widget solves this problem in a very elegant way. You just have to give the same FocusNode of the widget you want to scroll to.

# Basic Usage

The widget is very simple to use. You need to Wrap your widget on a EnsureVisibleWhenFocused widget. You have to pass the FocusNode of the widget you want to scroll to when it's given focus.

```dart
EnsureVisibleWhenFocused(
    focusNode: _focusNode,
    child: TextFormField(
        focusNode: _focusNode,
    ),
)
```

With the setup above, every time the TextFormField gains focus, a scroll will be made to it.

You can give focus to a field just doing:

```dart
_focusNode.requestFocus();
```

You can configure more things, such as the scroll duration and it's curve.

![enter image description here](https://media1.giphy.com/media/63pHOXkQZLhMD9s4NY/giphy.gif?cid=790b7611a6634a28eb0164655dc1697efcdf82c23a6f9a3a&rid=giphy.gif&ct=g)

## Suggestions & Bugs

For any suggestions or bug report please head to [issue tracker][tracker].

[tracker]: https://github.com/rodrigobastosv/ensure_visible_when_focused/issues
