---
layout: post
title: Customization in Xamarin Chips control | Syncfusion
description: Learn about customization support for background color, border color, close button color etc in Syncfusion Xamarin Chips control and more details.
platform: xamarin
control: Chips
documentation: ug
---

# Customization in Xamarin Chips (SfChip)

The chip control supports to customize the background color, border color, close button color, and more. The chip control can be customized using the following properties:

## ShowCloseButton

The [`ShowCloseButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChip.html#Syncfusion_XForms_Buttons_SfChip_ShowCloseButton) property sets the visible state of close button in SfChip.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            ShowCloseButton="true" >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.ShowCloseButton = true;
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with CloseButton](images/customization-images/chip_showclosebutton_image.png)

N> The default value of ShowCloseButton is [`false`].

## ShowSelectionIndicator

The [`ShowSelectionIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChip.html#Syncfusion_XForms_Buttons_SfChip_ShowSelectionIndicator) property sets the visible state of selection indicator in SfChip.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            ShowCloseButton="true"
                            ShowSelectionIndicator="true"
                            >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.ShowCloseButton = true;
            chip.ShowSelectionIndicator = true;
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with ShowSelectionIndicator](images/customization-images/chip_showselectionindicator_image.png)

N> The default value of ShowSelectionIndicator is [`false`].

## CloseButtonColor

The [`CloseButtonColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChip.html#Syncfusion_XForms_Buttons_SfChip_CloseButtonColor) property customizes the color of the close button in SfChip.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            ShowCloseButton="true"
                            CloseButtonColor="White"
                            >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.ShowCloseButton = true;
            chip.CloseButtonColor = Color.White;
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with CloseButtonColor](images/customization-images/chip_closebuttoncolor_image.png)

N> The default value of CloseButtonColor is [`Color.FromHex("#6b6b6b")`].

## SelectionIndicatorColor

The [`SelectionIndicatorColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChip.html#Syncfusion_XForms_Buttons_SfChip_SelectionIndicatorColor) property customizes the selection indicator color in SfChip.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            ShowCloseButton="true"
                            ShowSelectionIndicator="true"
                            CloseButtonColor = "White"
                            SelectionIndicatorColor = "White"
                            >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.ShowCloseButton = true;
            chip.ShowSelectionIndicator = true;
            chip.CloseButtonColor = Color.White;
            chip.SelectionIndicatorColor = Color.White;
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with SelectionIndicatorColor](images/customization-images/chip_selectionindicatorcolor_image.png)

N> The default value of SelectionIndicatorColor is [`Color.FromHex("#6b6b6b")`].

## BackgroundColor

The [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_BackgroundColor) property customizes the background color of SfChip.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            ShowCloseButton="true"
                            ShowSelectionIndicator="true"
                            CloseButtonColor = "White"
                            SelectionIndicatorColor = "White"
                            BackgroundColor="Aqua"
                            >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.ShowSelectionIndicator = true;
            chip.CloseButtonColor = Color.White;
            chip.SelectionIndicatorColor = Color.White;
            chip.BackgroundColor = Color.Aqua;
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with BackgroundColor](images/customization-images/chip_chipbackgroundcolor_image.png)

N> The default value of BackgroundColor is [`Color.Accent`].

## BorderColor

The [`BorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_BorderColor) property customizes the color of border in SfChip.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            BorderWidth="4"
                            BorderColor="Black"
                            >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.BorderWidth = 4;
            chip.BorderColor = Color.Black;
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with BorderColor](images/customization-images/chip_bordercolor_image.png)

N> The default value of BorderColor is [`Color.Transparent`].

## BorderWidth

The [`BorderWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_BorderWidth) property customizes the thickness of border in SfChip.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            BorderWidth="8"
                            BorderColor="Black"
                            >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.BorderWidth = 8;
            chip.BorderColor = Color.Black;
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with BorderWidth](images/customization-images/chip_borderwidth_image.png)

 N> Default value of BorderWidth 
    Android : [`0d`]
    iOS : [`0d`]
    UWP : [`2d`]

## CornerRadius

The `CornerRadius` property is used to customize the rounded edges in SfChip as demonstrated in the following code sample.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            BorderWidth="4"
                            CornerRadius = "4"
                            BorderColor="Black"
                            >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.BorderWidth = 4;
            chip.CornerRadius = 4;
            chip.BorderColor = Color.Black;
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with CornerRadius](images/customization-images/chip_cornerradius_image.png)

N> The default value of CornerRadius is [`Thickness(0)`].

## FontAttributes

The [`FontAttributes`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_FontAttributes) property customizes the font style of text in SfChip.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            ShowCloseButton="true"
                            ShowSelectionIndicator="true"
                            CloseButtonColor = "White"
                            SelectionIndicatorColor = "White"
                            FontAttributes="Italic" >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.ShowSelectionIndicator = true;
            chip.CloseButtonColor = Color.White;
            chip.SelectionIndicatorColor = Color.White;
            chip.FontAttributes = FontAttributes.Italic;
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with FontAttributes](images/customization-images/chip_fontattribute_image.png)

## FontFamily

