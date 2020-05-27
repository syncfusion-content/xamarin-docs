---
layout: post
title: Overview of Syncfusion Xamarin.Forms Rich Text Editor
description: What are the key features available in Syncfusion Rich Text Editor control for Xamarin.Forms platform.
platform: xamarin
control: Rich Text Editor
documentation: ug
---

# Xamarin Rich Text Editor (SfRichTextEditor) Overview

The Xamarin Rich Text Editor control is a WYSIWYG editor that provides a great user experience for composing or editing rich text content from your Xamarin.Forms applications. Users can format their content using the standard toolbar commands.

## Key features

* Applies formatting such as bold, italics, and underline.
* Applies font color and background color to the content.
* Customizes the text size and selection.
* Creates bulleted and numbered lists.
* Allows hyperlink manipulations such as create, edit, and remove hyperlink.
* Allows Undo and Redo editing action in Xamarin.Forms UWP.

![Overview of Rich Text Editor](SfRichTextEditor_Images/Overview.gif)

## Limitations

### All platform
 1. RichTextEditor scroll view will not be working if the control is placed inside a ScrollView.
 2. To avoid rendering of the RichTextEditor out of the screen, it is highly recommended to set the `MaximumHeightRequest` property when the `AutoSize` is enabled.
 3. Toolbar will be hidden when the `MaximumHeightRequest` is beyond the keyboard region. 

### iOS
 1. AutoFocus will not be working when `AutoSize` is enabled.
 2. Extra spaces will be added in the bottom of the RichTextEditor when the control is AutoSizing.
 3. Focus and UnFocus events will not triggered programmatically until RichTextEditor is manually focused.
 4. Custom toolbar will not working in the Xamarin RichTextEditor iOS because the control selection will be lost when clicking the elements in the custom toolbar.
 
### UWP
 1. ScrollBar will be visible by default.
