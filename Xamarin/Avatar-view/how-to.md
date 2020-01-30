---
layout: post
title: States in Syncfusion AvatarView control for Xamarin.Forms.
description: This section will explain about how to use the different states that exist in Xamarin.Forms SfAvatarView.
platform: Xamarin
control: AvatarView
documentation: ug
---

# How to

## Set badge view to avatar

The `SfAvatarView` control provides support for `BadgeView` to notify users of new or unread messages, notifications, or the status of something.

{% tabs %}

{% highlight xaml %}

xmlns:badge="clr-namespace:Syncfusion.XForms.BadgeView;assembly=Syncfusion.SfBadgeView.XForms"
.......

        <badge:SfBadgeView VerticalOptions="Center"
                           HorizontalOptions="Center">
            <badge:SfBadgeView.Content>
                <sfavatar:SfAvatarView  HorizontalOptions="Center"
                                        ContentType="Custom"
                                        ImageSource="alex.png"
                                        VerticalOptions="Center"
                                        WidthRequest="60"
                                        HeightRequest="60"
                                        CornerRadius="30">
                </sfavatar:SfAvatarView>
            </badge:SfBadgeView.Content>
            <badge:SfBadgeView.BadgeSettings>
                <badge:BadgeSetting Offset="-10,-10"
                                    BadgeAnimation="Scale"
                                    BadgePosition="BottomRight" 
                                    BadgeType="Success"
                                    BadgeIcon="Away"/>
            </badge:SfBadgeView.BadgeSettings>
        </badge:SfBadgeView>

{% endhighlight %}

{% highlight C# %}
             
            using Syncfusion.XForms.BadgeView;
    .................

            SfBadgeView badge = new SfBadgeView();
            badge.HorizontalOptions = LayoutOptions.Center;
            badge.VerticalOptions = LayoutOptions.Center;
            badge.BadgeSettings = new BadgeSetting();
            BadgeSetting badgeSetting = new BadgeSetting();
            badgeSetting.BadgeType = BadgeType.Success;
            badgeSetting.BadgeIcon = BadgeIcon.Away;
            badgeSetting.BadgePosition = BadgePosition.BottomRight;
            badgeSetting.BadgeAnimation = BadgeAnimation.Scale;
            badgeSetting.Offset = new Point(-10, -10);
            badge.BadgeSettings = badgeSetting;

            Grid mainGrid = new Grid();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.WidthRequest = 60;
            avatarview.HeightRequest = 60;
            avatarview.CornerRadius = 30;
            avatarview.ImageSource = "alex.png";
            avatarview.ContentType = ContentType.Custom;
            badge.Content = avatarview;
            mainGrid.Children.Add(badge);
            this.Content = mainGrid;

{% endhighlight %}

{% endtabs %}

![BadgeView support](images/BadgeView_AvatarView.jpg)

N> The `SfBadgeView` is available in [`Syncfusion.Xamarin.SfBadgeView`](https://www.nuget.org/packages/Syncfusion.Xamarin.SfBadgeView) from [`nuget.org`](https://www.nuget.org/). To know more about `SfBadgeView` view, refer to this [documentation](https://help.syncfusion.com/xamarin/sfbadgeview/getting-started).