The [`FontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_FontFamily) property customizes the font family of text in SfChip.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            ShowCloseButton="true"
                            ShowSelectionIndicator="true"
                            CloseButtonColor = "White"
                            SelectionIndicatorColor = "White"
                            FontFamily="Arial"
                            >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.ShowSelectionIndicator = true;
            chip.CloseButtonColor = Color.White;
            chip.SelectionIndicatorColor = Color.White;
            chip.FontFamily = "Arial";
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with FontFamily](images/customization-images/chipfontfamily_image.png)

## FontSize

The [`FontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_FontSize) property customizes the size of text in SfChip.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            ShowCloseButton="true"
                            ShowSelectionIndicator="true"
                            CloseButtonColor = "White"
                            SelectionIndicatorColor = "White"
                            FontSize = "10"
                            >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.ShowSelectionIndicator = true;
            chip.CloseButtonColor = Color.White;
            chip.SelectionIndicatorColor = Color.White;
            chip.FontSize = 10;
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with FontSize](images/customization-images/chip_fontsize_image.png)

N> Default Value of FontSize 
   Android : [`14d`]
   iOS : [`15d`]
   UWP : [`15d`]

## TextColor

The [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_TextColor) property customizes the color of text in SfChip.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            ShowCloseButton="true"
                            ShowSelectionIndicator="true"
                            CloseButtonColor = "White"
                            SelectionIndicatorColor = "White"
                            BackgroundColor="Aqua"
                            TextColor="Black"
                            >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.ShowSelectionIndicator = true;
            chip.CloseButtonColor = Color.White;
            chip.SelectionIndicatorColor = Color.White;
            chip.BackgroundColor = Color.Aqua;
            chip.TextColor = Color.Black;
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with TextColor](images/customization-images/chip_textcolor_image.png)

N> The default value of TextColor is [`Color.White`].

## TextAlignment

The [`HorizontalTextAlignment `](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_HorizontalTextAlignment) and [`VerticalTextAlignment `](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_VerticalTextAlignment) properties customize the alignment of text in SfChip.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            ShowSelectionIndicator="true"
                            SelectionIndicatorColor = "White"
                            BackgroundColor="Aqua"
                            HorizontalTextAlignment="Start"
                            VerticalTextAlignment="Start"
                            TextColor="Black"
                            >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.ShowSelectionIndicator = true;
            chip.SelectionIndicatorColor = Color.White;
            chip.BackgroundColor = Color.Aqua;
            chip.HorizontalTextAlignment = TextAlignment.Start;
            chip.VerticalTextAlignment = TextAlignment.Start;
            chip.TextColor = Color.Black;
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with TextAlignment](images/customization-images/chip_textalignment_image.png)

N> The default values of HorizontalTextAlignment and VerticalTextAlignment are [`TextAlignment.Center`].

## ShowIcon

You can enable the icon image using the [`ShowIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ShowIcon) property to know whether any image appears to the SfChip.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            BackgroundColor="Aqua"
                            TextColor="Black"
                            ImageSource="ChipUserContact.png"
                            ShowIcon="true"
                            >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.BackgroundColor = Color.Aqua;
            chip.TextColor = Color.Black;
            chip.ImageSource = "ChipUserContact.png";
            chip.ShowIcon = true;
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with ShowIcon](images/customization-images/chip_imagesource_image.png)

N> The default value of ShowIcon is [`false`].

## ImageSource

The [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) property customizes the icon image of SfChip by adding a custom image.

N> Enable the [`ShowIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ShowIcon) property to enable the [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) property.


{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            BackgroundColor="Aqua"
                            TextColor="Black"
                            ImageSource="ChipUserContact.png"
                            ShowIcon="true"
                            >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.BackgroundColor = Color.Aqua;
            chip.TextColor = Color.Black;
            chip.ImageSource = "ChipUserContact.png";
            chip.ShowIcon = true;
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with ImageSource](images/customization-images/chip_imagesource_image.png)

## ImageWidth

The [`ImageWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageWidth) property customizes the width of icon image in SfChip.

N> Enable the [`ShowIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ShowIcon) property to enable the [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) property.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            BackgroundColor="Aqua"
                            TextColor="Black"
                            ImageSource="ChipUserContact.png"
                            ImageWidth="25"
                            ShowIcon="true"
                            >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.BackgroundColor = Color.Aqua;
            chip.TextColor = Color.Black;
            chip.ImageSource = "ChipUserContact.png";
            chip.ImageWidth = 25;
            chip.ShowIcon = true;
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with ImageWidth](images/customization-images/chip_imagewidth_image.png)

N> The default value of ImageWidth is [`32`].

## ImageAlignment 

The [`ImageAlignment`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageAlignment) property customizes the alignment of icon image in SfChip.

