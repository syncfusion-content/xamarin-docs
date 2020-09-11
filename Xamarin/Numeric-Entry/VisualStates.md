---
layout: post
title: Visual States for Syncfusion Essential Xamarin.Forms SfNumericTextBox
description: How to customize the appearance of Xamarin.Forms SfNumericTextBox according to its available visual states.
platform: xamarin.forms
control: SfNumericTextBox
documentation: ug
---

# Visual States in Xamarin.Forms SfNumericTextBox

The button visual can be customized through `VisualStates`. The [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.html) control have the following four visual states:

* Normal
* Focused
* Disabled

N> The Focused VisualState only available in Android and iOS platforms.

{% tabs %}
{% highlight xaml %}

    <StackLayout HorizontalOptions="Center" VerticalOptions="Center">
        <numeric:SfNumericTextBox x:Name="numericTextBox" WidthRequest="100" Value="50"/>

        <VisualStateManager.VisualStateGroups>
            <VisualStateGroup x:Name="CommonStates">
                <VisualState x:Name="Normal">
                    <VisualState.Setters>
                        <Setter Property="BackgroundColor" Value="White" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState x:Name="Disabled">
                    <VisualState.Setters>
                        <Setter Property="BackgroundColor" Value="DarkGray" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState x:Name="Focused">
                    <VisualState.Setters>
                        <Setter Property="BackgroundColor" Value="Yellow" />
                    </VisualState.Setters>
                </VisualState>
            </VisualStateGroup>
        </VisualStateManager.VisualStateGroups>
    </StackLayout>

{% endhighlight %}
{% highlight c# %}

            StackLayout stackLayout = new StackLayout
            {
                HorizontalOptions = LayoutOptions.Center,
                VerticalOptions = LayoutOptions.Center
            };
            SfNumericTextBox button = new SfNumericTextBox
            {
                Value = 50,
                WidthRequest = 100
            };

            VisualStateGroupList visualStateGroupList = new VisualStateGroupList();

            VisualStateGroup commonStateGroup = new VisualStateGroup();
            VisualState normalState = new VisualState
            {
                Name = "Normal"
            };
            normalState.Setters.Add(new Setter { Property = SfNumericTextBox.BackgroundColorProperty, Value = Color.White });

            VisualState disabledState = new VisualState
            {
                Name = "Disabled"
            };
            disabledState.Setters.Add(new Setter { Property = SfNumericTextBox.BackgroundColorProperty, Value = Color.DarkGray });

            VisualState fousedState = new VisualState
            {
                Name = "Focused"
            };
            fousedState.Setters.Add(new Setter { Property = SfNumericTextBox.BackgroundColorProperty, Value = Color.Yellow });

            commonStateGroup.States.Add(normalState);
            commonStateGroup.States.Add(disabledState);
            commonStateGroup.States.Add(fousedState);
            visualStateGroupList.Add(commonStateGroup);

            VisualStateManager.SetVisualStateGroups(button, visualStateGroupList);

            stackLayout.Children.Add(button);
            this.Content = stackLayout;

{% endhighlight %}
{% endtabs %}

**Normal visual state:**
![SfNumericTextBox with normal visual state](images/NormalState.jpg)

**Disabled visual state:**
![SfNumericTextBox with focused visual state](images/FocusState.jpg)

**Focused visual state:**
![SfNumericTextBox with disabled visual state](images/DisabledState.jpg)

## See also

[How to change the Xamarin.Forms numeric textbox style using its visual states (SfNumericTextBox)](https://www.syncfusion.com/kb/11785/how-to-change-the-xamarin-forms-numeric-textbox-style-using-its-visual-states)