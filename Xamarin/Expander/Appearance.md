---
layout: post
title: Appearance | Expander for Xamarin.Forms | Syncfusion
description: Learn about Appearance support in Syncfusion Xamarin Expander (SfExpander) control and more details.
platform: xamarin
control: SfExpander
documentation: ug
---

# Appearance in Xamarin Expander (SfExpander)

The Expander allows customizing appearance of the Icon, and provides various functionalities to the users.

## Header icon position 

The [SfExpander](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Expander.SfExpander.html) allows you to customize the position of the header icon by using the [HeaderIconPosition](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Expander.SfExpander.html#Syncfusion_XForms_Expander_SfExpander_HeaderIconPosition) property. By default, the header icon position is `Start`. 

{% tabs %}
{% highlight xaml %}
    <syncfusion:SfExpander x:Name="expander" HeaderIconPosition="End" />       
{% endhighlight %}
{% highlight c# %}
    expander.HeaderIconPosition = Syncfusion.XForms.Expander.IconPosition.End;
{% endhighlight %}
{% endtabs %}

## Header background color customization

The [SfExpander](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Expander.SfExpander.html) allows you to customize the background color of the expander header by using the [HeaderBackgroundColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Expander.SfExpander.html#Syncfusion_XForms_Expander_SfExpander_HeaderBackgroundColor) property.

{% tabs %}
{% highlight xaml %}
    <syncfusion:SfExpander x:Name="expander" HeaderBackgroundColor="Pink"/>
{% endhighlight %}
{% highlight c# %}
    expander.HeaderBackgroundColor = Color.Pink;
{% endhighlight %}
{% endtabs %}

## Icon color customization

The [SfExpander](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Expander.SfExpander.html) allows you to customize the color of the expander icon by using the [IconColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Expander.SfExpander.html#Syncfusion_XForms_Expander_SfExpander_IconColor) property. By default, `IconColor` is black.

{% tabs %}
{% highlight xaml %}
    <syncfusion:SfExpander x:Name="expander" IconColor="Accent"/>
{% endhighlight %}
{% highlight c# %}
    expander.IconColor = Color.Accent;
{% endhighlight %}
{% endtabs %}

## Visual State Manager

The appearance of the [SfExpander](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Expander.SfExpander.html) can be customized using the following two `VisualStates`:

* Expanded
* Collapsed

{% tabs %}
{% highlight xaml %}
<syncfusion:SfExpander x:Name="expander">
    <syncfusion:SfExpander.Header>
        <Grid>
            <Label  Text="Veg Pizza" VerticalTextAlignment="Center"/>
        </Grid>
    </syncfusion:SfExpander.Header>
    <syncfusion:SfExpander.Content>
        <Grid>
            <Label HeightRequest="50" Text="Veg pizza is prepared with the items that meet vegetarian standards by not including any meat or animal tissue products." VerticalTextAlignment="Center"/>
        </Grid>
    </syncfusion:SfExpander.Content>
    <VisualStateManager.VisualStateGroups>
        <VisualStateGroupList>
            <VisualStateGroup>
                <VisualState Name="Expanded">
                    <VisualState.Setters>
                        <Setter Property="HeaderBackgroundColor" Value="Red"/>
                    </VisualState.Setters>
                </VisualState>
                <VisualState Name="Collapsed">
                    <VisualState.Setters>
                        <Setter Property="HeaderBackgroundColor" Value="Green"/>
                    </VisualState.Setters>
                </VisualState>
            </VisualStateGroup>
        </VisualStateGroupList>
    </VisualStateManager.VisualStateGroups>
</syncfusion:SfExpander>
{% endhighlight %}
{% highlight c# %}
SfExpander expander = new SfExpander();
expander.Header = new Label() 
{
    Text="Veg Pizza" 
};
expander.Content = new Label() 
{ 
    Text="Veg pizza is prepared with the items that meet vegetarian standards by not including any meat or animal tissue products."
};
    
VisualStateGroupList visualStateGroupList = new VisualStateGroupList();
VisualStateGroup commonStateGroup = new VisualStateGroup();

VisualState expanded = new VisualState
{
    Name = "Expanded"
};
expanded.Setters.Add(new Setter { Property = SfExpander.HeaderBackgroundColorProperty, Value = Color.Red });
expanded.Setters.Add(new Setter { Property = SfExpander.HeaderBackgroundColorProperty, Value = Color.Red });

VisualState collapsed = new VisualState
{
    Name = "Collapsed"
};
collapsed.Setters.Add(new Setter { Property = SfExpander.HeaderBackgroundColorProperty, Value = Color.Green });
collapsed.Setters.Add(new Setter { Property = SfExpander.HeaderBackgroundColorProperty, Value = Color.Green });
    
commonStateGroup.States.Add(expanded);
commonStateGroup.States.Add(collapsed);

visualStateGroupList.Add(commonStateGroup);
VisualStateManager.SetVisualStateGroups(expander, visualStateGroupList);
this.Content = expander;
{% endhighlight %}
{% endtabs %}

![Xamarin Forms Expander with VSM](expander_images/Expander_VSM.png)

You can download the entire source of this demo [here](https://github.com/SyncfusionExamples/Xamarin-Expander-VisualStateManager). 

N> When effects view is applied to `Expander` by adding Visual as "Material", it is necessary to initialize the `Xamarin.Forms.FormsMaterial.Init` in iOS and Android.

## See also

[How to customize header icon in Xamarin.Forms Expander (SfExpander)](https://www.syncfusion.com/kb/11378/)                                                                                                                                                                                                         
[How to center align the Expander header text in Xamarin.Forms (SfExpander)](https://www.syncfusion.com/kb/11360/)                                                                                                                                                                                                                                                                                                                                                                                                      
[How to use a custom font icon for Expander in Xamarin.Forms (SfExpander)](https://www.syncfusion.com/kb/11469/)