N> Enable the [`ShowIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ShowIcon) property to enable the [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) property.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
  
   <ContentPage.Content>
        <StackLayout Margin="8,8,8,8" >
           <buttons:SfChip  Text="James" 
                            WidthRequest="150"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            BackgroundColor="Aqua"
                            TextColor="Black"
                            ImageSource="ChipUserContact.png"
                            ImageAlignment="End"
                            ImageWidth="25"
                            ShowIcon="true"
                            >
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfChip chip = new SfChip();
            chip.Text = "James";
            chip.WidthRequest = 150;
            chip.HorizontalOptions = LayoutOptions.Center;
            chip.VerticalOptions = LayoutOptions.Center;
            chip.BackgroundColor = Color.Aqua;
            chip.TextColor = Color.Black;
            chip.ImageSource = "ChipUserContact.png";
            chip.ImageAlignment = Alignment.End;
            chip.ImageWidth = 25;
            chip.ShowIcon = true;
            stackLayout.Children.Add(chip);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChip with ImageAlignment](images/customization-images/chip_imagealignment_image.png)

N> The default value of ImageAlignment is [`Alignment.Start`].

## Command

The [`Command`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_Command) property associates a command with an instance of SfChip. This property is most often set with MVVM pattern to bind callbacks back into the ViewModel.

{% tabs %}

{% highlight xaml %}

 <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
 
   <ContentPage.BindingContext>
       <local:CommandDemoViewModel />
   </ContentPage.BindingContext>

   <ContentPage.Content>
        <StackLayout Margin="8,8,0,0">
            <buttons:SfChip x:Name="Chip" 
                            Text="Chip"
                            HorizontalOptions="Center"
                            VerticalOptions="Center"
                            WidthRequest="150"
                            ShowCloseButton="true"
                            BackgroundColor="{Binding Background}"
                            Command="{Binding ButtonCommand}">

           
           </buttons:SfChip>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

// ViewModel class for Command Demo.

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

![SfChip with Command](images/customization-images/chip_command_image.png)

N> The default value of Command is [`null`].

## Customization of SfChipGroup

The chip group supports to customize the chip's background color, border color, text color, and more. The chip group can be customized using the following properties:

## InputView

The [`InputView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_InputView) property allows to provide a view to the input chip. In this example, the input chip is used to add an employee at run time. To get the employee name as input, an entry is added as InputView.

{% tabs %}

{% highlight xaml %}

<ContentPage
xmlns="http://xamarin.com/schemas/2014/forms"
xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
xmlns:local="clr-namespace:Chips"
x:Class="Chips.GettingStarted">
	<ContentPage.BindingContext>
		<local:ViewModel x:Name="viewModel"/>
	</ContentPage.BindingContext>
	<ContentPage.Content>
	<buttons:SfChipGroup 
		x:Name="chipGroup" 
		ItemsSource="{Binding Employees}"
		ChipPadding="8,8,0,0" 
		DisplayMemberPath="Name">
		<buttons:SfChipGroup.ChipLayout>
				<FlexLayout 
				HorizontalOptions="Start" 
				VerticalOptions="Center"
				Direction="Row"
				Wrap="Wrap" 
				JustifyContent="Start" 
				AlignContent="Start" 
				AlignItems="Start"/>
		</buttons:SfChipGroup.ChipLayout>
		<buttons:SfChipGroup.InputView>
			<Entry 
				Margin="10,10,0,0" 
				WidthRequest="110"
				Completed="Entry_Completed"/>
		</buttons:SfChipGroup.InputView>
	</buttons:SfChipGroup>
	</ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace Chips
{
	public partial class GettingStarted: ContentPage
	{
		public GettingStarted()
		{
			InitializeComponent();
			Grid grid = new Grid();
			SfChipGroup chipGroup = new SfChipGroup();
			grid.Children.Add(chipGroup);
			FlexLayout layout = new FlexLayout()
			{
				Direction = FlexDirection.Row,
				Wrap = FlexWrap.Wrap,
				HorizontalOptions = LayoutOptions.Start,
				VerticalOptions = LayoutOptions.Center,
				AlignContent = FlexAlignContent.Start,
				JustifyContent = FlexJustify.Start,
				AlignItems = FlexAlignItems.Start,
			};
			var entry= new Entry { Margin = new Thickness(10, 10, 0, 0), WidthRequest = 110 };
			entry.Completed += Entry_Completed;
			chipGroup.InputView = entry;
			chipGroup.ChipLayout = layout;
			this.BindingContext = new ViewModel();
			chipGroup.SetBinding(SfChipGroup.ItemsSourceProperty, "Employees");
			chipGroup.DisplayMemberPath = "Name";
			chipGroup.ChipPadding = new Thickness(8, 8, 0, 0);
			this.Content = grid;
		}
	}
}
{% endhighlight %}

{% endtabs %}

![SfChipGroup with InputView](images/customization-images/chipgroup_inputview_image.png)

N> The InputView is visible only in the Input type. The default value of InputView is [`null`].

## SelectedChipBackgroundColor

