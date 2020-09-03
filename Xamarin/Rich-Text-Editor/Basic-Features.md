---
layout: post
title: Basic features in Syncfusion Xamarin.Forms Rich Text Editor
description: This page explains how to basic features available in Syncfusion Rich Text Editor for Xamarin.Forms platform.
platform: xamarin
control: Rich Text Editor
documentation: ug
---

# Basic Features

## Setting Text

The Xamarin Rich Text Editor control displays the text/formatted text(HTML string) that can be set using the [`Text`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html#Syncfusion_XForms_RichTextEditor_SfRichTextEditor_Text) property.

{% tabs %} 

{% highlight xaml %} 

 <richtexteditor:SfRichTextEditor VerticalOptions="FillAndExpand" Text= "The &lt;b&gt; rich text editor &lt;/b&gt; component is WYSIWYG editor that provides the best user experience to create and update the content" />

{% endhighlight %}

{% highlight C# %} 
richtexteditor = new SfRichTextEditor()
{
	VerticalOptions = LayoutOptions.FillAndExpand,			
	Text = "The <b>rich text editor</b> component is WYSIWYG editor that provides the best user experience to create and update the content";
};
this.Content = richtexteditor;
{% endhighlight %}

{% endtabs %}

## Retrieving HTML text

The formatted text of Rich Text Editor can be retrieved using [`GetHtmlString`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html#Syncfusion_XForms_RichTextEditor_SfRichTextEditor_GetHtmlString) method of [`SfRichTextEditor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html).

{% tabs %} 

{% highlight C# %} 

string HTMLText = richtexteditor.GetHtmlString();

{% endhighlight %}

{% endtabs %}