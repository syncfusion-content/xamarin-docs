---

layout: post
title: Predefined symbols of Syncfusion Badge view control for Xamarin.Forms
description: Learn how to set Syncfusion badge view predefined symbols and types of badge icons in Xamarin.Forms platform
platform: xamarin
control: SfBadgeView
documentation: ug

---

# Predefined symbols in Xamarin.Forms BadgeView (SfBadgeView)

You can change the badge icon using the [`BadgeIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.BadgeView.BadgeSetting.html#Syncfusion_XForms_BadgeView_BadgeSetting_BadgeIcon) property. Badge icons will be visible when you do not set the badge text. The badge supports the following types of [`BadgeIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.BadgeView.BadgeSetting.html#Syncfusion_XForms_BadgeView_BadgeSetting_BadgeIcon):

* Add
* Available
* Away
* Busy
* Delete 
* Dot
* None
* Prohibit1
* Prohibit2

N> When both the [`BadgeIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.BadgeView.BadgeSetting.html#Syncfusion_XForms_BadgeView_BadgeSetting_BadgeIcon) and [`BadgeText`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.BadgeView.SfBadgeView.html#Syncfusion_XForms_BadgeView_SfBadgeView_BadgeText) are set for badge view, then badge text has a higher priority. The badge text will be rendered in output.

{% tabs %}

{% highlight xaml %}

<badge:SfBadgeView HorizontalOptions="Center" VerticalOptions="Center" >
        <badge:SfBadgeView.Content>
            <Image Source="BadgeImage9.png" HeightRequest="70" WidthRequest="60"/>
        </badge:SfBadgeView.Content>
        <badge:SfBadgeView.BadgeSettings>
            <badge:BadgeSetting BadgeType="Warning"  Offset="0, -10" BadgePosition="BottomRight" BadgeIcon="Away"/>
        </badge:SfBadgeView.BadgeSettings>
</badge:SfBadgeView>

{% endhighlight %}

{% highlight c# %}

SfBadgeView sfBadgeView = new SfBadgeView();
sfBadgeView.HorizontalOptions = LayoutOptions.Center;
sfBadgeView.VerticalOptions = LayoutOptions.Center;
Image image = new Image();
image.Source = "BadgeImage9.png";
image.HeightRequest = 70;
image.WidthRequest = 60;
sfBadgeView.Content = image;
BadgeSetting badgeSetting = new BadgeSetting();
badgeSetting.BadgeType = BadgeType.Warning;
badgeSetting.BadgeIcon = BadgeIcon.Away;
badgeSetting.BadgePosition = BadgePosition.BottomRight;
badgeSetting.Offset = new Point(0, -10);
sfBadgeView.BadgeSettings = badgeSetting;
Content = sfBadgeView;
    
{% endhighlight %}

{% endtabs %}

![Xamarin BadgeView Badge Icon](predefined-symbols_images/predefinedsymbols.png)