The [`SelectedChipBackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_SelectedChipBackgroundColor) property customizes the background color of the selected chip.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
 
 <ContentPage.BindingContext>
        <local:ViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <StackLayout Margin="10,10,10,10">
            <buttons:SfChipGroup
                ItemsSource="{Binding Employees}"
                DisplayMemberPath="Name"
                SelectedChipBackgroundColor="Fuchsia"
                Type="Choice">
            </buttons:SfChipGroup>
        </StackLayout>  
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stack = new StackLayout();
            SfChipGroup chipGroup = new SfChipGroup();
            stack.Children.Add(chipGroup);
            FlexLayout layout = new FlexLayout()
            {
                Direction = FlexDirection.Row,
                Wrap = FlexWrap.Wrap,
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Center,
                AlignContent = FlexAlignContent.Start,
                JustifyContent = FlexJustify.Start,
                AlignItems = FlexAlignItems.Start,
            };
           
            chipGroup.ChipLayout = layout;
            this.BindingContext = new ViewModel();
            chipGroup.SetBinding(SfChipGroup.ItemsSourceProperty, "Employees");
            chipGroup.DisplayMemberPath = "Name";
            chipGroup.SelectedChipBackgroundColor = Color.Fuchsia;
            chipGroup.Type = SfChipsType.Choice;
            this.Content = stack;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChipGroup with SelectedChipBackgroundColor](images/customization-images/chipgroup_selectedchipbackgroundcolor_image.png)

N> The default value of SelectedChipBackgroundColor is [`Color.Accent`].

## SelectedChipTextColor

The [`SelectedChipTextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_SelectedChipTextColor) property customizes the text color of the selected chip.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
 
 <ContentPage.BindingContext>
        <local:ViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <StackLayout Margin="10,10,10,10">
            <buttons:SfChipGroup
                ItemsSource="{Binding Employees}"
                DisplayMemberPath="Name"
                SelectedChipBackgroundColor="White"
                SelectedChipTextColor="Fuchsia"
                Type="Choice">
            </buttons:SfChipGroup>
        </StackLayout>  
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stack = new StackLayout();
            SfChipGroup chipGroup = new SfChipGroup();
            stack.Children.Add(chipGroup);
            FlexLayout layout = new FlexLayout()
            {
                Direction = FlexDirection.Row,
                Wrap = FlexWrap.Wrap,
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Center,
                AlignContent = FlexAlignContent.Start,
                JustifyContent = FlexJustify.Start,
                AlignItems = FlexAlignItems.Start,
            };
           
            chipGroup.ChipLayout = layout;
            this.BindingContext = new ViewModel();
            chipGroup.SetBinding(SfChipGroup.ItemsSourceProperty, "Employees");
            chipGroup.DisplayMemberPath = "Name";
            chipGroup.SelectedChipBackgroundColor = Color.White;
            chipGroup.SelectedChipTextColor = Color.Fuchsia;
            chipGroup.Type = SfChipsType.Choice;
            this.Content = stack;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChipGroup with SelectedChipTextColor](images/customization-images/chipgroup_selectedchiptextcolor_image.png)

N> The default value of SelectedChipTextColor is [`Color.White`].

## ChipBackgroundColor

The [`ChipBackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_ChipBackgroundColor) property customizes the background color of the SfChipGroup.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
 
 <ContentPage.BindingContext>
        <local:ViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <StackLayout Margin="10,10,10,10">
            <buttons:SfChipGroup
                ItemsSource="{Binding Employees}"
                DisplayMemberPath="Name"
                ChipBackgroundColor="Aqua"
                Type="Choice">
            </buttons:SfChipGroup>
        </StackLayout>  
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stack = new StackLayout();
            SfChipGroup chipGroup = new SfChipGroup();
            stack.Children.Add(chipGroup);
            FlexLayout layout = new FlexLayout()
            {
                Direction = FlexDirection.Row,
                Wrap = FlexWrap.Wrap,
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Center,
                AlignContent = FlexAlignContent.Start,
                JustifyContent = FlexJustify.Start,
                AlignItems = FlexAlignItems.Start,
            };
           
            chipGroup.ChipLayout = layout;
            this.BindingContext = new ViewModel();
            chipGroup.SetBinding(SfChipGroup.ItemsSourceProperty, "Employees");
            chipGroup.DisplayMemberPath = "Name";
            chipGroup.ChipBackgroundColor = Color.Aqua;
            chipGroup.Type = SfChipsType.Choice;
            this.Content = stack;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChipGroup with ChipBackgroundColor](images/customization-images/chipgroup_chipbackgroundcolor_image.png)

N> The default value of ChipBackgroundColor is [`Color.FromHex("#E0E0E0")`].

## ChipBorderColor

The [`ChipBorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_ChipBorderColor) property customizes the border color of the SfChipGroup.

{% tabs %}

{% highlight xaml %}

 <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
 
 <ContentPage.BindingContext>
        <local:ViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <StackLayout Margin="10,10,10,10">
            <buttons:SfChipGroup
                ItemsSource="{Binding Employees}"
                DisplayMemberPath="Name"
                ChipBorderWidth="5" 
                ChipBorderColor="Black"
                ChipBackgroundColor="Aqua">
            </buttons:SfChipGroup>
        </StackLayout>  
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stack = new StackLayout();
            SfChipGroup chipGroup = new SfChipGroup();
            stack.Children.Add(chipGroup);
            FlexLayout layout = new FlexLayout()
            {
                Direction = FlexDirection.Row,
                Wrap = FlexWrap.Wrap,
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Center,
                AlignContent = FlexAlignContent.Start,
                JustifyContent = FlexJustify.Start,
                AlignItems = FlexAlignItems.Start,
            };
           
            chipGroup.ChipLayout = layout;
            this.BindingContext = new ViewModel();
            chipGroup.SetBinding(SfChipGroup.ItemsSourceProperty, "Employees");
            chipGroup.DisplayMemberPath = "Name";
            chipGroup.ChipBorderWidth = 5;
            chipGroup.ChipBorderColor = Color.Black;
            chipGroup.ChipBackgroundColor = Color.Aqua;
            this.Content = stack;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChipGroup with ChipBorderColor](images/customization-images/chipgroup_chipbordercolor_image.png)

