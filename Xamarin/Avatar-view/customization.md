---
layout: post
title: Customization in Syncfusion AvatarView Xamarin.Forms
description: This section will explain about how to achieve the customization of default View in Xamarin.Forms SfAvatarView.
platform: Xamarin
control: AvatarView
documentation: ug
---

# Customization in Xamarin Avatar View(SfAvatarView)

## Customization in Xamarin Avatar View(SfAvatarView)

The [`SfAvatarView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html) control provides options to customize the color and size. The control can be customized using the following properties:

## Colors

Color in the [`SfAvatarView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html) can be customized by the border color, the default background color, and automatic background color.

### Border color

The border color is used for setting color to the border of [`SfAvatarView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html) using the [`BorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Border.SfBorder.html#Syncfusion_XForms_Border_SfBorder_BorderColor) property.

{% tabs %}

{% highlight xaml %}

   <Grid>
        <sfavatar:SfAvatarView  ContentType="Default"  
                                AvatarShape="Circle"
                                AvatarSize="Large"
                                HorizontalOptions="Center"
                                VerticalOptions="Center"
                                ImageSource="ellanaa.png"
                                BorderColor="Red">
        </sfavatar:SfAvatarView>
   </Grid>

{% endhighlight %}

{% highlight c# %}

            Grid mainGrid = new Grid();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.ContentType = ContentType.Default;
            avatarview.AvatarShape = AvatarShape.Circle;
            avatarview.AvatarSize = AvatarSize.Large;
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.ImageSource = "ellanaa.png";
            avatarview.BorderColor = Color.Red;
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;

{% endhighlight %}

{% endtabs %}

![AvatarControl Border Color](images/BorderColor_AvatarView.png)

### Default background color

The background color for the [`SfAvatarView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html) control can be set using the [`AvatarColorMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_AvatarColorMode) property. When the [`AvatarColorMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_AvatarColorMode) property is set to default, it displays the background color set in the [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_BackgroundColor) property.

{% tabs %}

{% highlight xaml %}

   <Grid>
        <sfavatar:SfAvatarView ContentType="Initials"
                               AvatarShape="Circle"
                               AvatarSize="Large"
                               HorizontalOptions="Center"
                               VerticalOptions="Center"
                               AvatarName="Alex"          
                               BackgroundColor="Bisque"
                               AvatarColorMode="Default"
                               BorderColor="Black">
        </sfavatar:SfAvatarView>
   </Grid>
      

{% endhighlight %}

{% highlight c# %}

            Grid mainGrid = new Grid();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.ContentType = ContentType.Initials;
            avatarview.AvatarShape = AvatarShape.Circle;
            avatarview.AvatarSize = AvatarSize.Large;
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.AvatarName = "Alex";
            avatarview.BorderColor = Color.Black;
            avatarview.AvatarColorMode = AvatarColorMode.Default;
            avatarview.BackgroundColor = Color.Bisque;
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;

{% endhighlight %}

{% endtabs %}

![Default background color](images/Default_Background_AvatarView.png)

### Automatic background color

The [`SfAvatarView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html) control allows automatic background color while initializing. It contains the following properties:

* [`DarkBackground`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.AvatarColorMode.html#Syncfusion_XForms_AvatarView_AvatarColorMode_DarkBackground): Shows a dark color for the initials and background color.
* [`LightBackground`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.AvatarColorMode.html#Syncfusion_XForms_AvatarView_AvatarColorMode_LightBackground): Shows a light color for the initials and background color.

#### Dark color

The dark background color can be set using [`DarkBackground`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.AvatarColorMode.html#Syncfusion_XForms_AvatarView_AvatarColorMode_DarkBackground) in the [`AvatarColorMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_AvatarColorMode) property.

{% tabs %}

{% highlight xaml %}

   <Grid>
        <sfavatar:SfAvatarView ContentType="Initials"
                               InitialsType="DoubleCharacter"
                               AvatarShape="Circle"
                               AvatarSize="Large"
                               HorizontalOptions="Center"
                               VerticalOptions="Center"
                               AvatarName="Alex"
                               AvatarColorMode="DarkBackground"
                               BorderColor="Black">
        </sfavatar:SfAvatarView>
   </Grid>

{% endhighlight %}

{% highlight c# %}


            Grid mainGrid = new Grid();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.AvatarShape = AvatarShape.Circle;
            avatarview.AvatarSize = AvatarSize.Large;
            avatarview.ContentType = ContentType.Initials;
            avatarview.InitialsType = InitialsType.DoubleCharacter;
            avatarview.AvatarName = "Alex";
            avatarview.BorderColor = Color.Black;
            avatarview.AvatarColorMode = AvatarColorMode.DarkBackground;
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;


{% endhighlight %}

{% endtabs %}

![Dark color](images/Dark_SfAvatarView.png)

#### Light color

The light background color can be set using [`LightBackground`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.AvatarColorMode.html#Syncfusion_XForms_AvatarView_AvatarColorMode_LightBackground) in the [`AvatarColorMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_AvatarColorMode) property.

{% tabs %}

{% highlight xaml %}

   <Grid>
        <sfavatar:SfAvatarView ContentType="Initials"
                               InitialsType="DoubleCharacter"
                               VerticalOptions="Center"
                               AvatarName="Alex"
                               AvatarShape="Circle"
                               AvatarSize="Large"
                               AvatarColorMode="LightBackground"
                               BorderColor="Black"
                               HorizontalOptions="Center" >
        </sfavatar:SfAvatarView>
   </Grid>

{% endhighlight %}

{% highlight c# %}
  
            Grid mainGrid = new Grid();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.AvatarShape = AvatarShape.Circle;
            avatarview.AvatarSize = AvatarSize.Large;
            avatarview.ContentType = ContentType.Initials;
            avatarview.InitialsType = InitialsType.DoubleCharacter;
            avatarview.AvatarName = "Alex";
            avatarview.BorderColor = Color.Black;
            avatarview.AvatarColorMode = AvatarColorMode.LightBackground;
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;

{% endhighlight %}

{% endtabs %}

![Light color](images/Light_SfAvatarView.png)

### Gradients

You can also specify a range of colors using [`BackgroundGradient`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_BackgroundGradient) as demonstrated in the following code example.

{% tabs %}

{% highlight xaml %}

            xmlns:gradient ="clr-namespace:Syncfusion.XForms.Graphics;assembly=Syncfusion.Core.XForms"
................
        <sfavatar:SfAvatarView ContentType="Initials" 
                               AvatarName="Alex"
                               AvatarShape="Circle"
                               AvatarSize="Large"
                               HorizontalOptions="Center"
                               VerticalOptions="Center"      
                               InitialsType="DoubleCharacter">
            <sfavatar:SfAvatarView.BackgroundGradient>
                <gradient:SfLinearGradientBrush>
                    <gradient:SfLinearGradientBrush.GradientStops>
                        <gradient:SfGradientStop Color="#2F9BDF" Offset="0"/>
                        <gradient:SfGradientStop Color="#51F1F2" Offset="1"/>
                    </gradient:SfLinearGradientBrush.GradientStops>
                </gradient:SfLinearGradientBrush>
            </sfavatar:SfAvatarView.BackgroundGradient>
        </sfavatar:SfAvatarView>
  

{% endhighlight %}

{% highlight c# %}

            using Syncfusion.XForms.Graphics;
            .......

            SfLinearGradientBrush gradientBrush = new SfLinearGradientBrush();
            gradientBrush.GradientStops = new GradientStopCollection()
            {
                new SfGradientStop(){ Color = Color.FromHex("#2F9BDF"), Offset = 0 },
                new SfGradientStop(){ Color = Color.FromHex("#51F1F2"), Offset = 1 }
            };

            Grid mainGrid = new Grid();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.AvatarShape = AvatarShape.Circle;
            avatarview.AvatarSize = AvatarSize.Large;
            avatarview.ContentType = ContentType.Initials;
            avatarview.InitialsType = InitialsType.DoubleCharacter;
            avatarview.AvatarName = "Alex";
            avatarview.BorderColor = Color.Black;
            avatarview.BackgroundGradient = gradientBrush;
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;

{% endhighlight %}

{% endtabs %}

![SfAvatarView conrol with gradient](images/Gradient_SfAvatarView.png)

N> Here, the [`BackgroundGradient`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_BackgroundGradient) is a type of [`SfGradientBrush`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Graphics.SfGradientBrush.html), so you can apply [`SfLinearGradientBrush`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Graphics.SfLinearGradientBrush.html) on it. This [`SfLinearGradientBrush`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Graphics.SfLinearGradientBrush.html) is available in [`Syncfusion.Xamarin.Core`](https://www.nuget.org/packages/Syncfusion.Xamarin.Core) from [`nuget.org`](https://www.nuget.org/). To know more about gradient view, refer to this [documentation](https://help.syncfusion.com/xamarin/sfgradientview/getting-started).

## Sizing

In the [`SfAvatarView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html) control, size of the view can be controlled using width, height, border width, and corner radius.

### Width

You can customize the width of the avatar view using the [`WidthRequest`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_WidthRequest) property.

### Height

You can customize the height of the avatar view using the [`HeightRequest`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_HeightRequest) property.

### Border width

You can customize the thickness of the avatar view using the [`BorderWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Border.SfBorder.html#Syncfusion_XForms_Border_SfBorder_BorderWidth) property.

{% tabs %}

{% highlight xaml %}

   <Grid>
        <sfavatar:SfAvatarView ContentType="Default"
                               AvatarShape="Circle"
                               AvatarSize="Large"
                               ImageSource="ellanaa.png"
                               BorderColor="Red" 
                               VerticalOptions="Center"
                               BorderWidth="4"
                               HorizontalOptions="Center" >
        </sfavatar:SfAvatarView>
   </Grid>

{% endhighlight %}

{% highlight c# %}

            Grid mainGrid = new Grid();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.AvatarShape = AvatarShape.Circle;
            avatarview.AvatarSize = AvatarSize.Large;
            avatarview.BorderWidth = 4;
            avatarview.BorderColor = Color.Red,
            avatarview.ContentType = ContentType.Default;
            avatarview.ImageSource = "ellanaa.png";
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;

{% endhighlight %}

{% endtabs %}

![AvatarView Border width](images/BordeWidth_AvatarView.png)

### Corner radius

You can customize the corner radius of the avatar view using the [`CornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_CornerRadius) property.

{% tabs %}

{% highlight xaml %}

   <Grid>
        <sfavatar:SfAvatarView ContentType="Default"
                               ImageSource="ellanaa.png"
                               HorizontalOptions="Center"
                               VerticalOptions="Center"   
                               WidthRequest="60"
                               HeightRequest="60"
                               CornerRadius="20">
        </sfavatar:SfAvatarView>
   </Grid>

{% endhighlight %}

{% highlight c# %}

            Grid mainGrid = new Grid();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.WidthRequest = 60;
            avatarview.HeightRequest = 60;
            avatarview.CornerRadius = 20;
            avatarview.ImageSource = "ellanaa.png";
            avatarview.ContentType = ContentType.Default;
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;

{% endhighlight %}

{% endtabs %}

![SfAvatarView corner radius](images/CornerRadius_AvatarView.png)

