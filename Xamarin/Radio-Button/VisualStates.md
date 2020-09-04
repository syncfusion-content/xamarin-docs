---
layout: post
title: Visual States for Syncfusion Essential Xamarin.Forms SfRadioButton
description: How to customize RadioButton based on its visual state changes in Xamarin.Forms SfRadioButton which can be customized using `VisualStates`. 
platform: xamarin.forms
control: SfRadioButton
documentation: ug
---

# Visual States for Xamarin.Forms Radio Button

The visual of Radio Button can be customized using `VisualStates`. The [`SfRadioButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfRadioButton.html) control contains the following two visual states:

* Checked
* Unchecked


{% tabs %}
{% highlight xaml %}

<buttons:SfRadioButton Text="Radio Button">
    <VisualStateManager.VisualStateGroups>
        <VisualStateGroup x:Name="CommonStates">
            <VisualState x:Name="Checked">
                <VisualState.Setters>
                    <Setter Property="TextColor" Value="Accent"/>
                    <Setter Property="BackgroundColor" Value="#8bc5fb"/>
                    <Setter Property="CheckedColor" Value="Accent"/>
                </VisualState.Setters>
            </VisualState>
            <VisualState x:Name="Unchecked">
                <VisualState.Setters>
                    <Setter Property="TextColor" Value="#ea3737"/>
                    <Setter Property="BackgroundColor" Value="#f6acac"/>
                    <Setter Property="UncheckedColor" Value="#ea3737"/>
                </VisualState.Setters>
            </VisualState>
        </VisualStateGroup>
    </VisualStateManager.VisualStateGroups>
</buttons:SfRadioButton>

{% endhighlight %}
{% highlight c# %}

SfRadioButton radioButton = new SfRadioButton { Text = "Radio Button" };
VisualStateGroupList visualStateGroupList = new VisualStateGroupList();
VisualStateGroup commonStateGroup = new VisualStateGroup();

VisualState checkedState = new VisualState
{
    Name = "Checked"
};

checkedState.Setters.Add(new Setter { Property = SfRadioButton.TextColorProperty, Value = Color.Accent });
checkedState.Setters.Add(new Setter { Property = SfRadioButton.BackgroundColorProperty, Value = Color.FromHex("#8bc5fb") });
checkedState.Setters.Add(new Setter { Property = SfRadioButton.CheckedColorProperty, Value = Color.Accent });

VisualState uncheckedState = new VisualState
{
    Name = "Unchecked"
};
uncheckedState.Setters.Add(new Setter { Property = SfRadioButton.TextColorProperty, Value = Color.FromHex("#ea3737") });
uncheckedState.Setters.Add(new Setter { Property = SfRadioButton.BackgroundColorProperty, Value = Color.FromHex("#f6acac") });
uncheckedState.Setters.Add(new Setter { Property = SfRadioButton.UncheckedColorProperty, Value = Color.FromHex("#ea3737") });

commonStateGroup.States.Add(checkedState);
commonStateGroup.States.Add(uncheckedState);

visualStateGroupList.Add(commonStateGroup);
VisualStateManager.SetVisualStateGroups(radioButton, visualStateGroupList);

{% endhighlight %}
{% endtabs %}

**Checked visual state:**
![SfRadioButton with visual state of checked state](images/RadioButton_VisualState_Checked.png)

**Unchecked visual state:**
![SfRadioButton with visual state of unchecked state](images/RadioButton_VisualState_Unchecked.png)