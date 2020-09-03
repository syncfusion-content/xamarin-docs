---

layout: post
title: Position customization of Syncfusion Badge view for Xamarin.Forms
description: Learn how to set Syncfusion badge view position customization in Xamarin.Forms platform
platform: xamarin
control: SfBadgeView
documentation: ug

---

# Position customization

The default position of notification is `TopRight`. You can change the position to the `TopLeft`, `BottomLeft`, and `BottomRight` using the [`BadgePosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.BadgeView.BadgeSetting.html#Syncfusion_XForms_BadgeView_BadgeSetting_BadgePosition) properties. 

{% tabs %}

{% highlight xaml %}

 <badge:SfBadgeView BadgeText="NEW" HorizontalOptions="Center" VerticalOptions="Center">
        <badge:SfBadgeView.Content>
            <Button Text="Primary" WidthRequest="120" HeightRequest="60"/>
        </badge:SfBadgeView.Content>
        <badge:SfBadgeView.BadgeSettings>
            <badge:BadgeSetting   BadgePosition="TopRight"/>
        </badge:SfBadgeView.BadgeSettings>
</badge:SfBadgeView>

{% endhighlight %}

{% highlight c# %}

SfBadgeView sfBadgeView = new SfBadgeView();
sfBadgeView.HorizontalOptions = LayoutOptions.Center;
sfBadgeView.VerticalOptions = LayoutOptions.Center;
sfBadgeView.BadgeText = "NEW";
Button button = new Button();
button.Text = "Primary";
button.WidthRequest = 120;
button.HeightRequest = 60;
sfBadgeView.Content = button;
BadgeSetting badgeSetting = new BadgeSetting();
badgeSetting.BadgePosition = BadgePosition.TopRight;
sfBadgeView.BadgeSettings = badgeSetting;
Content = sfBadgeView;
    
{% endhighlight %}

{% endtabs %}

![Xamarin BadgeView Badge Position](badge-position_images/badgeposition.png)

## Setting badge offset

You can adjust the badge text using the [`Offset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.BadgeView.BadgeSetting.html#Syncfusion_XForms_BadgeView_BadgeSetting_Offset) property.

{% tabs %}

{% highlight xaml %}

  <badge:SfBadgeView BadgeText="8" HorizontalOptions="Center" VerticalOptions="Center">
        <badge:SfBadgeView.Content>
            <Image Source="BadgeImage9.png" HeightRequest="70" WidthRequest="60"/>
        </badge:SfBadgeView.Content>
        <badge:SfBadgeView.BadgeSettings>
            <badge:BadgeSetting BadgeType="Success" Offset="-5,-10" BadgePosition="BottomRight"/>
        </badge:SfBadgeView.BadgeSettings>
</badge:SfBadgeView>

{% endhighlight %}

{% highlight c# %}

SfBadgeView sfBadgeView = new SfBadgeView();
sfBadgeView.HorizontalOptions = LayoutOptions.Center;
sfBadgeView.VerticalOptions = LayoutOptions.Center;
sfBadgeView.BadgeText = "8";
Image image = new Image();
image.Source = "BadgeImage9.png";
image.HeightRequest = 70;
image.WidthRequest = 60;
sfBadgeView.Content = image;
BadgeSetting badgeSetting = new BadgeSetting();
badgeSetting.BadgeType = BadgeType.Success;
badgeSetting.BadgePosition = BadgePosition.BottomRight;
badgeSetting.Offset = new Point(-5, -10);
sfBadgeView.BadgeSettings = badgeSetting;
Content = sfBadgeView;

{% endhighlight %}

{% endtabs %}

![Xamarin BadgeView Badge Offset](badge-position_images/badgeoffset.png)