N> The default value of ChipBorderColor is [`Color.Transparent`].

## ChipTextColor

The [`ChipTextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_ChipTextColor) property customizes the text color of the SfChipGroup.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
 
 <ContentPage.BindingContext>
        <local:ViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <StackLayout Margin="10,10,10,10">
            <buttons:SfChipGroup
                ItemsSource="{Binding Employees}"
                DisplayMemberPath="Name"
                ChipTextColor="Blue">
            </buttons:SfChipGroup>
            <buttons:SfChipGroup.ChipLayout>
                    <FlexLayout 
                        HorizontalOptions="Start" 
                        VerticalOptions="Center" 
                        Direction="Row" 
                        Wrap="Wrap"
                        JustifyContent="Start"
                        AlignContent="Start" 
                        AlignItems="Start"/>
                </buttons:SfChipGroup.ChipLayout>
        </StackLayout>  
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stack = new StackLayout();
            SfChipGroup chipGroup = new SfChipGroup();
            stack.Children.Add(chipGroup);
            FlexLayout layout = new FlexLayout()
            {
                Direction = FlexDirection.Row,
                Wrap = FlexWrap.Wrap,
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Center,
                AlignContent = FlexAlignContent.Start,
                JustifyContent = FlexJustify.Start,
                AlignItems = FlexAlignItems.Start,
            };
           
            chipGroup.ChipLayout = layout;
            this.BindingContext = new ViewModel();
            chipGroup.SetBinding(SfChipGroup.ItemsSourceProperty, "Employees");
            chipGroup.DisplayMemberPath = "Name";
            chipGroup.ChipTextColor = Color.Blue;
            this.Content = stack;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChipGroup with ChipTextColor](images/customization-images/chipgroup_chiptextcolor_image.png)

N> The default value of ChipTextColor is [`Color.FromHex("#212121")`].

## ChipTextSize

The [`ChipTextSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_ChipTextSize) property customizes the text size of the SfChipGroup.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
 
 <ContentPage.BindingContext>
        <local:ViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <StackLayout Margin="8,8,0,0">
            <buttons:SfChipGroup
                ItemsSource="{Binding Employees}"
                DisplayMemberPath="Name"
                ChipTextSize="10">
            </buttons:SfChipGroup>
            <buttons:SfChipGroup.ChipLayout>
                    <FlexLayout 
                        HorizontalOptions="Start" 
                        VerticalOptions="Center" 
                        Direction="Row" 
                        Wrap="Wrap"
                        JustifyContent="Start"
                        AlignContent="Start" 
                        AlignItems="Start"/>
                </buttons:SfChipGroup.ChipLayout>
        </StackLayout>  
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stack = new StackLayout();
            SfChipGroup chipGroup = new SfChipGroup();
            stack.Children.Add(chipGroup);
            FlexLayout layout = new FlexLayout()
            {
                Direction = FlexDirection.Row,
                Wrap = FlexWrap.Wrap,
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Center,
                AlignContent = FlexAlignContent.Start,
                JustifyContent = FlexJustify.Start,
                AlignItems = FlexAlignItems.Start,
            };
           
            chipGroup.ChipLayout = layout;
            this.BindingContext = new ViewModel();
            chipGroup.SetBinding(SfChipGroup.ItemsSourceProperty, "Employees");
            chipGroup.DisplayMemberPath = "Name";
            chipGroup.ChipTextSize = 10;
            this.Content = stack;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChipGroup with ChipTextSize](images/customization-images/chipgroup_chiptextsize_image.png)

N> The default value of ChipTextSize is [`14d`].

## ChipPadding

The [`ChipPadding`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_ChipPadding) property sets spacing between each chip.

{% tabs %}

{% highlight xaml %}

  <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
 
 <ContentPage.BindingContext>
        <local:ViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <StackLayout Margin="8,8,0,0">
            <buttons:SfChipGroup
                ItemsSource="{Binding Employees}"
                DisplayMemberPath="Name"
                ChipPadding="8,0,0,0">
            </buttons:SfChipGroup>
            <buttons:SfChipGroup.ChipLayout>
                    <FlexLayout 
                        HorizontalOptions="Start" 
                        VerticalOptions="Center" 
                        Direction="Row" 
                        Wrap="Wrap"
                        JustifyContent="Start"
                        AlignContent="Start" 
                        AlignItems="Start"/>
                </buttons:SfChipGroup.ChipLayout>
        </StackLayout>  
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stack = new StackLayout();
            SfChipGroup chipGroup = new SfChipGroup();
            stack.Children.Add(chipGroup);
            FlexLayout layout = new FlexLayout()
            {
                Direction = FlexDirection.Row,
                Wrap = FlexWrap.Wrap,
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Center,
                AlignContent = FlexAlignContent.Start,
                JustifyContent = FlexJustify.Start,
                AlignItems = FlexAlignItems.Start,
            };
           
            chipGroup.ChipLayout = layout;
            this.BindingContext = new ViewModel();
            chipGroup.SetBinding(SfChipGroup.ItemsSourceProperty, "Employees");
            chipGroup.ChipPadding = new Thickness(8, 8, 0, 0);
            chipGroup.DisplayMemberPath = "Name";
            this.Content = stack;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChipGroup with ChipPadding](images/customization-images/chipgroup_chippadding_image.png)
	
