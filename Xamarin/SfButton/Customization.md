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

![SfButton with background color](images/Button_backgroundcolor.png)

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

You can enable the Icon image using the [`ShowIcon`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~ShowIcon.html) property to know whether any image appears to the SfButton.

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

## Shadow Effect

The button control provides shadow effect support. To enable shadow effect, set the `HasShadow` property to true.

You can customize the color of shadow using the `ShadowColor` property. 

{% tabs %}

{% highlight xaml %}

  <Grid HeightRequest="50" WidthRequest="200" VerticalOptions="Center" HorizontalOptions="Center">
            <SyncfusionButton:SfButton
                                     CornerRadius="25"
                                     HasShadow="True"
                                     BorderWidth="1"
                                     BorderColor="Gray"
                                     BackgroundColor="#538EEC">
                <SyncfusionButton:SfButton.Content>
                    <Grid HorizontalOptions="Center" VerticalOptions="Center">
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="45"/>
                            <ColumnDefinition Width="*"/>
                        </Grid.ColumnDefinitions>
                        <Grid Padding="15,0,5,0">
                            <Label Text="&#xE7BF;" 
                                   HorizontalTextAlignment="Center" 
                                   VerticalOptions="Center"
                                   VerticalTextAlignment="Center"
                                   HorizontalOptions="Start" 
                                   FontSize="25" 
                                   TextColor="White">
                                <Label.FontFamily>
                                    <OnPlatform x:TypeArguments="x:String">
                                        <On Platform="iOS" Value="Segoe MDL2 Assets" />
                                        <On Platform="Android" Value="button_Segoe MDL2 Assets.ttf#Segoe MDL2 Assets" />
                                        <On Platform="UWP" Value="/Assets/Fonts/button_Segoe MDL2 Assets.ttf#Segoe MDL2 Assets" />
                                    </OnPlatform>
                                </Label.FontFamily>
                            </Label>
                        </Grid>
                        <Grid Padding="0,15,15,15" Grid.Column="1" >
                            <Label HorizontalOptions="Center" 
                                   HorizontalTextAlignment="Center" 
                                   FontSize="15" 
                                   TextColor="White"               
                                   VerticalTextAlignment="Center" 
                                   VerticalOptions="Center" 
                                   LineBreakMode="NoWrap" 
                                   Text="ADD To CART">
                            </Label>
                        </Grid>
                    </Grid>
                </SyncfusionButton:SfButton.Content>
            </SyncfusionButton:SfButton>
        </Grid>
	
{% endhighlight %}

{% highlight C# %}

Grid mainGrid = new Grid() { HeightRequest = 50, WidthRequest = 200, HorizontalOptions = LayoutOptions.Center, VerticalOptions = LayoutOptions.Center };
            SfButton button = new SfButton() { CornerRadius = new Thickness(25), HasShadow = true, BorderWidth = 1, BorderColor = Color.Gray, BackgroundColor = Color.FromHex("#538EEC") };
            Grid contentGrid = new Grid() { HorizontalOptions = LayoutOptions.Center, VerticalOptions = LayoutOptions.Center };
            Grid iconGrid = new Grid() { Padding = new Thickness(15, 0, 5, 0) };
            Label iconLabel = new Label() { Text = "\uE7BF", HorizontalOptions = LayoutOptions.Start, VerticalOptions = LayoutOptions.Center, HorizontalTextAlignment = TextAlignment.Center, VerticalTextAlignment = TextAlignment.Center, FontSize = 25, TextColor = Color.White };
            Grid textGrid = new Grid() { Padding = new Thickness(0, 15, 15, 15) };
            Label textLabel = new Label() { Text = "ADD To CART", LineBreakMode = LineBreakMode.NoWrap, HorizontalOptions = LayoutOptions.Center, VerticalOptions = LayoutOptions.Center, HorizontalTextAlignment = TextAlignment.Center, VerticalTextAlignment = TextAlignment.Center, FontSize = 15, TextColor = Color.White };
            contentGrid.ColumnDefinitions.Add(new ColumnDefinition() { Width = 45 });
            contentGrid.ColumnDefinitions.Add(new ColumnDefinition() { Width = GridLength.Star });
            if (Device.RuntimePlatform == "iOS")
            {
                iconLabel.FontFamily = "Segoe MDL2 Assets";
            }
            else if (Device.RuntimePlatform == "Android")
            {
                iconLabel.FontFamily = "button_Segoe MDL2 Assets.ttf#Segoe MDL2 Assets";
            }
            else if (Device.RuntimePlatform == "UWP")
            {
                iconLabel.FontFamily = "/ Assets / Fonts / button_Segoe MDL2 Assets.ttf#Segoe MDL2 Assets";
            }

            iconGrid.Children.Add(iconLabel);
            textGrid.Children.Add(textLabel);
            contentGrid.Children.Add(iconGrid, 0, 0);
            contentGrid.Children.Add(textGrid, 1, 0);
            button.Content = contentGrid;
            mainGrid.Children.Add(button);
            this.Content = mainGrid;

{% endhighlight %}

{% endtabs %}

N> Shadow support has not been provided for UWP Platform.

![ShadowImage](images/Xamarin_Forms_Shadow.png)

## How to set font icons using ttf file?

You can refer this [link](https://help.syncfusion.com/metro-studio/export-font-icon) for getting the font icons. Add the font file to your application by using the following steps for each platform:

**Adding font file for iOS**

1. Add the font family inside `Resource` folder iOS project.
2. Add the font file with the following build action: `BundleResource`.
3. Update the `Info.plist` file (fonts that are provided by application, UIAppFonts, or key).

**Adding font file for Android**

Add the font file to the `Assets` folder in the application project, and set the following build action: `AndroidAsset`.

**Adding font file for UWP**

Add the font family inside the application project of UWP.

N> For iOS alone, FontFamily property is declared without succeeding with .ttf and for android and UWP platform font family name is defined followed by .ttf.

The complete customization sample:[Customization](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Customization-1070507783)