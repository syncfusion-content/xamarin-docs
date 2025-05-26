---

layout: post
title: Predefined Symbols of Syncfusion Badge View Control for Xamarin.Forms
description: Learn to configure predefined symbols and types of badge icons in the Syncfusion Badge View for Xamarin.Forms.
platform: Xamarin
control: SfBadgeView
documentation: ug

---

# Predefined Symbols in Xamarin.Forms BadgeView (SfBadgeView)

Change the badge icon within the `SfBadgeView` using the [`BadgeIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.BadgeView.BadgeSetting.html#Syncfusion_XForms_BadgeView_BadgeSetting_BadgeIcon) property. Icons appear when badge text is not set. Supported `BadgeIcon` types include:
- Add
- Available
- Away
- Busy
- Delete
- Dot
- None
- Prohibit1
- Prohibit2

> **Note:** When both [`BadgeIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.BadgeView.BadgeSetting.html#Syncfusion_XForms_BadgeView_BadgeSetting_BadgeIcon) and [`BadgeText`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.BadgeView.SfBadgeView.html#Syncfusion_XForms_BadgeView_SfBadgeView_BadgeText) are set, badge text is prioritized and will be displayed.

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