N> The default value of ChipPadding is [`Thickness(5d, 0, 0, 0)`].

## ChipBorderWidth

The [`ChipBorderWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_ChipBorderWidth) property customizes the border width of the SfChipGroup.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
 
 <ContentPage.BindingContext>
        <local:ViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <StackLayout Margin="8,8,0,0">
            <buttons:SfChipGroup
                ItemsSource="{Binding Employees}"
                ChipBorderWidth="5" 
                DisplayMemberPath="Name"
                ChipBorderColor="Black">
            </buttons:SfChipGroup>
            <buttons:SfChipGroup.ChipLayout>
                    <FlexLayout 
                        HorizontalOptions="Start" 
                        VerticalOptions="Center" 
                        Direction="Row" 
                        Wrap="Wrap"
                        JustifyContent="Start"
                        AlignContent="Start" 
                        AlignItems="Start"/>
                </buttons:SfChipGroup.ChipLayout>
        </StackLayout>  
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stack = new StackLayout();
            SfChipGroup chipGroup = new SfChipGroup();
            stack.Children.Add(chipGroup);
            FlexLayout layout = new FlexLayout()
            {
                Direction = FlexDirection.Row,
                Wrap = FlexWrap.Wrap,
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Center,
                AlignContent = FlexAlignContent.Start,
                JustifyContent = FlexJustify.Start,
                AlignItems = FlexAlignItems.Start,
            };
           
            chipGroup.ChipLayout = layout;
            this.BindingContext = new ViewModel();
            chipGroup.SetBinding(SfChipGroup.ItemsSourceProperty, "Employees");
            chipGroup.ChipBorderWidth = 5;
            chipGroup.ChipBorderColor = Color.Black;
            chipGroup.DisplayMemberPath = "Name";
            this.Content = stack;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChipGroup with ChipBorderWidth](images/customization-images/chipgroup_chipborderwidth_image.png)

N> The default value of ChipBorderWidth is [`0d`].

## ItemHeight

The [`ItemHeight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_ItemHeight) property customizes the height of the items in the SfChipGroup.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
 
 <ContentPage.BindingContext>
        <local:ViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <StackLayout Margin="8,8,0,0">
            <buttons:SfChipGroup
                ItemsSource="{Binding Employees}"
                ItemHeight="60"
                DisplayMemberPath="Name">
            </buttons:SfChipGroup>
            <buttons:SfChipGroup.ChipLayout>
                    <FlexLayout 
                        HorizontalOptions="Start" 
                        VerticalOptions="Center" 
                        Direction="Row" 
                        Wrap="Wrap"
                        JustifyContent="Start"
                        AlignContent="Start" 
                        AlignItems="Start"/>
                </buttons:SfChipGroup.ChipLayout>
        </StackLayout>  
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stack = new StackLayout();
            SfChipGroup chipGroup = new SfChipGroup();
            stack.Children.Add(chipGroup);
            FlexLayout layout = new FlexLayout()
            {
                Direction = FlexDirection.Row,
                Wrap = FlexWrap.Wrap,
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Center,
                AlignContent = FlexAlignContent.Start,
                JustifyContent = FlexJustify.Start,
                AlignItems = FlexAlignItems.Start,
            };
           
            chipGroup.ChipLayout = layout;
            this.BindingContext = new ViewModel();
            chipGroup.SetBinding(SfChipGroup.ItemsSourceProperty, "Employees");
            chipGroup.ItemHeight = 60;
            chipGroup.DisplayMemberPath = "Name";
            this.Content = stack;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChipGroup with ItemHeight](images/customization-images/chipgroup_itemheight_image.png)

N> The default value of ItemHeight is [`double.NaN`].

## ShowIcon

