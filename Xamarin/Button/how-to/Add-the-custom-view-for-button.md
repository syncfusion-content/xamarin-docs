---
layout: post
title: How to add the custom view for Syncfusion SfButton
description: How to add the custom view for SfButton.
platform: xamarin.forms
control: sfbutton
documentation: ug
---

# Add the custom view for button

You can customize the appearance of the button by adding your custom view in the [`Content`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_Content) property. The following code sample demonstrates how to apply the busy indicator control as custom view for a button.

{% tabs %}
{% highlight xaml %}

xmlns:busyindicator="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"

. . .

<buttons:SfButton HeightRequest="60" CornerRadius="20" HorizontalOptions="Center" VerticalOptions="Center">
    <buttons:SfButton.Content>
        <StackLayout Orientation="Horizontal">
            <busyindicator:SfBusyIndicator AnimationType="SingleCircle" IsBusy="True" TextColor="White" WidthRequest="50"/>
            <Label Text="Loading..." FontSize="20" VerticalTextAlignment="Center" TextColor="White" />
        </StackLayout>
    </buttons:SfButton.Content>
</buttons:SfButton>

{% endhighlight %}
{% highlight c# %}

using Syncfusion.SfBusyIndicator.XForms;

. . . 

SfButton button = new SfButton();
button.HeightRequest = 60;
button.CornerRadius = 20;
button.HorizontalOptions = LayoutOptions.Center;
button.VerticalOptions = LayoutOptions.Center;

StackLayout stackLayout = new StackLayout();
stackLayout.Orientation = StackOrientation.Horizontal;
SfBusyIndicator busyindicator = new SfBusyIndicator()
{
    AnimationType = AnimationTypes.SingleCircle,
    IsBusy = true,
    TextColor = Color.White,
    WidthRequest = 50
};

Label label = new Label()
{
    Text = "Loading...",
    FontSize = 20,
    VerticalTextAlignment = TextAlignment.Center,
    TextColor = Color.White
};

stackLayout.Children.Add(busyindicator);
stackLayout.Children.Add(label);
button.Content = stackLayout;

{% endhighlight %}
{% endtabs %}

![SfButton with custom view](images/button_content.png)