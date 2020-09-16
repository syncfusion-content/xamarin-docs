---
layout: post
title: Customization for Syncfusion Essential Xamarin.Forms SfButton
description: This section describes how to customize the appearance of text, background and image for SfButton in Xamarin.Forms.
platform: xamarin.forms
control: sfbutton
documentation: ug
---

# Customization in Xamarin Buttons(SfButton)

The button control supports to customize the border color, image width, corner radius, background color, and more. The button control can be customized using the following properties:

## Text Customization

The text inside the button can be customized by its text color, font size, font attributes, font family and text alignment.

### TextColor

The [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_TextColor) property is used to customize the color of text in SfButton.

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

### FontSize

The [`FontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_FontSize) property is used to customize the size of text in SfButton.

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

### FontAttributes

The [`FontAttributes`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_FontAttributes) property is used to customize the font style of text in SfButton.

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

### FontFamily

The [`FontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_FontFamily) property is used to customize the font family of text in SfButton.

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

### TextAlignment

The [`HorizontalTextAlignment `](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_HorizontalTextAlignment) and [`VerticalTextAlignment `](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_VerticalTextAlignment) properties are used to customize the alignment of text in SfButton.

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

## Background Customization

The background of the button can be customized by its background color, border color, border width and corner radius.

### BackgroundColor

The [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_BackgroundColor) property is used to customize the background color of SfButton.

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

![SfButton with background color](images/Button_backgroundcolor.png)

### BorderColor

The [`BorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_BorderColor) property is used to customize the color of border in SfButton.

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

### BorderWidth

The [`BorderWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_BorderWidth) property is used to customize the thickness of border in SfButton. 

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

### CornerRadius

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

## Image Customization

The image can be customized by its show icon, image source, image width and image alignment.

### ShowIcon

You can enable the Icon image using the [`ShowIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ShowIcon) property to know whether any image appears to the SfButton.

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

### ImageSource

The [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) property is used to customize the icon image of SfButton by adding a custom image.

N> Enable the [`ShowIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ShowIcon) property to enable the [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) property. 

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

### ImageWidth

The [`ImageWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageWidth) property is used to customize the width of icon image in SfButton.

N> Enable the [`ShowIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ShowIcon) property to enable the [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) property. 

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

### ImageAlignment 

The [`ImageAlignment`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageAlignment) property is used to customize the alignment of icon image in SfButton. The following options are available in [`ImageAlignment`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageAlignment):

* [`Start`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.Alignment.html) - Places the image at the start if any flow direction is mentioned.
* [`End`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.Alignment.html) - Places the image at the end if any flow direction is mentioned.
* [`Top`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.Alignment.html) - Places the image at the top of the text.
* [`Bottom`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.Alignment.html) - Places the image at the bottom of the text.
* [`Left`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.Alignment.html) - Places the image at the left of the text. 
* [`Right`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.Alignment.html) - Places the image at the right of the text.

