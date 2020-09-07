---
layout: post
title: AutoSize | SfRichTextEditor | Xamarin | Syncfusion
description: This page explains how to use the AutoSize feature in the Syncfusion Rich Text Editor for Xamarin.Forms platform.
platform: xamarin
control: Rich Text Editor
documentation: ug
---

# AutoSize in Xamarin Rich Text Editor (SfRichTextEditor)

The Xamarin Rich Text Editor control provides support to dynamically change the height of the control based on the input text's height. This feature can be enabled by setting the `AutoSizeOption.TextChanges` to [`AutoSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html#Syncfusion_XForms_RichTextEditor_SfRichTextEditor_AutoSize) property. By default, AutoSize feature will be disabled in RichTextEditor. The following code example shows how to enable AutoSize in Rich Text Editor control.

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

AutoSize feature in the Xamarin Rich Text Editor control can be controlled by setting the [`MaximumHeightRequest`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html#Syncfusion_XForms_RichTextEditor_SfRichTextEditor_MaximumHeightRequest) and [`MinimumHeightRequest`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html#Syncfusion_XForms_RichTextEditor_SfRichTextEditor_MinimumHeightRequest) properties. The following code example shows how to set the MaximumHeightRequest and MinimumHeightRequest for RichTextEditor control.

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

N> AutoSize will not be working when the application is in `AdjustResize` SoftInputMode.

## Limitations in AutoSize

 1. AutoFocus will not be working in the Xamarin RichTextEditor iOS.
 2. Extra spaces will be added in the bottom of the RichTextEditor control in iOS platform.
 3. Focus and UnFocus events will not triggered programmatically until the RichTextEditor is manually focused in the Xamarin RichTextEditor iOS.
 4. Custom toolbar will not working in the Xamarin RichTextEditor iOS because the control selection will be lost when clicking the elements in the custom toolbar.
 5. RichTextEditor will not rendered in the XAML Previewer for RichTextEditor(all platforms).
 6. Toolbar will be hidden when the `MaximumHeightRequest` is beyond the keyboard region.