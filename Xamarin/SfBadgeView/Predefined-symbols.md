---

layout: post
title: Predefined symbols of Syncfusion Badge view control for Xamarin.Forms
description: Learn how to set Syncfusion badge view predefined symbols in Xamarin.Forms platform
platform: xamarin
control: SfBadgeView
documentation: ug

---

# Predefined symbols

You can change the badge icon using the [`BadgeIcon`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfBadgeView.XForms~Syncfusion.XForms.BadgeView.BadgeSetting~BadgeIcon.html) property. Badge text will be visible, when you set the badge icon as `None`. The badge supports the following types of [`BadgeIcon`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfBadgeView.XForms~Syncfusion.XForms.BadgeView.BadgeSetting~BadgeIcon.html):

* Add
* Available
* Away
* Busy
* Delete 
* Dot
* None
* Prohibit1
* Prohibit2

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