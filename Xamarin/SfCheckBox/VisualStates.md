---
layout: post
title: Visual States for Syncfusion Essential Xamarin.Forms SfCheckBox
description: How to customize SfCheckBox based on its visual state changes in Xamarin.Forms SfCheckBox.
platform: xamarin.forms
control: SfCheckBox
documentation: ug
---

## Visual States

The CheckBox visual can be customized through `VisualStates`. The [`SfCheckBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfCheckBox.html) control have the following four visual states:

* Disabled
* Checked
* Unchecked
* Intermediate


{% tabs %}
{% highlight xaml %}

<buttons:SfCheckBox Text="CheckBox">
    <VisualStateManager.VisualStateGroups>
        <VisualStateGroup x:Name="CommonStates">
            <VisualState x:Name="Checked">
                <VisualState.Setters>
                    <Setter Property="TextColor" Value="Accent"/>
                    <Setter Property="CheckedColor" Value="Accent"/>
                </VisualState.Setters>
            </VisualState>
            <VisualState x:Name="Unchecked">
                <VisualState.Setters>
                    <Setter Property="TextColor" Value="#ea3737"/>
                    <Setter Property="UncheckedColor" Value="#ea3737"/>
                </VisualState.Setters>
            </VisualState>
            <VisualState x:Name="Intermediate">
                <VisualState.Setters>
                    <Setter Property="Text" Value="Intermediate State"/>
                </VisualState.Setters>
            </VisualState>
            <VisualState x:Name="Disabled">
                <VisualState.Setters>
                    <Setter Property="TextColor" Value="#1947c3"/>
                    <Setter Property="BackgroundColor" Value="#7b7f89"/>
                </VisualState.Setters>
            </VisualState>
        </VisualStateGroup>
    </VisualStateManager.VisualStateGroups>
</buttons:SfCheckBox>

{% endhighlight %}
{% highlight c# %}

SfCheckBox checkBox = new SfCheckBox() { Text = "CheckBox" };
VisualStateGroupList visualStateGroupList = new VisualStateGroupList();
VisualStateGroup commonStateGroup = new VisualStateGroup();

VisualState checkedState = new VisualState
{
    Name = "Checked"
};

checkedState.Setters.Add(new Setter { Property = SfCheckBox.TextColorProperty, Value = Color.Accent });
checkedState.Setters.Add(new Setter { Property = SfCheckBox.CheckedColorProperty, Value = Color.Accent });

VisualState uncheckedState = new VisualState
{
    Name = "Unchecked"
};
uncheckedState.Setters.Add(new Setter { Property = SfCheckBox.TextColorProperty, Value = Color.FromHex("#ea3737") });
uncheckedState.Setters.Add(new Setter { Property = SfCheckBox.UncheckedColorProperty, Value = Color.FromHex("#ea3737") });

VisualState disabledState = new VisualState
{
    Name = "Disabled"
};

disabledState.Setters.Add(new Setter { Property = SfCheckBox.TextColorProperty, Value = Color.FromHex("#1947c3") });
disabledState.Setters.Add(new Setter { Property = SfCheckBox.BackgroundColorProperty, Value = Color.FromHex("#7b7f89") });

VisualState intermediateState = new VisualState
{
    Name = "Intermediate"
};

intermediateState.Setters.Add(new Setter { Property = SfCheckBox.TextProperty, Value = "Intermediate State") });

commonStateGroup.States.Add(checkedState);
commonStateGroup.States.Add(uncheckedState);
commonStateGroup.States.Add(intermediateState);
commonStateGroup.States.Add(disabledState);

visualStateGroupList.Add(commonStateGroup);
VisualStateManager.SetVisualStateGroups(checkBox, visualStateGroupList);

{% endhighlight %}
{% endtabs %}

Visual state checked:
![SfCheckBox with visual state of checked state](images/CheckBox_VisualState_Checked.png)

Visual state unchecked:
![SfCheckBox with visual state of unchecked state](images/CheckBox_VisualState_Unchecked.png)

Visual state intermediate:
![SfCheckBox with visual state of intermediate state](images/CheckBox_VisualState_Intermediate.png)

Visual state disabled:
![SfCheckBox with visual state of disabled state](images/CheckBox_VisualState_Disabled.png)
