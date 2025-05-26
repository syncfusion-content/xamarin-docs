---
layout: post
title: Visual States in Xamarin Button Control | Syncfusion
description: Discover how to use Visual States in the Syncfusion Xamarin Button (SfButton) control for enhanced UI customization.
platform: Xamarin
control: SfButton
documentation: ug
---

# Visual States in Xamarin Button (SfButton)

The button's appearance can be customized through `VisualStates`. The [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html) control supports the following five visual states:

- Normal
- Pressed
- Checked
- Unchecked
- Disabled

> Note:
> - Additionally, the `MouseOver` visual state is available only on the UWP platform.
> - The visual states `Checked` and `Unchecked` are only updated when the [`IsChecked`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_IsChecked) property is enabled in [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).

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

**Pressed Visual State:**
![SfButton with pressed visual state](images/VisualState_PressedState.png)

**Normal Visual State:**
![SfButton with normal visual state](images/VisualState_NormalState.png)

## See Also

[How to change Xamarin.Forms button style using its visual states](https://support.syncfusion.com/kb/article/9580/how-to-change-xamarinforms-button-style-using-its-visual-states)

