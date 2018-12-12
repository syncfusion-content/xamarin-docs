---
layout: post
title: Visual States for Syncfusion Essential Xamarin.Forms SfButton
description: How to customize a visual states for Xamarin.Forms SfButton.
platform: xamarin.forms
control: sfbutton
documentation: ug
---

## Visual states

The button visual can be customized through `VisualStates`. The `SfButton`(https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton.html) control have the following four visual states:

* Normal
* Pressed
* Checked
* Unchecked

{% tabs %}
{% highlight xaml %}

<StackLayout HorizontalOptions="Center" VerticalOptions="Center">
    <buttons:SfButton x:Name="SfButton" WidthRequest="100" Text="Button">
        <VisualStateManager.VisualStateGroups>
            <VisualStateGroup x:Name="CommonStates">
                <VisualState x:Name="Normal">
                    <VisualState.Setters>
                        <Setter Property="TextColor" Value="White" />
                    </VisualState.Setters>
                </VisualState>

                <VisualState x:Name="Pressed">
                    <VisualState.Setters>
                        <Setter Property="TextColor" Value="Black" />
                    </VisualState.Setters>
                </VisualState>
            </VisualStateGroup>
        </VisualStateManager.VisualStateGroups>
    </buttons:SfButton>
</StackLayout>

{% endhighlight %}
{% highlight c# %}

StackLayout stackLayout = new StackLayout
{
    HorizontalOptions = LayoutOptions.Center,
    VerticalOptions = LayoutOptions.Center
};
SfButton button = new SfButton
{
    Text = "Button",
    WidthRequest = 100
};

VisualStateGroupList visualStateGroupList = new VisualStateGroupList();

VisualStateGroup commonStateGroup = new VisualStateGroup();
VisualState normalState = new VisualState
{
    Name = "Normal"
};
normalState.Setters.Add(new Setter { Property = SfButton.TextColorProperty, Value = Color.White });

VisualState pressedState = new VisualState
{
    Name = "Pressed"
};
pressedState.Setters.Add(new Setter { Property = SfButton.TextColorProperty, Value = Color.Black });

commonStateGroup.States.Add(normalState);
commonStateGroup.States.Add(pressedState);
visualStateGroupList.Add(commonStateGroup);

VisualStateManager.SetVisualStateGroups(button, visualStateGroupList);

stackLayout.Children.Add(button);
this.Content = stackLayout;

{% endhighlight %}
{% endtabs %}

Visual state pressed:
![SfButton with visual state](images/VisualState_PressedState.png)

Visual state normal:
![SfButton with visual state](images/VisualState_NormalState.png)