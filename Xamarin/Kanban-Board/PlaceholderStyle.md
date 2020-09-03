---
layout: post
title: PlaceholderStyle for Essential Xamarin.Forms Kanban
description: Kanban Placeholder style
platform: xamarin
control: Kanban
documentation: ug
---

# Placeholder

The placeholder is to denote a card's new position in the [`KanbanColumn`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanColumn.html). It will appear while dragging a card over the column.

### Placeholder style

[`PlaceholderStyle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html#Syncfusion_SfKanban_XForms_SfKanban_PlaceholderStyle) property is used to customize the placeholder. Following [`KanbanPlaceholderStyle`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle.html) properties are used to customize its appearance.

* [`BackgroundColor`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle~BackgroundColor.html)  	 - This property is used to change the background color of the placeholder.
* [`BorderColor`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle~BorderColor.html) 	 	 - This property is used to change the border color of the placeholder.
* [`BorderThickness`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle~BorderThickness.html)  	 - This property is used to change the border width of the placeholder.
* [`StrokeDashArray`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle~StrokeDashArray.html)     - This property is used to change the dashes of the placeholder border.
* [`FontSize`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle~FontSize.html)            - This is used to change the text size of the placeholder.
* [`TextColor`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle~TextColor.html)           - This property is used to change the text color of the placeholder.

Following properties are used to customize the selected category when you have more than one category in a column.

* [`SelectedBackgroundColor`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle~SelectedBackgroundColor.html) 	- This property is used to change the background color of the selected placeholder.
* [`SelectedBorderColor`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle~SelectedBorderColor.html) 		- This property is used to change the border color of the selected placeholder.
* [`SelectedBorderThickness`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle~SelectedBorderThickness.html) 	- This property is used to change the border width of the selected placeholder.
* [`SelectedStrokeDashArray`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle~SelectedStrokeDashArray.html)     - This property is used to change the dashes of the selected placeholder.
* [`SelectedFontSize`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle~SelectedFontSize.html)            - This is used to change the font size of the text in selected placeholder.
* [`SelectedTextColor`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanPlaceholderStyle~SelectedTextColor.html)           - This property is used to change the color of the text in selected placeholder.

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

