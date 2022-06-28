---
layout: post
title: Customization in Xamarin Rich Text Editor control | Syncfusion
description: Learn here all about Customization support in Syncfusion Xamarin Rich Text Editor (SfRichTextEditor) control and more.
platform: xamarin
control: Rich Text Editor
documentation: ug
---

# Customization in Xamarin Rich Text Editor (SfRichTextEditor)

The Xamarin Rich Text Editor control provides support for customizing the toolbar items and toolbar appearance.

## ToolbarOptions

The [`ToolbarOptions`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html#Syncfusion_XForms_RichTextEditor_SfRichTextEditor_ToolbarOptions) property of [`SfRichTextEditor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html) is used to change the toolbar items presented in the toolbar. The following different toolbar items are available in [`SfRichTextEditor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html):

* `Alignment`	
* `Bold`
* `BulletList`	
* `ClearFormat`
* `DecreaseIndent`
* `Font`
* `FontColor`
* `FontSize`
* `HighlightColor`
* `Hyperlink`
* `IncreaseIndent`
* `Italic`
* `NumberList`
* `ParagraphFormat`
* `Redo`
* `Strikethrough`
* `SubScript`
* `SuperScript`
* `Underline`
* `Undo`
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

## Customizing toolbar

The appearance of the toolbar can be customized. The [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.ToolbarSettings.html#Syncfusion_XForms_RichTextEditor_ToolbarSettings_BackgroundColor), [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.ToolbarSettings.html#Syncfusion_XForms_RichTextEditor_ToolbarSettings_TextColor), and [`ToolbarBackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.ToolbarSettings.html#Syncfusion_XForms_RichTextEditor_ToolbarSettings_ToolbarBackgroundColor) properties helps to change the background color, text color of toolbar item, and background color of toolbar respectively. The following code example explains how to customize the toolbar appearance.

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

## Placeholder

Specifies the placeholder for the RichTextEditor’s content, which is displayed when the RichTextEditor text is empty. The following code example explains how to set a placeholder for Rich Text Editor.

{% tabs %} 

{% highlight xaml %} 
<StackLayout>
	<richtexteditor:SfRichTextEditor VerticalOptions="FillAndExpand" PlaceHolder="Type something"/>
</StackLayout>   
{% endhighlight %}

{% highlight C# %} 
richtexteditor = new SfRichTextEditor();
richtexteditor.VerticalOptions = LayoutOptions.FillAndExpand;
richtexteditor.PlaceHolder="Type something";
this.Content = richtexteditor;
{% endhighlight %}

{% endtabs %}
![Placeholder in Rich Text Editor](SfRichTextEditor_Images/Placeholder.png)

## Placeholder Customization

The placeholder style can be customized using the properties PlaceHolderFontColor, PlaceHolderFontSize, and PlaceHolderFontFamily.

N> The PlaceHolderFontFamily property accepts fonts as Embedded source, System Font Name, or Base64 TTF string.

{% tabs %} 

{% highlight xaml %} 
<StackLayout>
	<richtexteditor:SfRichTextEditor VerticalOptions="FillAndExpand" PlaceHolder="Type something" PlaceHolderFontColor="Red" PlaceHolderFontSize="30" PlaceHolderFontFamily="cursive"/>
</StackLayout>   
{% endhighlight %}

{% highlight C# %} 
richtexteditor = new SfRichTextEditor();
richtexteditor.VerticalOptions = LayoutOptions.FillAndExpand;
richtexteditor.PlaceHolder="Type something";
richtexteditor.PlaceHolderFontColor="Red";
richtexteditor.PlaceHolderFontSize="30";
richtexteditor.PlaceHolderFontFamily="cursive";
this.Content = richtexteditor;
{% endhighlight %}

{% endtabs %}

## Read-only support

Rich Text Editor provides read-only support, which allows the users to restrict editing. Rich Text Editor can be used as HTML Viewer using this feature. The following code example explains how to set read-only mode in Rich Text Editor.

{% tabs %} 

{% highlight xaml %} 
<StackLayout>
   <richtexteditor:SfRichTextEditor VerticalOptions="FillAndExpand" ReadOnly="True" />
</StackLayout>   
{% endhighlight %}

{% highlight C# %} 
richtexteditor = new SfRichTextEditor();
richtexteditor.VerticalOptions = LayoutOptions.FillAndExpand;
richtexteditor.ReadOnly=true;
this.Content = richtexteditor;
{% endhighlight %}

{% endtabs %}

## ToggleBold

Rich Text Editor provides ['ToggleBold'](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html#Syncfusion_XForms_RichTextEditor_SfRichTextEditor_ToggleBold) support, which allows the users to toggle the text in bold format. The following code example explains how to set ToggleBold mode in Rich Text Editor.

{% tabs %}
{% highlight C# %} 
richtexteditor = new SfRichTextEditor();
richtexteditor.VerticalOptions = LayoutOptions.FillAndExpand;
richtexteditor.ToggleBold();
this.Content = richtexteditor;
{% endhighlight %}

{% endtabs %}

## ToggleBulletList

Rich Text Editor provides ['ToggleBulletList'](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html#Syncfusion_XForms_RichTextEditor_SfRichTextEditor_ToggleBulletList) support, which allows the users to toggle the text in bullet format. The following code example explains how to set ToggleBulletList mode in Rich Text Editor.

{% tabs %}
{% highlight C# %} 
richtexteditor = new SfRichTextEditor();
richtexteditor.VerticalOptions = LayoutOptions.FillAndExpand;
richtexteditor.ToggleBulletList();
this.Content = richtexteditor;
{% endhighlight %}

{% endtabs %}

## ToggleItalic

Rich Text Editor provides ['ToggleItalic'](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html#Syncfusion_XForms_RichTextEditor_SfRichTextEditor_ToggleItalic) support, which allows the users to toggle the text in italic format. The following code example explains how to set ToggleItalic mode in Rich Text Editor.

{% tabs %}
{% highlight C# %} 
richtexteditor = new SfRichTextEditor();
richtexteditor.VerticalOptions = LayoutOptions.FillAndExpand;
richtexteditor.ToggleItalic();
this.Content = richtexteditor;
{% endhighlight %}

{% endtabs %}

## ToggleNumberedList

Rich Text Editor provides ['ToggleNumberedList'](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html#Syncfusion_XForms_RichTextEditor_SfRichTextEditor_ToggleNumberedList) support, which allows the users to toggle the text in numbered list format. The following code example explains how to set ToggleNumberedList mode in Rich Text Editor.

{% tabs %}
{% highlight C# %} 
richtexteditor = new SfRichTextEditor();
richtexteditor.VerticalOptions = LayoutOptions.FillAndExpand;
richtexteditor.ToggleNumberedList();
this.Content = richtexteditor;
{% endhighlight %}

{% endtabs %}

## ToggleSubScript

Rich Text Editor provides ['ToggleSubScript'](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html#Syncfusion_XForms_RichTextEditor_SfRichTextEditor_ToggleSubScript) support, which allows the users to toggle the selected text as sub script format. The following code example explains how to set ToggleSubScript mode in Rich Text Editor.

{% tabs %}
{% highlight C# %} 
richtexteditor = new SfRichTextEditor();
richtexteditor.VerticalOptions = LayoutOptions.FillAndExpand;
richtexteditor.ToggleSubScript();
this.Content = richtexteditor;
{% endhighlight %}

{% endtabs %}

## ToggleSuperScript

Rich Text Editor provides ['ToggleSuperScript'](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html#Syncfusion_XForms_RichTextEditor_SfRichTextEditor_ToggleSuperScript) support, which allows the users to toggle the selected text as super script format. The following code example explains how to set ToggleSuperScript mode in Rich Text Editor.

{% tabs %}
{% highlight C# %} 
richtexteditor = new SfRichTextEditor();
richtexteditor.VerticalOptions = LayoutOptions.FillAndExpand;
richtexteditor.ToggleSuperScript();
this.Content = richtexteditor;
{% endhighlight %}

{% endtabs %}

## ToggleUnderline

Rich Text Editor provides ['ToggleUnderline'](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html#Syncfusion_XForms_RichTextEditor_SfRichTextEditor_ToggleUnderline) support, which allows the users to toggle the text in underline format. The following code example explains how to set ToggleUnderline mode in Rich Text Editor.

{% tabs %}
{% highlight C# %} 
richtexteditor = new SfRichTextEditor();
richtexteditor.VerticalOptions = LayoutOptions.FillAndExpand;
richtexteditor.ToggleUnderline();
this.Content = richtexteditor;
{% endhighlight %}

{% endtabs %}

## ToggleStrikethrough

Rich Text Editor provides ['ToggleStrikethrough'] support, which allows the users to toggle the text in Strikethrough format. The following code example explains how to set ToggleStrikethrough mode in Rich Text Editor.

{% tabs %}
{% highlight C# %} 
richtexteditor = new SfRichTextEditor();
richtexteditor.VerticalOptions = LayoutOptions.FillAndExpand;
richtexteditor.ToggleStrikethrough();
this.Content = richtexteditor;
{% endhighlight %}

{% endtabs %}


## ToolbarPosition

Rich Text Editor provides the support to switch the position of a toolbar to the top or bottom of the screen. The following code example explains how to switch the toolbar position in the Rich Text Editor.

{% tabs %} 

{% highlight xaml %} 
<StackLayout>
   <richtexteditor:SfRichTextEditor VerticalOptions="FillAndExpand" ToolbarPosition="Top" />
</StackLayout>   
{% endhighlight %}

{% highlight C# %} 
richtexteditor = new SfRichTextEditor();
richtexteditor.VerticalOptions = LayoutOptions.FillAndExpand;
richtexteditor.ToolbarPosition = Syncfusion.XForms.RichTextEditor.ToolbarPosition.Top;
this.Content = richtexteditor;
{% endhighlight %}

{% endtabs %}

## Custom Toolbar

The Rich Text Editor provides a custom toolbar support, which allows the users to add custom toolbar items to the toolbar in the editor. The following code example explains how to set custom toolbar in Rich Text Editor.

{% tabs %} 

{% highlight C# %} 
SfRichTextEditor richTextEditor = new SfRichTextEditor();
richTextEditor.PlaceHolder = "Type something";
ObservableCollection<object> collection = new ObservableCollection<object>();
collection.Add(ToolbarOptions.Bold);
collection.Add(ToolbarOptions.Italic);
collection.Add(ToolbarOptions.Underline);
collection.Add(ToolbarOptions.NumberList);
collection.Add(ToolbarOptions.BulletList);
Button emojiButton = new Button();
emojiButton.BackgroundColor = Color.Transparent;
emojiButton.HeightRequest = 50;
emojiButton.WidthRequest = 50;
emojiButton.Text = "\U0001F642";
collection.Add(emojiButton);
richTextEditor.ToolbarItems = collection;
this.Content = richTextEditor;
{% endhighlight %}

{% endtabs %}

![Rich Text Editor custom toolbar support](SfRichTextEditor_Images/CustomToolbar.png)

N> The custom toolbar will not support the sub toolbar in the Xamarin RichTextEditor iOS because the control selection will be lost when clicking the elements in the sub toolbar.

### Insert new item to the custom toolbar collection

The following code example explains how to insert a new item to the existing custom toolbar in the Rich Text Editor.

{% highlight C# %} 

SfRichTextEditor richTextEditor = new SfRichTextEditor();
richTextEditor.PlaceHolder = "Type something";
ObservableCollection<object> collection = new ObservableCollection<object>();
richTextEditor.ToolbarItems = collection;
this.Content = richTextEditor;

//Insert a new item to the custom toolbar collection.
Button emojiButton = new Button();
emojiButton.BackgroundColor = Color.Transparent;
emojiButton.HeightRequest = 50;
emojiButton.WidthRequest = 50;
emojiButton.Text = "\U0001F642";
collection.Add(ToolbarOptions.Bold);
collection.Add(ToolbarOptions.Italic);
collection.Add(emojiButton);
collection.Add(ToolbarOptions.Underline);
{% endhighlight %}

### Remove an item from the custom toolbar collection

The following code example explains how to remove an existing item from the custom toolbar in the Rich Text Editor.

{% highlight C# %} 

SfRichTextEditor richTextEditor = new SfRichTextEditor();
richTextEditor.PlaceHolder = "Type something";
ObservableCollection<object> collection = new ObservableCollection<object>();
collection.Add(ToolbarOptions.Bold);
collection.Add(ToolbarOptions.Italic);
collection.Add(ToolbarOptions.Underline);
collection.Add(ToolbarOptions.NumberList);
collection.Add(ToolbarOptions.BulletList);
Button emojiButton = new Button();
emojiButton.BackgroundColor = Color.Transparent;
emojiButton.HeightRequest = 50;
emojiButton.WidthRequest = 50;
emojiButton.Text = "\U0001F642";
collection.Add(emojiButton);
richTextEditor.ToolbarItems = collection;
this.Content = richTextEditor;

//Remove an item from the custom toolbar collection.
collection.RemoveAt(0);
collection.Remove(emojiButton);

{% endhighlight %}

### Reorder the custom toolbar collection

The following code example explains how to reorder the custom toolbar in the Rich Text Editor.

{% highlight C# %} 

SfRichTextEditor richTextEditor = new SfRichTextEditor();
richTextEditor.PlaceHolder = "Type something";
ObservableCollection<object> collection = new ObservableCollection<object>();
collection.Add(ToolbarOptions.Italic);
collection.Add(ToolbarOptions.Underline);
collection.Add(ToolbarOptions.Bold);
Button emojiButton = new Button();
emojiButton.BackgroundColor = Color.Transparent;
emojiButton.HeightRequest = 50;
emojiButton.WidthRequest = 50;
emojiButton.Text = "\U0001F642";
collection.Add(emojiButton);
collection.Add(ToolbarOptions.NumberList);
collection.Add(ToolbarOptions.BulletList);
richTextEditor.ToolbarItems = collection;
this.Content = richTextEditor;

{% endhighlight %}
