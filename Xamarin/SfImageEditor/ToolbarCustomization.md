---
layout : post
title : ToolbarCustomization in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to customize toolbar in ImageEditor for Xamarin.Forms
platform : Xamarin.Forms
control : ImageEditor
documentation : ug
---

# ToolbarCustomization

You can customize color palette, toolbar visibility and appearance of each toolbaritem.


## Customize toolbaritems

SfImageEditor control supports to customize and configure the apperance of toolbar menu. You can customize image editor toolbar by adding respective FootertoolbarItem and HeadertoolbarItem 

#### ToolbarItem

You can customize each toolbaritem with the help of `Text` and `Icon` properties. ImageEdior Toolbar menu contains set of header and footer menu items which helps to perform image editor actions
and this can be categorized into the following types,

1.HeaderToolbarItem
2.FooterToolbarItem
3.SubItems

 
### Adding HeadertoolbarItem

`HeadertoolbarItem` will be arranged on top of the image editor and you can customize headertoolbaritem with the help of Icon and Text as like below,

{% highlight C# %}

            editor.ToolbarSettings.ToolbarItems.Add(new HeaderToolbarItem() { Icon = ImageSource.FromResource("IMgeditForms.share.png"), Text="Share" });

{% endhighlight %}

### Adding FootertoolbarItem   

 `FooterToolbarItem` will be arranged on bottom of the image editor and you can customize footertoolbarItem with the help of Icon and Text along with subitems.

Refer to the below code snippet to customize FootertoolbarItem,

{% highlight C# %}

            editor.ToolbarSettings.ToolbarItems.Add(new FooterToolbarItem() { Icon = ImageSource.FromResource("IMgeditForms.delete.png"), Text="Delete" });
            editor.ToolbarSettings.ToolbarItems.Add(new FooterToolbarItem() { Icon = ImageSource.FromResource("IMgeditForms.more.png"), Text="More" });

{% endhighlight %}

### Adding SubItems to the FootertoolbarItem

`SubItems` only applicable for `FooterToolbarItem` and it represents grouped action of respective footertoolbarItem. SubItems will be arranged above the footertoolbarItem layout and you can also customize subitems appearence as like main toolbar items. 

Refer to the below code snippet to customize subitems of FootertoolbarItem,

{% highlight C# %}

 	editor.ToolbarSettings.ToolbarItems.Add(new FooterToolbarItem()
            {
                Text = "More",
                Icon = ImageSource.FromResource("IMgeditForms.Image.more.png"),
                SubItems = new ObservableCollection<Syncfusion.SfImageEditor.XForms.ToolbarItem>()
                {
                   new ToolbarItem() {
                Icon = ImageSource.FromResource("IMgeditForms.Image.download.png")
                },
                   new ToolbarItem() {
                Icon = ImageSource.FromResource("IMgeditForms.Image.share.png")
                } }
            });

{% endhighlight %}

N> You can remove existing toolbaritems(Text,Path,Shape,Transform,Reset,Undo,Redo and Save) from the image editor toolbarItems collection based on the index value. 

You can change icon and text value dynamically for any of already added toolbaritem based on the index as like below,

{% highlight C# %}

editor.ToolbarSettings.ToolbarItems[5].Text = "new item";
editor.ToolbarSettings.ToolbarItems[3].Icon = ImageSource.FromResource("ImgPanning.Image.jpg");

{% endhighlight %}


### ToolbarItemSelected event 

Whenever you tap the toolbar menu item, the `ToolbarItemSelected` event will be triggered and you can get the respective tapped toolbaritem as an argument as shown below,

{% highlight C# %}

        public MainPage()
        {
            editor.ToolbarSettings.ToolbarItemSelected += ToolbarSettings_ToolbarItemSelected;
        }

        private void ToolbarSettings_ToolbarItemSelected(object sender, ToolbarItemSelectedEventArgs e)
        {
           DisplayAlert("Selected ToolbarItem is  " + e.ToolbarItem.Text, "Ok", "Cancel");
        }

{% endhighlight %}


## To hide/show toolbar

To show or hide the toolbar, set `IsVisible` property of toolbar to either true or false. By default, toolbar IsVisible property is true.

{% tabs %}

{% highlight XAML %}
  
     <imageeditor:SfImageEditor.ToolbarSettings>
			<imageeditor:ToolbarSettings IsVisible="false" />
		</imageeditor:SfImageEditor.ToolbarSettings>
      
{% endhighlight %}

{% highlight C# %}

      editor.ToolbarSettings.IsVisible = false;
     

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/toolbarvisibility.png)


## To hide/visible the toolbar item

You can hide or show the toolbar items by specifying its icon name and setting the boolean value to true or false. 

N> You can customize the icon by specifying its names namely, text, path, shapes, transform, rectangle, circle, arrow, flip, crop, rotate, reset, undo, Redo and save.

{% tabs %}

{% highlight C# %}

    editor.SetToolbarItemVisibility("text,save", false);

{% endhighlight %}

{% endtabs %}


![SfImageEditor](ImageEditor_images/Toolbaritemvisibiliy.png)


## To customize the ColorPalette

You can change the default colors of the ColorPalette in toolbar.

{% tabs %}

{% highlight XAML %}
  
    <imageeditor:SfImageEditor.ColorPalette>
			<Color>Yellow</Color>
			<Color>Pink</Color>
			<Color>Violet</Color>
		</imageeditor:SfImageEditor.ColorPalette>  
      
{% endhighlight %}

{% highlight C# %}

    ObservableCollection<Color> CustomColorPalette = new ObservableCollection<Color>()
	{
				Color.Yellow,
				Color.Pink,
				Color.Violet
	};

			editor.ColorPalette = CustomColorPalette;

{% endhighlight %}

{% endtabs %}
