---
layout: post
title: Visual States for Syncfusion Essential Xamarin.Forms SfCheckBox
description: How to customize SfCheckBox based on its visual state changes(Checked state, UnChecked state, Intermediate state) in Xamarin.Forms SfCheckBox.
platform: xamarin.forms
control: SfCheckBox
documentation: ug
---

# Visual States for Xamarin.Forms CheckBox

The visual of CheckBox can be customized using `VisualStates`. The [`SfCheckBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfCheckBox.html) control contains the following three visual states:

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

VisualState intermediateState = new VisualState
{
    Name = "Intermediate"
};

intermediateState.Setters.Add(new Setter { Property = SfCheckBox.TextProperty, Value = "Intermediate State") });

commonStateGroup.States.Add(checkedState);
commonStateGroup.States.Add(uncheckedState);
commonStateGroup.States.Add(intermediateState);

visualStateGroupList.Add(commonStateGroup);
VisualStateManager.SetVisualStateGroups(checkBox, visualStateGroupList);

{% endhighlight %}
{% endtabs %}

**Checked visual state:**
![SfCheckBox with visual state of checked state](images/CheckBox_VisualState_Checked.png)

**Unchecked visual state:**
![SfCheckBox with visual state of unchecked state](images/CheckBox_VisualState_Unchecked.png)

**Intermediate visual state:**
![SfCheckBox with visual state of intermediate state](images/CheckBox_VisualState_Intermediate.png)
