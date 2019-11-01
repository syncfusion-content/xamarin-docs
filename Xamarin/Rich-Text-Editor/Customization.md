---
layout: post
title: Customization of Syncfusion Xamarin.Forms Rich Text Editor
description: This page explains how to customize the appearance of Syncfusion Rich Text Editor for Xamarin.Forms platform.
platform: xamarin
control: Rich Text Editor
documentation: ug
---

# Customization of Rich Text Editor

The Xamarin Rich Text Editor control provides support for customizing the toolbar items and toolbar appearance.

## ToolbarOptions

The [`ToolbarOptions`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRichTextEditor.XForms~Syncfusion.XForms.RichTextEditor.SfRichTextEditor~ToolbarOptions.html) property of [`SfRichTextEditor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRichTextEditor.XForms~Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html) is used to change the toolbar items presented in Toolbar. The following different toolbar items are available in [`SfRichTextEditor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRichTextEditor.XForms~Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html).

* `Alignment`	
* `Bold`
* `BulletList`	
* `ClearFormat`
* `DecreaseIndent`
* `FontColor`
* `FontSize`
* `HighlightColor`
* `IncreaseIndent`
* `Italic`
* `NumberList`
* `ParagraphFormat`
* `Underline`
* `All` - default

{% tabs %} 

{% highlight xaml %} 

         <richtexteditor:SfRichTextEditor x:Name="richtexteditor" VerticalOptions="FillAndExpand" ToolbarOptions="Bold,FontColor,NumberList" Text= "The Xamarin Rich Text Editor control is a WYSIWYG editor that provides a great user experience for composing or editing rich text content from your Xamarin.Forms applications." />
       

{% endhighlight %}

{% highlight C# %} 
		richtexteditor = new SfRichTextEditor()
		{
			VerticalOptions = LayoutOptions.FillAndExpand,
			ToolbarOptions = ToolbarOptions.Bold| ToolbarOptions.FontColor| ToolbarOptions.NumberList,
			Text = "The Xamarin Rich Text Editor control is a WYSIWYG editor that provides a great user experience for composing or editing rich text content from your Xamarin.Forms applications.",
		};
		this.Content = richtexteditor;

{% endhighlight %}

{% endtabs %}

## Customizing Toolbar

The appearance of toolbar can be customized. [`BackgroundColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfRichTextEditor.XForms~Syncfusion.XForms.RichTextEditor.ToolbarSettings~BackgroundColor.html) , [`TextColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfRichTextEditor.XForms~Syncfusion.XForms.RichTextEditor.ToolbarSettings~TextColor.html) and [`ToolbarBackgroundColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfRichTextEditor.XForms~Syncfusion.XForms.RichTextEditor.ToolbarSettings~ToolbarBackgroundColor.html) properties helps to change the background color of toolbar item, text color of toolbar item and background color of toolbar respectively. The following code example illustrates how to customize the toolbar appearance.

{% tabs %} 

{% highlight xaml %} 
	    <richtexteditor:SfRichTextEditor x:Name="richtexteditor" VerticalOptions="FillAndExpand">
            <richtexteditor:SfRichTextEditor.ToolbarSettings>
                <richtexteditor:ToolbarSettings BackgroundColor="Orange" ToolbarBackgroundColor="DarkBlue" TextColor="DarkBlue"/>
            </richtexteditor:SfRichTextEditor.ToolbarSettings>
        </richtexteditor:SfRichTextEditor>      
{% endhighlight %}

{% highlight C# %} 

		richtexteditor = new SfRichTextEditor();
		richtexteditor.VerticalOptions = LayoutOptions.FillAndExpand;
		richtexteditor.ToolbarSettings.BackgroundColor = Color.Orange;
		richtexteditor.ToolbarSettings.TextColor = Color.DarkBlue;
		richtexteditor.ToolbarSettings.ToolbarBackgroundColor = Color.DarkBlue;
		this.Content = richtexteditor;

{% endhighlight %}

{% endtabs %}