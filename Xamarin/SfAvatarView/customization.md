---
layout: post
title: Customization in Syncfusion AvatarView Xamarin.Forms
description: Explaining about customization in SfAvatarView.
platform: Xamarin
control: AvatarView
documentation: ug
---

# Customization 

The SfAvatarView control provides options to customize the color and size. The control can be customized using the following properties:

## Colors

Color in the SfAvatarView can be customized by the border color, the default background color, and automatic background color.

### Border color

The border color is used for setting color to the border of SfAvatarView using the `BorderColor` property.

{% tabs %}

{% highlight xaml %}

              <sfavatar:SfAvatarView  AvatarType="Automatic"  
                                       AvatarStyle="LargeCircle"
                                       HorizontalOptions="Center"
                                       VerticalOptions="Center"
                                       ImageSource="ellanaa.png"
                                       BorderColor="Red">
            </sfavatar:SfAvatarView>

{% endhighlight %}

{% highlight c# %}

            Grid mainGrid = new Grid();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.AvatarType = AvatarType.Automatic;
            avatarview.AvatarStyle = AvatarStyle.LargeCircle;
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

The background color for the SfAvatarView control can be set using the `ColorMode` property. When the `ColorMode` property is set to default, it displays the background color set in the `BackgroundColor` property.

{% tabs %}

{% highlight xaml %}

                <sfavatar:SfAvatarView AvatarType="Initials"  
                                       AvatarStyle="LargeCircle"
                                       HorizontalOptions="Center"
                                       VerticalOptions="Center"
                                       Initials="Alex"          
                                       BackgroundColor="Bisque"
                                       ColorMode="Default"
                                       BorderColor="Black">
                </sfavatar:SfAvatarView>
      

{% endhighlight %}

{% highlight c# %}

            Grid mainGrid = new Grid();
            SfAvatarView avatarview = new SfAvatarView();     
            avatarview.AvatarType = AvatarType.Initials;
            avatarview.AvatarStyle = AvatarStyle.LargeCircle;
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.Initials = "Alex";
            avatarview.BorderColor = Color.Black;
            avatarview.ColorMode = ColorMode.Default;
            avatarview.BackgroundColor = Color.Bisque;
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;

{% endhighlight %}

{% endtabs %}

![Default background color](images/Default_Background_AvatarView.png)

### Automatic background color

The `SfAvatarView` control allows automatic background color while initializing. It contains the following properties:

* `AutomaticDarkColorsOnInitialize`: Shows a dark color for the initials and background color.
* `AutomaticLightColorsOnInitialize`: Shows a light color for the initials and background color.

#### Dark color

The dark background color can be set using `AutomaticDarkColorsOnInitialize` in the `ColorMode` property.

{% tabs %}

{% highlight xaml %}

    <sfavatar:SfAvatarView AvatarType="Initials"  
                           InitialsType="DoubleCharacter"
                           AvatarStyle="LargeCircle"
                           HorizontalOptions="Center"
                           VerticalOptions="Center"
                           Initials="Alex"
                           ColorMode="AutomaticDarkColorsOnInitialize"
                           BorderColor="Black">
    </sfavatar:SfAvatarView>

{% endhighlight %}

{% highlight c# %}


            Grid mainGrid = new Grid();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.AvatarStyle = AvatarStyle.LargeCircle;
            avatarview.AvatarType = AvatarType.Initials;
            avatarview.InitialsType = InitialsType.DoubleCharacter;
            avatarview.Initials = "Alex";
            avatarview.BorderColor = Color.Black;
            avatarview.ColorMode = ColorMode.AutomaticDarkColorsOnInitialize;
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;


{% endhighlight %}

{% endtabs %}

![Dark color](images/Dark_SfAvatarView.png)

#### Light color

The light background color can be set using `AutomaticLightColorsOnInitialize` in the `ColorMode` property.

{% tabs %}

{% highlight xaml %}

   <sfavatar:SfAvatarView AvatarType="Initials"  
                          InitialsType="DoubleCharacter"
                          VerticalOptions="Center"
                          Initials="Alex"
                          AvatarStyle="LargeCircle"
                          ColorMode="AutomaticLightColorsOnInitialize"
                          BorderColor="Black" 
                          HorizontalOptions="Center" >
    </sfavatar:SfAvatarView>

{% endhighlight %}

{% highlight c# %}
  
             Grid mainGrid = new Grid();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.AvatarStyle = AvatarStyle.LargeCircle;
            avatarview.AvatarType = AvatarType.Initials;
            avatarview.InitialsType = InitialsType.DoubleCharacter;
            avatarview.Initials = "Alex";
            avatarview.BorderColor = Color.Black;
            avatarview.ColorMode = ColorMode.AutomaticLightColorsOnInitialize;
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;

{% endhighlight %}

{% endtabs %}

![Light color](images/Light_SfAvatarView.png)

### Gradients

You can also specify a range of colors using `BackgroundBrush` as demonstrated in the following code example.

{% tabs %}

{% highlight xaml %}

            xmlns:gradient ="clr-namespace:Syncfusion.XForms.Graphics;assembly=Syncfusion.Core.XForms"
................
        <sfavatar:SfAvatarView AvatarType="Initials" 
                               Initials="Alex"
                               AvatarStyle="LargeCircle"
                               HorizontalOptions="Center"
                               VerticalOptions="Center"      
                               InitialsType="DoubleCharacter">
            <sfavatar:SfAvatarView.BackgroundBrush>
                <gradient:SfLinearGradientBrush>
                    <gradient:SfLinearGradientBrush.GradientStops>
                        <gradient:SfGradientStop Color="#2F9BDF" Offset="0"/>
                        <gradient:SfGradientStop Color="#51F1F2" Offset="1"/>
                    </gradient:SfLinearGradientBrush.GradientStops>
                </gradient:SfLinearGradientBrush>
            </sfavatar:SfAvatarView.BackgroundBrush>
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
            avatarview.AvatarStyle = AvatarStyle.LargeCircle;
            avatarview.AvatarType = AvatarType.Initials;
            avatarview.InitialsType = InitialsType.DoubleCharacter;
            avatarview.Initials = "Alex";
            avatarview.BorderColor = Color.Black;
            avatarview.BackgroundBrush = gradientBrush;
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;

{% endhighlight %}

{% endtabs %}

![SfAvatarView conrol with gradient](images/Gradient_SfAvatarView.png)

N> Here, the `BackgroundBrush` is a type of `SfGradientBrush`, so you can apply `SfLinearGradientBrush` on it. This `SfLinearGradientBrush` is available in [`Syncfusion.Xamarin.Core`](https://www.nuget.org/packages/Syncfusion.Xamarin.Core) from [`nuget.org`](https://www.nuget.org/). To know more about gradient view, refer to this [documentation](https://help.syncfusion.com/xamarin/sfgradientview/getting-started).

## Sizing

In the `SfAvatarView` control, size of the view can be controlled using width, height, border width, and corner radius.

### Width

You can customize the width of the avatar view using the `WidthRequest` property.

### Height

You can customize the height of the avatar view using the `HeightRequest` property.

### Border width

You can customize the thickness of the avatar view using the `BorderWidth` property.

{% tabs %}

{% highlight xaml %}

               <sfavatar:SfAvatarView AvatarType="Automatic"  
                                       AvatarStyle="LargeCircle"
                                       ImageSource="ellanaa.png"
                                       BorderColor="Red" 
                                       BorderWidth="4"
                                       HorizontalOptions="Center" >
                </sfavatar:SfAvatarView>

{% endhighlight %}

{% highlight c# %}

            Grid mainGrid = new Grid();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.AvatarStyle = AvatarStyle.LargeCircle;
            avatarview.BorderWidth = 4;
            avatarview.AvatarType = AvatarType.Automatic;   
            avatarview.ImageSource = "ellanaa.png";        
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;

{% endhighlight %}

{% endtabs %}

![AvatarView Border width](images/BordeWidth_AvatarView.png)

### Corner radius

You can customize the corner radius of the avatar view using the `CornerRadius` property.

{% tabs %}

{% highlight xaml %}

         <sfavatar:SfAvatarView AvatarType="Automatic"
                                       ImageSource="ellanaa.png"
                                       HorizontalOptions="Center"
                                       VerticalOptions="Center"   
                                       WidthRequest="60"
                                       HeightRequest="60"
                                       CornerRadius="20">
                </sfavatar:SfAvatarView>

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
            avatarview.AvatarType = AvatarType.Automatic;           
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;

{% endhighlight %}

{% endtabs %}

![SfAvatarView corner radius](images/CornerRadius_AvatarView.png)