N> Enable the [`ShowIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ShowIcon) property to enable the [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) property. 

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

## Gradient background

You can set the gradient as background of SfButton using the [`BackgroundGradient`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_BackgroundGradient) property. It supports the following types of gradients:

* Linear gradient
* Radial gradient

N> UWP platform does not support radial gradient.

Refer to this [documentation](https://help.syncfusion.com/xamarin/sfgradientview/customization) to learn more details about gradient.

{% tabs %}
{% highlight xaml %}

xmlns:gradient ="clr-namespace:Syncfusion.XForms.Graphics;assembly=Syncfusion.Core.XForms"

. . . 

<button:SfButton Text="Linear Gradient" CornerRadius="20">
    <button:SfButton.BackgroundGradient>
        <gradient:SfLinearGradientBrush>
            <gradient:SfLinearGradientBrush.GradientStops>
                <gradient:SfGradientStop Color="#2F9BDF" Offset="0"/>
                <gradient:SfGradientStop Color="#51F1F2" Offset="1"/>
            </gradient:SfLinearGradientBrush.GradientStops>
        </gradient:SfLinearGradientBrush>
    </button:SfButton.BackgroundGradient>
</button:SfButton>

<button:SfButton Text="Radial Gradient" CornerRadius="20">
    <button:SfButton.BackgroundGradient>
        <gradient:SfRadialGradientBrush Radius="1.5">
            <gradient:SfRadialGradientBrush.GradientStops>
                <gradient:SfGradientStop Color="#FFB57B" Offset="0"/>
                <gradient:SfGradientStop Color="#FF5361" Offset="1"/>
            </gradient:SfRadialGradientBrush.GradientStops>
        </gradient:SfRadialGradientBrush>
    </button:SfButton.BackgroundGradient>
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

using Syncfusion.XForms.Graphics;

. . .

SfButton linearButton = new SfButton();
linearButton.Text = "Linear Gradient";
linearButton.CornerRadius = 20;
SfLinearGradientBrush linearGradientBrush = new SfLinearGradientBrush();
linearGradientBrush.GradientStops = new GradientStopCollection()
{
    new SfGradientStop(){ Color = Color.FromHex("#2F9BDF"), Offset = 0 },
    new SfGradientStop(){ Color = Color.FromHex("#51F1F2"), Offset = 1 }
};     
linearButton.BackgroundGradient = linearGradientBrush;

SfButton radialButton = new SfButton();
radialButton.Text = "Radial Gradient";
radialButton.CornerRadius = 20;
SfRadialGradientBrush radialGradientBrush = new SfRadialGradientBrush();
radialGradientBrush.Radius = 1.5;
radialGradientBrush.GradientStops = new GradientStopCollection()
{
    new SfGradientStop(){ Color = Color.FromHex("#FFB57B"), Offset = 0 },
    new SfGradientStop(){ Color = Color.FromHex("#FF5361"), Offset = 1 }
};
radialButton.BackgroundGradient = radialGradientBrush;

{% endhighlight %}
{% endtabs %}

![Xamarin.Forms gradient support](images/Button_gradient.png)

## Command

The [`Command`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_Command)  property is used to associate a command with an instance of SfButton. This property is most often set with MVVM pattern to bind callbacks back into the ViewModel.

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
        SetBackgroundColor();
        this.Background=Color.Accent;
    }

    private void SetBackgroundColor()
    {
	    //do whatever you want to do here
        this.Background = this.Background == Color.DeepSkyBlue ? Color.Accent : Color.DeepSkyBlue;
    }

    public ICommand ButtonCommand => new Command(SetBackgroundColor);

}

{% endhighlight %}
{% endtabs %}

## Shadow Effect

The button control provides shadow effect support. To enable shadow effect, set the `HasShadow` property to true.

You can customize the color of shadow using the `ShadowColor` property. 

{% tabs %}

{% highlight xaml %}

          <SyncfusionButton:SfButton
                                     HeightRequest="50"
                                     WidthRequest="200"
                                     VerticalOptions="Center"
                                     HorizontalOptions="Center"
                                     CornerRadius="25"
                                     HasShadow="True"
                                     BorderWidth="1"
                                     BorderColor="Gray"
                                     BackgroundColor="#538EEC"
                                     ImageSource="Basket.png"
                                     ShowIcon="True"
                                     ImageAlignment="End"
                                     Text="ADD To CART"/>
	
{% endhighlight %}

{% highlight C# %}

SfButton button = new SfButton()
            {
                HeightRequest = 50,
                WidthRequest = 200,
                HorizontalOptions = LayoutOptions.Center,
                VerticalOptions = LayoutOptions.Center,
                CornerRadius = new Thickness(25),
                HasShadow = true,
                BorderWidth = 1,
                BorderColor = Color.Gray,
                BackgroundColor = Color.FromHex("#538EEC"),
                ImageSource = "Basket.png",
                ShowIcon = true,
                ImageAlignment = Alignment.Start,
                Text = "ADD To CART"
            };

            this.Content = button;

{% endhighlight %}

{% endtabs %}

N> Shadow support has not been provided for UWP Platform.

![ShadowImage](images/Xamarin_Forms_Shadow.png)

## Ripple Effect

The button control provides ripple effect support. To enable the ripple effect, set the [`EnableRippleEffect`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_EnableRippleEffect) property to true. By default, [`EnableRippleEffect`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_EnableRippleEffect) value is true.

{% tabs %}

{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button" EnableRippleEffect="false" />

{% endhighlight %}

{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.EnableRippleEffect = false;

{% endhighlight %}

{% endtabs %}

N> Ripple Effect support has not been provided for UWP and WPF Platform.

The complete customization sample:[Customization](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Customization-1070507783)

## See also

[How to create a different shape of Xamarin.Forms button](https://www.syncfusion.com/kb/11850/how-to-create-a-different-shape-of-xamarin-forms-button)

[How to create a round or circle button in Xamarin.Forms](https://www.syncfusion.com/kb/10938/how-to-create-a-round-or-circle-button-in-xamarin-forms)

[How to add the SVG images in Xamarin.Forms button](https://www.syncfusion.com/kb/11682/how-to-add-the-svg-images-in-xamarin-forms-button)
