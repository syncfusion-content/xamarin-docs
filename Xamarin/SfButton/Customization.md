---
layout: post
title: Customization for Syncfusion Essential Xamarin.Forms SfButton
description: How to customize a appearance for Xamarin.Forms SfButton.
platform: xamarin.forms
control: sfbutton
documentation: ug
---

## Customization

The button control supports customizing the border color, image width, corner radius, background color, and more. The button can be customized using the following properties.


## Corner radius

The `CornerRadius` property is used to customize the rounded edges in the button as demonstrated in the following code sample.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" CornerRadius="3"  >
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.CornerRadius = 3;

{% endhighlight %}
{% endtabs %}

![SfButton with cornerradius](images/Button_CornerRadius.png)

## Border width

The [`BorderWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~BorderWidth.html) property is used to customize the thickness of border in SfButton. 

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" BorderColor = "Red" BorderWidth="4"  >
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.BorderWidth = 4;
button.BorderColor = Color.Red;

{% endhighlight %}
{% endtabs %}

![SfButton with border radius](images/Button_BorderRadius.png)

## Border color

The [`BorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~BorderColor.html) property is used to customize the color of the border in SfButton.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" BorderColor = "Red" BorderWidth="4"  >
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.BorderWidth = 4;
button.BorderColor = Color.Red;

{% endhighlight %}
{% endtabs %}

![SfButton with border color](images/Button_BorderColor.png)

## Text Color

The [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~TextColor.html) property is used to customize the color of the text in SfButton.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" TextColor = "White" >
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.TextColor = Color.White;

{% endhighlight %}
{% endtabs %}

![SfButton with text color](images/Button_TextColor.png)

## Background Color

The [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~BackgroundColor.html) property is used to customize the background color of the [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton.html).

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" BackgroundColor = "Accent" >
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.BackgroundColor = Color.Accent;

{% endhighlight %}
{% endtabs %}

![SfButton with background color](images/Button_backgroundColor.png)

## FontSize

The [`FontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~FontSize.html) property is used to customize the size of the text in SfButton.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" FontSize = "18" >
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

The [`FontAttributes`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~FontAttributes.html) property is used to customize the font style of the text in SfButton.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" FontAttributes = "Italic" >
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

The [`FontFamily`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~FontFamily.html) property is used to customize the font family of the text in SfButton.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" FontFamily = "Arial" >
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

The [`HorizontalTextAlignment `](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~HorizontalTextAlignment.html) and [`VerticalTextAlignment `](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~VerticalTextAlignment.html) property is used to customize the alignment of the text in SfButton.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" HorizontalTextAlignment="Center" VerticalTextAlignment="Center" >
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.HorizontalTextAlignment = TextAlignment.Center;
button.VerticalTextAlignment = TextAlignment.Center;

{% endhighlight %}
{% endtabs %}

![SfButton with text alignment](images/Button_textalignment.png)

## ImageSource

The [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~ImageSource.html) property is used to customize the background of SfButton by add the custome image.

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" ImageSource="">
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
 button.ImageSource= "";

{% endhighlight %}
{% endtabs %}

![SfButton with image as backgroung](images/Button_background.png)