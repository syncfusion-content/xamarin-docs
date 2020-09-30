---
layout: post
title: PlaceholderStyle for Essential Xamarin.Forms Kanban
description: Kanban Placeholder style
platform: xamarin
control: Kanban
documentation: ug
---

# Placeholder

The placeholder is to denote a card's new position in the [`KanbanColumn`](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanColumn.html). It will appear while dragging a card over the column.

### Placeholder style

[`PlaceholderStyle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html#Syncfusion_SfKanban_XForms_SfKanban_PlaceholderStyle) property is used to customize the placeholder. Following [`KanbanPlaceholderStyle`](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle.html) properties are used to customize its appearance.

* [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_XForms_KanbanPlaceholderStyle_BackgroundColor)  	 - This property is used to change the background color of the placeholder.
* [`BorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_XForms_KanbanPlaceholderStyle_BorderColor) 	 	 - This property is used to change the border color of the placeholder.
* [`BorderThickness`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_XForms_KanbanPlaceholderStyle_BorderThickness)  	 - This property is used to change the border width of the placeholder.
* [`StrokeDashArray`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_XForms_KanbanPlaceholderStyle_StrokeDashArray)     - This property is used to change the dashes of the placeholder border.
* [`FontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_XForms_KanbanPlaceholderStyle_FontSize)            - This is used to change the text size of the placeholder.
* [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_XForms_KanbanPlaceholderStyle_TextColor)           - This property is used to change the text color of the placeholder.

Following properties are used to customize the selected category when you have more than one category in a column.

* [`SelectedBackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_XForms_KanbanPlaceholderStyle_SelectedBackgroundColor) 	- This property is used to change the background color of the selected placeholder.
* [`SelectedBorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_XForms_KanbanPlaceholderStyle_SelectedBorderColor) 		- This property is used to change the border color of the selected placeholder.
* [`SelectedBorderThickness`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_XForms_KanbanPlaceholderStyle_SelectedBorderThickness) 	- This property is used to change the border width of the selected placeholder.
* [`SelectedStrokeDashArray`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_XForms_KanbanPlaceholderStyle_SelectedStrokeDashArray)     - This property is used to change the dashes of the selected placeholder.
* [`SelectedFontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_XForms_KanbanPlaceholderStyle_SelectedFontSize)            - This is used to change the font size of the text in selected placeholder.
* [`SelectedTextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_XForms_KanbanPlaceholderStyle_SelectedTextColor)           - This property is used to change the color of the text in selected placeholder.

The following code example describes the above behavior.

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban.PlaceholderStyle >

<kanban:KanbanPlaceholderStyle FontSize="16"
TextColor="Green"
BackgroundColor="Fuchsia"
BorderColor="Fuchsia"
BorderThickness="2"

SelectedFontSize="16"
SelectedTextColor="Red"
SelectedBorderColor="Yellow"
SelectedBorderThickness="2"
SelectedBackgroundColor="Green">
</kanban:KanbanPlaceholderStyle>

</kanban:SfKanban.PlaceholderStyle>

{% endhighlight %}

{% highlight C# %}

KanbanPlaceholderStyle style = new KanbanPlaceholderStyle();

style.FontSize = 20;
style.TextColor = Color.Green;
style.BackgroundColor = Color.FromRgb(239, 89, 123);
style.BorderColor = Color.Blue;
style.BorderThickness = 2;
style.StrokeDashArray = new double[] { 1, 1 };

style.SelectedFontSize = 20;
style.SelectedTextColor = Color.Red;
style.SelectedBorderColor = Color.Yellow;
style.SelectedBackgroundColor = Color.FromRgb(0, 255, 0);
style.SelectedBorderThickness = 2;
style.SelectedStrokeDashArray = new double[] { 2, 1 };

kanban.PlaceholderStyle = style;

{% endhighlight %}

{% endtabs %}

The following output demonstrates the above code example.

![PlaceholderStyle support for Xamarin.Forms Kanban](SfKanban_images/PlaceholderStyle.png)

