---
layout: post
title: Customization in Xamarin Button Control | Syncfusion
description: Discover the customization capabilities of the Syncfusion Xamarin Button (SfButton) control, including text, background, and image properties.
platform: Xamarin
control: SfButton
documentation: ug
---

# Customization in Xamarin Button (SfButton)

The [Xamarin Button](https://www.syncfusion.com/xamarin-ui-controls/xamarin-button) control supports customization options such as border color, image width, corner radius, and background color. The button control can be customized using the following properties:

## Text Customization

You can customize the text inside the button by modifying text color, font size, font attributes, font family, and text alignment.

### TextColor

The [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_TextColor) property customizes the text color in [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).

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

The [`FontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_FontSize) property customizes the text size in [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).

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

The [`FontAttributes`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_FontAttributes) property customizes the font style of text in [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).

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

![SfButton with font attributes](images/Button_fontattributes.png)

### FontFamily

The [`FontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_FontFamily) property customizes the font family of text in [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).

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

![SfButton with font family](images/Button_fontfamily.png)

### TextAlignment

The [`HorizontalTextAlignment`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_HorizontalTextAlignment) and [`VerticalTextAlignment`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_VerticalTextAlignment) properties customize text alignment in [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).

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

Customize the button's background by modifying background color, border color, border width, and corner radius.

### BackgroundColor

The [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_BackgroundColor) property customizes the background color of [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).

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

The [`BorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_BorderColor) property customizes the border color in [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).

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

The [`BorderWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_BorderWidth) property customizes the border thickness in [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).

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

### BorderThickness

The [`BorderThickness`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Border.SfBorder.html#Syncfusion_XForms_Border_SfBorder_BorderThickness) property customizes the border thickness on all four sides of the [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button"  HorizontalOptions="Center" VerticalOptions="Center" BorderColor = "Red" BorderThickness="0,0,0,5">
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.HorizontalOptions = LayoutOptions.Center;
button.VerticalOptions = LayoutOptions.Center;
button.BorderColor = Color.Red;
button.BorderThickness = new Thickness (0,0,0,5);

{% endhighlight %}
{% endtabs %}

![SfButton with border thickness](images/Button_borderthickness.png)

### CornerRadius

The [`CornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Border.SfBorder.html#Syncfusion_XForms_Border_SfBorder_CornerRadius) property customizes the rounded edges in [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html), as demonstrated in the following code sample.

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

![SfButton with corner radius](images/Button_cornerradius.png)

## Image Customization

The image can be customized by configuring the show icon option, image source, image width, and image alignment.

### ShowIcon

You can enable the icon image using the [`ShowIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ShowIcon) property to determine if an image appears on the [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).

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

## Image

The [`Image`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_Image) property customizes the height, width, image source, and aspect for the image of [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).

{% tabs %}
{% highlight xaml %}

<button:SfButton x:Name="button" Text="Button"  >
<button:SfButton.Image>
  <Image Source="ButtonUserContact.png" HeightRequest="50" WidthRequest="50"/>
</button:SfButton.Image>
</button:SfButton>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.HorizontalOptions = LayoutOptions.Center;
button.VerticalOptions = LayoutOptions.Center;
button.Image = new Image()
{
    source = "ButtonUserContact.png",
    WidthRequest = 50,
    HeightRequest = 50
};

{% endhighlight %}
{% endtabs %}

![SfButton with image property](images/Button_image.png)

### ImageSource

The [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) property customizes the icon image on [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html) by adding a custom image.

> Note: Enable the [`ShowIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ShowIcon) property to activate the [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) property.

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

![SfButton with icon image](images/Button_icon.png)

### ImageWidth

The [`ImageWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageWidth) property customizes the width of the icon image in [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).

> Note: Enable the [`ShowIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ShowIcon) property to activate the [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) property.

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

The [`ImageAlignment`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageAlignment) property customizes the alignment of the icon image in [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html). The following options are available:

- [`Start`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.Alignment.html#Syncfusion_XForms_Buttons_Alignment_Start) - Places the image on the left edge of [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).
- [`End`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.Alignment.html#Syncfusion_XForms_Buttons_Alignment_End) - Places the image on the right edge of [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).
- [`Top`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.Alignment.html#Syncfusion_XForms_Buttons_Alignment_Top) - Places the image above the text.
- [`Bottom`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.Alignment.html#Syncfusion_XForms_Buttons_Alignment_Bottom) - Places the image below the text.
- [`Left`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.Alignment.html#Syncfusion_XForms_Buttons_Alignment_Left) - Ensures the image remains on the left part of [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html) despite directional changes.
- [`Right`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.Alignment.html#Syncfusion_XForms_Buttons_Alignment_Right) - Ensures the image remains on the right part of [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html) despite directional changes.
> Note: Enable the [`ShowIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ShowIcon) property to activate the [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) property.

**End Image Alignment in `SfButton`**

{% tabs %}
{% highlight xaml %}

   <buttons:SfButton  
            Text="Shopping"
            TextColor="Black"
            HorizontalOptions="Center"
            ImageSource="add_to_card.png"
            ShowIcon="True" 
            ImageWidth="50"
            BorderWidth="2"
            BorderColor="Black"
            BackgroundColor="White"
            ImageAlignment="End"/>

{% endhighlight %}

{% highlight c# %}
SfButton button = new SfButton()
{
    Text = "Shopping",
    TextColor = Color.Black,
    HorizontalOptions = LayoutOptions.Center,
    ImageSource = "add_to_card.png",
    ShowIcon = true,
    ImageWidth = 50,
    BorderWidth = 2,
    BorderColor = Color.Black,
    BackgroundColor = Color.White,
    ImageAlignment = Alignment.End
};

{% endhighlight %}
{% endtabs %}

![SfButton with end image alignment](images/Button_imagealignment_end.png)

**Start Image Alignment in `SfButton`**

{% tabs %}
{% highlight xaml %}

      <buttons:SfButton  
            Text="Shopping"
            TextColor="Black"
            HorizontalOptions="Center"
            ImageSource="add_to_card.png"
            ShowIcon="True" 
            ImageWidth="50"
            BorderWidth="2"
            BorderColor="Black"
            BackgroundColor="White"
            ImageAlignment="Start"/>

{% endhighlight %}

{% highlight c# %}
SfButton button = new SfButton()
{
    Text = "Shopping",
    TextColor = Color.Black,
    HorizontalOptions = LayoutOptions.Center,
    ImageSource = "add_to_card.png",
    ShowIcon = true,
    ImageWidth = 50,
    BorderWidth = 2,
    BorderColor = Color.Black,
    BackgroundColor = Color.White,
    ImageAlignment = Alignment.Start
};


{% endhighlight %}
{% endtabs %}

![SfButton with start image alignment](images/Button_imagealignment_start.png)

**Top Image Alignment in `SfButton`**

{% tabs %}
{% highlight xaml %}

      <buttons:SfButton  
            Text="Shopping"
            TextColor="Black"
            HorizontalOptions="Center"
            ImageSource="add_to_card.png"
            ShowIcon="True" 
            ImageWidth="50"
            BorderWidth="2"
            BorderColor="Black"
            BackgroundColor="White"
            ImageAlignment="Top"/>

{% endhighlight %}

{% highlight c# %}
SfButton button = new SfButton()
{
    Text = "Shopping",
    TextColor = Color.Black,
    HorizontalOptions = LayoutOptions.Center,
    ImageSource = "add_to_card.png",
    ShowIcon = true,
    ImageWidth = 50,
    BorderWidth = 2,
    BorderColor = Color.Black,
    BackgroundColor = Color.White,
    ImageAlignment = Alignment.Top
};


{% endhighlight %}
{% endtabs %}

![SfButton with top image alignment](images/Button_imagealignment_top.png)

**Bottom Image Alignment in `SfButton`**

{% tabs %}
{% highlight xaml %}

      <buttons:SfButton  
            Text="Shopping"
            TextColor="Black"
            HorizontalOptions="Center"
            ImageSource="add_to_card.png"
            ShowIcon="True" 
            ImageWidth="50"
            BorderWidth="2"
            BorderColor="Black"
            BackgroundColor="White"
            ImageAlignment="Bottom"/>

{% endhighlight %}

{% highlight c# %}
SfButton button = new SfButton()
{
    Text = "Shopping",
    TextColor = Color.Black,
    HorizontalOptions = LayoutOptions.Center,
    ImageSource = "add_to_card.png",
    ShowIcon = true,
    ImageWidth = 50,
    BorderWidth = 2,
    BorderColor = Color.Black,
    BackgroundColor = Color.White,
    ImageAlignment = Alignment.Bottom
};


{% endhighlight %}
{% endtabs %}

![SfButton with image with icon image with top alignment](images/Button_imagealignment_bottom.png)

**Left image alignment in `SfButton`**

In RTL flow direction, image alignment with [`Start`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.Alignment.html#Syncfusion_XForms_Buttons_Alignment_Start) will change its direction of placing image to the right. To keep that in same left position, set [`Left`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.Alignment.html#Syncfusion_XForms_Buttons_Alignment_Left) alignment as shown in the following code sample.

{% tabs %}
{% highlight xaml %}

      <buttons:SfButton  
            Text="Shopping"
            TextColor="Black"
            HorizontalOptions="Center"
            ImageSource="add_to_card.png"
            ShowIcon="True" 
            ImageWidth="50"
            BorderWidth="2"
            BorderColor="Black"
            BackgroundColor="White"
            ImageAlignment="Left"/>

{% endhighlight %}

{% highlight c# %}

SfButton button = new SfButton()
{
    Text = "Shopping",
    TextColor = Color.Black,
    HorizontalOptions = LayoutOptions.Center,
    ImageSource = "add_to_card.png",
    ShowIcon = true,
    ImageWidth = 50,
    BorderWidth = 2,
    BorderColor = Color.Black,
    BackgroundColor = Color.White,
    ImageAlignment = Alignment.Left
};

{% endhighlight %}
{% endtabs %}

![SfButton with image with icon image with left alignment](images/Button_imagealignment_left.png)

**Right image alignment in `SfButton`**

In RTL flow direction, image alignment with [`End`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.Alignment.html#Syncfusion_XForms_Buttons_Alignment_End) will change its direction of placing image to the left. To keep that in same right position, set [`Right`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.Alignment.html#Syncfusion_XForms_Buttons_Alignment_Right) alignment as shown in the following code sample.

{% tabs %}
{% highlight xaml %}

      <buttons:SfButton  
            Text="Shopping"
            TextColor="Black"
            HorizontalOptions="Center"
            ImageSource="add_to_card.png"
            ShowIcon="True" 
            ImageWidth="50"
            BorderWidth="2"
            BorderColor="Black"
            BackgroundColor="White"
            ImageAlignment="Right"/>

{% endhighlight %}

{% highlight c# %}
SfButton button = new SfButton()
{
    Text = "Shopping",
    TextColor = Color.Black,
    HorizontalOptions = LayoutOptions.Center,
    ImageSource = "add_to_card.png",
    ShowIcon = true,
    ImageWidth = 50,
    BorderWidth = 2,
    BorderColor = Color.Black,
    BackgroundColor = Color.White,
    ImageAlignment = Alignment.Right
};


{% endhighlight %}
{% endtabs %}

![SfButton with image with icon image with right alignment](images/Button_imagealignment_right.png)

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

The [`Command`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_Command)  property is used to associate a command with an instance of [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html). This property is most often set with MVVM pattern to bind callbacks back into the ViewModel.

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

The button control provides shadow effect support. To enable shadow effect, set the [`HasShadow`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Border.SfBorder.html#Syncfusion_XForms_Border_SfBorder_HasShadow) property to true.

You can customize the color of shadow using the [`ShadowColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Border.SfBorder.html#Syncfusion_XForms_Border_SfBorder_ShadowColor) property. 

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

The complete customization sample:[Customization](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Customization-1070507783)

## See also

[How to create a different shape of Xamarin.Forms button](https://support.syncfusion.com/kb/article/10315/how-to-create-a-different-shape-of-xamarin-forms-button)

[How to create a round or circle button in Xamarin.Forms](https://support.syncfusion.com/kb/article/9456/how-to-create-a-round-or-circle-button-in-xamarin-forms)

[How to add the SVG images in Xamarin.Forms button](https://support.syncfusion.com/kb/article/10118/how-to-add-the-svg-images-in-xamarin-forms-button)
