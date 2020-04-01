---
layout: post
title: Overview of Syncfusion Xamarin.Forms Rich Text Editor
description: What are the key features available in Syncfusion Rich Text Editor control for Xamarin.Forms platform.
platform: xamarin
control: Rich Text Editor
documentation: ug
---

# Overview

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
 2. RichTextEditor will not rendered in the XAML Previewer for RichTextEditor. 
 3. To avoid rendering of the RichTextEditor out of the screen, it is highly recommended to set the `MaximumHeightRequest` property when the `AutoSize` is enabled.
 4. Toolbar will be hidden when the `MaximumHeightRequest` is beyond the keyboard region. 

### Android
 1. By default, AutoFocus is disabled in the RichTextEditor Android. To enable this, the `SoftInputMode` must be set in MainActivity.cs as mentioned in our [`GettingStarted`](https://help.syncfusion.com/xamarin/rich-text-editor/gettingstarted#android) page.
 2. AutoFocus will be triggered only when typing the content in the RichTextEditor.
 
### iOS
 1. AutoFocus will not be working when `AutoSize` is enabled.
 2. Extra spaces will be added in the bottom of the RichTextEditor control.
 3. Focus and UnFocus events will not triggered programatically until RichTextEditor is manually focused.
 4. Custom toolbar will not working in the Xamarin RichTextEditor iOS because the control selection will be lost when clicking the elements in the custom toolbar.
 
### UWP
 1. ScrollBar will be visible by default.