You can enable the icon image using the [`ShowIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_ShowIcon) property to know whether any image appears on the SfChipGroup.

{% tabs %}

{% highlight xaml %}

 <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
 
<ContentPage.BindingContext>
        <local:ViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <Grid>
            <buttons:SfChipGroup 
                ItemsSource="{Binding Employees}" 
                ChipPadding="8,8,0,0" 
                ImageMemberPath="Image"
                ShowIcon="true"
                ChipBackgroundColor="Aqua"
                DisplayMemberPath="Name">
                <buttons:SfChipGroup.ChipLayout>
                    <FlexLayout 
                        HorizontalOptions="Start" 
                        VerticalOptions="Center" 
                        Direction="Row" 
                        Wrap="Wrap"
                        JustifyContent="Start"
                        AlignContent="Start" 
                        AlignItems="Start"/>
                </buttons:SfChipGroup.ChipLayout>
            </buttons:SfChipGroup>  
        </Grid>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stack = new StackLayout();
            SfChipGroup chipGroup = new SfChipGroup();
            stack.Children.Add(chipGroup);
            FlexLayout layout = new FlexLayout()
            {
                Direction = FlexDirection.Row,
                Wrap = FlexWrap.Wrap,
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Center,
                AlignContent = FlexAlignContent.Start,
                JustifyContent = FlexJustify.Start,
                AlignItems = FlexAlignItems.Start,
            };
           
            chipGroup.ChipLayout = layout;
            this.BindingContext = new ViewModel();
            chipGroup.SetBinding(SfChipGroup.ItemsSourceProperty, "Employees");
            chipGroup.DisplayMemberPath = "Name";
            chipGroup.ImageMemberPath = "Image";
            chipGroup.ChipImageWidth = 30;
            chipGroup.SelectionIndicatorColor = Color.Black;
            chipGroup.CloseButtonColor = Color.White;
            chipGroup.ChipBackgroundColor = Color.Aqua;
            chipGroup.Type = SfChipsType.Input;
            chipGroup.ShowIcon = true;
            chipGroup.ChipPadding = new Thickness(8, 8, 0, 0);
            this.Content = stack;
        }
    }
    public class Person
    {
        public string Name
        {
            get;
            set;
        }

        public string Image
        {
            get;
            set;
        }
    }
    public class ViewModel : INotifyPropertyChanged
    {
        private ObservableCollection<Person> employees;
        public ObservableCollection<Person> Employees
        {
            get
            {
                return employees;
            }
            set
            {
                Employees = value;
                OnPropertyChanged("Employees");
            }
        }

        public ViewModel()
        {
            employees = new ObservableCollection<Person>();
            employees.Add(new Person() { Image = "ChipUserContact.png", Name = "John" });
            employees.Add(new Person() { Image = "ChipUserContact.png", Name = "James" });
        }

        public event PropertyChangedEventHandler PropertyChanged;

        public void OnPropertyChanged(string property)
        {
            if (PropertyChanged != null)
            {
                PropertyChanged(this, new PropertyChangedEventArgs(property));
            }
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChipGroup with ShowIcon](images/customization-images/chipgroup_showicon_image.png)

## CloseButtonColor

The [`CloseButtonColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_CloseButtonColor) property customizes the color of close button in the SfChipGroup.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
 
<ContentPage.BindingContext>
        <local:ViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <StackLayout Margin="8,8,0,0">
            <buttons:SfChipGroup 
                ItemsSource="{Binding Employees}" 
                ImageMemberPath="Image"
                Type="Input"
                ChipImageWidth="30"
                ShowIcon="true"
                CloseButtonColor="White"
                ChipBackgroundColor="Aqua"
                DisplayMemberPath="Name">
                <buttons:SfChipGroup.ChipLayout>
                    <FlexLayout 
                        HorizontalOptions="Start" 
                        VerticalOptions="Center" 
                        Direction="Row" 
                        Wrap="Wrap"
                        JustifyContent="Start"
                        AlignContent="Start" 
                        AlignItems="Start"/>
                </buttons:SfChipGroup.ChipLayout>
            </buttons:SfChipGroup>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
             StackLayout stack = new StackLayout();
            SfChipGroup chipGroup = new SfChipGroup();
            stack.Children.Add(chipGroup);
            FlexLayout layout = new FlexLayout()
            {
                Direction = FlexDirection.Row,
                Wrap = FlexWrap.Wrap,
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Center,
                AlignContent = FlexAlignContent.Start,
                JustifyContent = FlexJustify.Start,
                AlignItems = FlexAlignItems.Start,
            };
           
            chipGroup.ChipLayout = layout;
            this.BindingContext = new ViewModel();
            chipGroup.SetBinding(SfChipGroup.ItemsSourceProperty, "Employees");
            chipGroup.DisplayMemberPath = "Name";
            chipGroup.ImageMemberPath = "Image";
            chipGroup.ChipImageWidth = 30;
            chipGroup.SelectionIndicatorColor = Color.Black;
            chipGroup.CloseButtonColor = Color.White;
            chipGroup.ChipBackgroundColor = Color.Aqua;
            chipGroup.Type = SfChipsType.Input;
            chipGroup.ShowIcon = true;
            this.Content = stack;
        }
    }
} 

{% endhighlight %}

{% endtabs %}

N> The default value of CloseButtonColor is [`Color.Black`].

## SelectionIndicatorColor

