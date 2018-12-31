---
layout: post
title: Customization for Syncfusion Essential Xamarin.Forms SfButton
description: How to customize a appearance for Xamarin.Forms SfButton.
platform: xamarin.forms
control: sfbutton
documentation: ug
---

## Customization

The button control supports to customize the border color, image width, corner radius, background color, and more. The button control can be customized using the following properties:


## CornerRadius

The `CornerRadius` property is used to customize the rounded edges in SfButton as demonstrated in the following code sample.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" CornerRadius="3">
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.CornerRadius = 3;

{% endhighlight %}
{% endtabs %}

![SfButton with cornerradius](images/Button_cornerradius.png)

## BorderWidth

The [`BorderWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~BorderWidth.html) property is used to customize the thickness of border in SfButton. 

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" BorderColor = "Red" BorderWidth="4">
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.BorderWidth = 4;
button.BorderColor = Color.Red;

{% endhighlight %}
{% endtabs %}

## BorderColor

The [`BorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~BorderColor.html) property is used to customize the color of border in SfButton.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" BorderColor = "Red" BorderWidth="4">
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.BorderWidth = 4;
button.BorderColor = Color.Red;

{% endhighlight %}
{% endtabs %}

![SfButton with border](images/Button_border.png)

## TextColor

The [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~TextColor.html) property is used to customize the color of text in SfButton.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" TextColor = "White">
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.TextColor = Color.White;

{% endhighlight %}
{% endtabs %}

![SfButton with text color](images/Button_textcolor.png)

## BackgroundColor

The [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~BackgroundColor.html) property is used to customize the background color of SfButton.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" BackgroundColor = "DeepSkyBlue">
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.BackgroundColor = Color.DeepSkyBlue;

{% endhighlight %}
{% endtabs %}

![SfButton with background color](images/Button_backgroundColor.png)

## FontSize

The [`FontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~FontSize.html) property is used to customize the size of text in SfButton.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" FontSize = "18">
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.FontSize = 18;

{% endhighlight %}
{% endtabs %}

![SfButton with font size](images/Button_fontsize.png)

## FontAttributes

The [`FontAttributes`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~FontAttributes.html) property is used to customize the font style of text in SfButton.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" FontAttributes = "Italic">
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.FontAttributes = FontAttributes.Italic;

{% endhighlight %}
{% endtabs %}

![SfButton with fontattributes](images/Button_fontattributes.png)

## FontFamily

The [`FontFamily`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~FontFamily.html) property is used to customize the font family of text in SfButton.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" FontFamily = "Arial">
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.FontFamily = "Arial";

{% endhighlight %}
{% endtabs %}

![SfButton with fontfamily](images/Button_fontfamily.png)

## TextAlignment

The [`HorizontalTextAlignment `](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~HorizontalTextAlignment.html) and [`VerticalTextAlignment `](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~VerticalTextAlignment.html) properties are used to customize the alignment of text in SfButton.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" HorizontalTextAlignment="Center" VerticalTextAlignment="Center">
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.HorizontalTextAlignment = TextAlignment.Center;
button.VerticalTextAlignment = TextAlignment.Center;

{% endhighlight %}
{% endtabs %}

## ShowIcon

you can enable the Icon image using the [`ShowIcon`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~ShowIcon.html) property to know whether any image appears to the SfButton.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" ImageSource="Heart.png" ShowIcon="True">
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.ImageSource = "Heart.png";
button.ShowIcon = True;

{% endhighlight %}
{% endtabs %}

## ImageSource

The [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~ImageSource.html) property is used to customize the icon image of SfButton by adding a custom image.

N> Enable the [`ShowIcon`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~ShowIcon.html) property to enable the [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~ImageSource.html) property. 

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" ImageSource="Heart.png" ShowIcon="True">
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.ImageSource = "Heart.png";
button.ShowIcon = True;

{% endhighlight %}
{% endtabs %}

![SfButton with image with content](images/Button_icon.png)

## ImageWidth

The [`ImageWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~ImageWidth.html) property is used to customize the width of icon image in SfButton.

N> Enable the [`ShowIcon`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~ShowIcon.html) property to enable the [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~ImageSource.html) property. 

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" ImageSource="Heart.png" ShowIcon="True" ImageWidth="50">
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.ImageSource = "Heart.png";
button.ShowIcon = true;
button.ImageWidth = 50;

{% endhighlight %}
{% endtabs %}

## ImageAlignment 

The [`ImageAlignment`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~ImageAlignment.html) property is used to customize the alignment of icon image in SfButton.

N> Enable the [`ShowIcon`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~ShowIcon.html) property to enable the [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~ImageSource.html) property. 

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" ImageSource="Heart.png" ShowIcon="True" ImageAlignment="End">
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.ImageSource = "Heart.png";
button.ShowIcon = true;
button.ImageAlignment = Alignment.End;

{% endhighlight %}
{% endtabs %}

![SfButton with image with icon image alignment](images/Button_iconalignment.png)

## Command

The [`Command`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~Command.html)  property is used to associate a command with an instance of SfButton. This property is most often set with MVVM pattern to bind callbacks back into the ViewModel.

N> Default value is [`null`].

{% tabs %}
{% highlight xaml %}

 <ContentPage.BindingContext>
    <local:CommandDemoViewModel />
 </ContentPage.BindingContext>

<button:SfButton x:Name="button" Text="Button" BackgroundColor="{Binding Background}" Command="{Binding ButtonCommand}">
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

// ViewModel

public class CommandDemoViewModel : INotifyPropertyChanged
{

    private Color _background = Color.Accent;

    public Color Background
    {
        get { return _background; }
        set
        {
            _background = value;
            NotifyPropertyChanged();
        }
    }

    private void NotifyPropertyChanged([CallerMemberName] String propertyName = "")
    {
        PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
    }

    public event PropertyChangedEventHandler PropertyChanged;

    public CommandDemoViewModel()
    {
        BackgroundColor();
        this.Background=Color.Accent;
    }

    private void BackgroundColor()
    {
        this.Background = this.Background == Color.DeepSkyBlue ? Color.Accent : Color.DeepSkyBlue;
    }

    public ICommand ButtonCommand => new Command(BackgroundColor);

}

{% endhighlight %}
{% endtabs %}

The complete customization sample:[Customization](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Customization-1070507783)