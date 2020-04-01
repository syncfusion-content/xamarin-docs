---
layout: post
title: AutoSize | SfRichTextEditor | Xamarin | Syncfusion
description: This page explains how to use the AutoSize feature in Syncfusion Rich Text Editor for Xamarin.Forms platform.
platform: xamarin
control: Rich Text Editor
documentation: ug
---

# AutoSize

The Xamarin Rich Text Editor control provides support to dynamically the height of the control based on input text's height. This feature can be enabled by setting `AutoSizeOption.TextChanges` to [`AutoSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRichTextEditor.XForms~Syncfusion.XForms.RichTextEditor.SfRichTextEditor~AutoSize.html) property. By default, AutoSize feature will be disabled in RichTextEditor. The following code example shows how to enable AutoSize in Rich Text Editor control.

{% tabs %} 

{% highlight xaml %} 

 <richtexteditor:SfRichTextEditor AutoSize="TextChanges" />

{% endhighlight %}

{% highlight C# %} 
richtexteditor = new SfRichTextEditor()
{
	AutoSize = AutoSizeOption.TextChanges
};
this.Content = richtexteditor;
{% endhighlight %}

{% endtabs %}

## MaximumHeightRequest and MinimumHeightRequest

AutoSize feature in Xamarin Rich Text Editor control can be controlled by setting [`MaximumHeightRequest`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfRichTextEditor.XForms~Syncfusion.XForms.RichTextEditor.SfRichTextEditor~MaximumHeightRequest.html) and [`MinimumHeightRequest`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfRichTextEditor.XForms~Syncfusion.XForms.RichTextEditor.SfRichTextEditor~MinimumHeightRequest.html) property. The following code example shows how to set MaximumHeightRequest and MinimumHeightRequest for RichTextEditor control.

{% tabs %} 

{% highlight xaml %} 

 <richtexteditor:SfRichTextEditor AutoSize="TextChanges" MaximumHeightRequest="500" MinimumHeightRequest="250" />

{% endhighlight %}

{% highlight C# %} 
richtexteditor = new SfRichTextEditor()
{
	AutoSize = AutoSizeOption.TextChanges,
	MaximumHeightRequest = 500,
	MinimumHeightRequest = 250
};
this.Content = richtexteditor;
{% endhighlight %}

{% endtabs %}

## Limitations in AutoSize

 1. AutoFocus will not be working in Xamarin RichTextEditor iOS.
 2. Extra spaces will be added in the bottom of the RichTextEditor control in iOS platform.
 3. Focus and UnFocus events will not triggered programatically until RichTextEditor is manually focused in Xamarin RichTextEditor iOS.
 4. Custom toolbar will not working in Xamarin RichTextEditor iOS since the control selection will be lost while the clicking the elements in custom toolbar.
 5. RichTextEditor will not rendered in XAML Previewer for RichTextEditor(all platforms).
 6. Toolbar will be hidden when the `MaximumHeightRequest` is beyond the keyboard region.
 
## Limitations

### All platform
 1. RichTextEditor scroll view will not be working if the control is placed inside a ScrollView.
 2. RichTextEditor will not rendered in XAML Previewer for RichTextEditor. 
 3. To avoid rendering of RichTextEditor out of the screen, it is highly recommended to set `MaximumHeightRequest` property when `AutoSize` is enabled.
 4. Toolbar will be hidden when the `MaximumHeightRequest` is beyond the keyboard region. 

### Android
 1. By default, AutoFocus is disabled in RichTextEditor Android. To enable this, `SoftInputMode` must be set in MainActivity.cs as mentioned in our [`GettingStarted`](https://help.syncfusion.com/xamarin/rich-text-editor/gettingstarted#android) page.
 2. AutoFocus will be triggered only when typing the content in the RichTextEditor.
 
### iOS
 1. AutoFocus will not be working when `AutoSize` is enabled.
 2. Extra spaces will be added in the bottom of the RichTextEditor control.
 3. Focus and UnFocus events will not triggered programatically until RichTextEditor is manually focused.
 4. Custom toolbar will not working in Xamarin RichTextEditor iOS since the control selection will be lost while the clicking the elements in custom toolbar.
 
### UWP
 1. ScrollBar will be visible by default.