The [`SelectionIndicatorColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_SelectionIndicatorColor) property customizes the selection indicator color of the SfChipGroup.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
 
<ContentPage.BindingContext>
        <local:ViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <StackLayout Margin="8,8,0,0">
            <buttons:SfChipGroup 
                ItemsSource="{Binding Employees}" 
                Type="Filter"
                SelectionIndicatorColor="Black"
                CloseButtonColor="White"
                ChipBackgroundColor="Aqua"
                DisplayMemberPath="Name">
                <buttons:SfChipGroup.ChipLayout>
                    <FlexLayout 
                        HorizontalOptions="Start" 
                        VerticalOptions="Center" 
                        Direction="Row" 
                        Wrap="Wrap"
                        JustifyContent="Start"
                        AlignContent="Start" 
                        AlignItems="Start"/>
                </buttons:SfChipGroup.ChipLayout>
            </buttons:SfChipGroup>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stack = new StackLayout();
            SfChipGroup chipGroup = new SfChipGroup();
            stack.Children.Add(chipGroup);
            FlexLayout layout = new FlexLayout()
            {
                Direction = FlexDirection.Row,
                Wrap = FlexWrap.Wrap,
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Center,
                AlignContent = FlexAlignContent.Start,
                JustifyContent = FlexJustify.Start,
                AlignItems = FlexAlignItems.Start,
            };
           
            chipGroup.ChipLayout = layout;
            this.BindingContext = new ViewModel();
            chipGroup.SetBinding(SfChipGroup.ItemsSourceProperty, "Employees");
            chipGroup.DisplayMemberPath = "Name";
            chipGroup.SelectionIndicatorColor = Color.Black;
            chipGroup.CloseButtonColor = Color.White;
            chipGroup.ChipBackgroundColor = Color.Aqua;
            chipGroup.Type = SfChipsType.Filter;
            this.Content = stack;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChipGroup with SelectionIndicatorColor](images/customization-images/chipgroup_selectionindicatorcolor_image.png)

N> The default value of SelectionIndicatorColor is [`Color.White`].

## ChipImageWidth

The [ChipImageWidth](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_ChipImageWidth) property customizes the width of icon image in the SfChipGroup.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ChipCustomization"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="ChipCustomization.MainPage">
 
<ContentPage.BindingContext>
        <local:ViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <StackLayout Margin="8,8,0,0">
            <buttons:SfChipGroup 
                ItemsSource="{Binding Employees}" 
                ImageMemberPath="Image"
                Type="Choice"
                ChipImageWidth="30"
                ShowIcon="true"
                ChipBackgroundColor="Aqua"
                DisplayMemberPath="Name">
                <buttons:SfChipGroup.ChipLayout>
                    <FlexLayout 
                        HorizontalOptions="Start" 
                        VerticalOptions="Center" 
                        Direction="Row" 
                        Wrap="Wrap"
                        JustifyContent="Start"
                        AlignContent="Start" 
                        AlignItems="Start"/>
                </buttons:SfChipGroup.ChipLayout>
            </buttons:SfChipGroup>  
        </StackLayout>
    </ContentPage.Content>
    
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;
using System.ComponentModel;
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace ChipCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stack = new StackLayout();
            SfChipGroup chipGroup = new SfChipGroup();
            stack.Children.Add(chipGroup);
            FlexLayout layout = new FlexLayout()
            {
                Direction = FlexDirection.Row,
                Wrap = FlexWrap.Wrap,
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Center,
                AlignContent = FlexAlignContent.Start,
                JustifyContent = FlexJustify.Start,
                AlignItems = FlexAlignItems.Start,
            };
           
            chipGroup.ChipLayout = layout;
            this.BindingContext = new ViewModel();
            chipGroup.SetBinding(SfChipGroup.ItemsSourceProperty, "Employees");
            chipGroup.DisplayMemberPath = "Name";
            chipGroup.ImageMemberPath = "Image";
            chipGroup.ChipImageWidth = 30;
            chipGroup.ChipBackgroundColor = Color.Aqua;
            chipGroup.Type = SfChipsType.Choice;
            chipGroup.ShowIcon = true;
            this.Content = stack;
        }
    }

// Model Class

    public class Person
    {
        public string Name
        {
            get;
            set;
        }

        public string Image
        {
            get;
            set;
        }
    }

  //ViewModel Class

    public class ViewModel : INotifyPropertyChanged
    {
        private ObservableCollection<Person> employees;
        public ObservableCollection<Person> Employees
        {
            get
            {
                return employees;
            }
            set
            {
                Employees = value;
                OnPropertyChanged("Employees");
            }
        }

        public ViewModel()
        {
            employees = new ObservableCollection<Person>();
            employees.Add(new Person() { Image = "ChipUserContact.png", Name = "John" });
            employees.Add(new Person() { Image = "ChipUserContact.png", Name = "James" });
        }

        public event PropertyChangedEventHandler PropertyChanged;

        public void OnPropertyChanged(string property)
        {
            if (PropertyChanged != null)
            {
                PropertyChanged(this, new PropertyChangedEventArgs(property));
            }
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SfChipGroup with ChipImageWidth](images/customization-images/chipgroup_chipimagewidth_image.png)

N> The default value of ChipImageWidth is [`26`].

## See also

[How to customize the corner radius of ChipGroup items in Xamarin.Forms](https://www.syncfusion.com/kb/11282/how-to-customize-the-corner-radius-of-chipgroup-items-in-xamarin-forms)

[How to remove the indicator icon from Xamarin.Forms chip group (SfChipGroup)](https://www.syncfusion.com/kb/11270/how-to-remove-the-indicator-icon-from-xamarin-forms-chip-group-sfchipgroup)

[How to restrict chip selection in Xamarin](https://www.syncfusion.com/kb/11205/how-to-restrict-chip-selection-in-xamarin)

[How to select a multiple chips from the Xamarin ChipGroup [SfChipGroup]](https://www.syncfusion.com/kb/11155/how-to-select-a-multiple-chips-from-the-xamarin-chipgroup-sfchipgroup)

[How to display each chip in different colors in the Xamarin.Forms ChipGroup](https://www.syncfusion.com/kb/10940/how-to-display-each-chip-in-different-colors-in-the-xamarin-forms-chipgroup)
