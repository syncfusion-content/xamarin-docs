---
layout: post
title: Appearance | Accordion for Xamarin.Forms | Syncfusion
description: Learn about Appearance support in Syncfusion Xamarin Accordion (SfAccordion) control and more details.
platform: xamarin
control: SfAccordion
documentation: ug
---

# Appearance in Xamarin Accordion (SfAccordion)

The Accordion allows customizing appearance of the Icon, and provides different functionalities to the users.

## Header icon position 

[SfAccordion](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html) allows you to customize the position of the header icon in accordion item by using the [HeaderIconPosition](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html#Syncfusion_XForms_Accordion_SfAccordion_HeaderIconPosition) property. By default, the header Icon position is `End`.  

{% tabs %}
{% highlight xaml %}
<syncfusion:SfAccordion x:Name="accordion" HeaderIconPosition="Start" />       
{% endhighlight %}
{% highlight c# %}
accordion.HeaderIconPosition = Syncfusion.XForms.Expander.IconPosition.Start;
{% endhighlight %}
{% endtabs %}

## Header background color customization

[SfAccordion](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html) allows you to customize the background color of the expander header by using the [HeaderBackgroundColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.AccordionItem.html#Syncfusion_XForms_Accordion_AccordionItem_HeaderBackgroundColor) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfAccordion x:Name="accordion">
    <syncfusion:SfAccordion.Items>
        <syncfusion:AccordionItem HeaderBackgroundColor="Pink"/>
    </syncfusion:SfAccordion.Items>
</syncfusion:SfAccordion>
{% endhighlight %}
{% highlight c# %}
SfAccordion accordion;
public MainPage()
{
    InitializeComponent();
    InitializeAccordionItems();
    this.Content = accordion;
}

private void InitializeAccordionItems()
{
    accordion = new SfAccordion();
    accordion.Items.Add(GenerateAccordionItem());
}

public AccordionItem GenerateAccordionItem()
{
    var item = new AccordionItem();
    item.HeaderBackgroundColor = Color.Pink;
    return item;
}
{% endhighlight %}
{% endtabs %}

## Icon color customization

[SfAccordion](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html) allows you to customize the color of the expander icon by using the [IconColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.AccordionItem.html#Syncfusion_XForms_Accordion_AccordionItem_IconColor) property. By default, `IconColor` is black.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfAccordion x:Name="accordion">
    <syncfusion:SfAccordion.Items>
        <syncfusion:AccordionItem IconColor="Accent"/>
    </syncfusion:SfAccordion.Items>
</syncfusion:SfAccordion>
{% endhighlight %}
{% highlight c# %}
SfAccordion accordion;
public MainPage()
{
    InitializeComponent();
    InitializeAccordionItems();
    this.Content = accordion;
}

private void InitializeAccordionItems()
{
    accordion = new SfAccordion();
    accordion.Items.Add(GenerateAccordionItem());
}

public AccordionItem GenerateAccordionItem()
{
    var item = new AccordionItem();
    item.IconColor = Color.Accent;
    return item;
}
{% endhighlight %}
{% endtabs %}

## Visual State Manager

The appearance of the [SfAccordion](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html) can be customized using the following two `VisualStates`:

* Expanded
* Collapsed

{% tabs %}
{% highlight xaml %}
<syncfusion:SfAccordion x:Name="accordion">
    <syncfusion:SfAccordion.Items>
        <syncfusion:AccordionItem IconColor="Accent">
            <syncfusion:AccordionItem.Header>
                <Grid>
                    <Label TextColor="#495F6E" Text="Cheese burger" HeightRequest="50" VerticalTextAlignment="Center"/>
                </Grid>
            </syncfusion:AccordionItem.Header>
            <syncfusion:AccordionItem.Content>
                <Grid Padding="10,10,10,10" BackgroundColor="#FFFFFF">
                    <Label TextColor="#303030" Text="Hamburger accompanied with melted cheese. The term itself is a portmanteau of the words cheese and hamburger. The cheese is usually sliced, then added a short time before the hamburger finishes cooking to allow it to melt." HeightRequest="50" VerticalTextAlignment="Center"/>
                </Grid>
            </syncfusion:AccordionItem.Content>
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
        </syncfusion:AccordionItem>
    </syncfusion:SfAccordion.Items>
</syncfusion:SfAccordion>
{% endhighlight %}
{% highlight c# %}
SfAccordion accordion;
public MainPage()
{
    InitializeComponent();
    InitializeAccordionItems();
    this.Content = accordion;
}

private void InitializeAccordionItems()
{
    accordion = new SfAccordion();
    accordion.Items.Add(GenerateAccordionItem());
}

public AccordionItem GenerateAccordionItem()
{
    var item = new AccordionItem();
    item.IconColor = Color.Accent;
    VisualStateGroupList visualStateGroupList = new VisualStateGroupList();
    VisualStateGroup commonStateGroup = new VisualStateGroup();

    VisualState expanded = new VisualState
    {
        Name = "Expanded"
    };
    expanded.Setters.Add(new Setter { Property = AccordionItem.HeaderBackgroundColorProperty, Value = Color.Red });
    expanded.Setters.Add(new Setter { Property = AccordionItem.HeaderBackgroundColorProperty, Value = Color.Red });

    VisualState collapsed = new VisualState
    {
        Name = "Collapsed"
    };
    collapsed.Setters.Add(new Setter { Property = AccordionItem.HeaderBackgroundColorProperty, Value = Color.Green });
    collapsed.Setters.Add(new Setter { Property = AccordionItem.HeaderBackgroundColorProperty, Value = Color.Green });

    commonStateGroup.States.Add(expanded);
    commonStateGroup.States.Add(collapsed);

    visualStateGroupList.Add(commonStateGroup);
    VisualStateManager.SetVisualStateGroups(item, visualStateGroupList);
    return item;
}
{% endhighlight %}
{% endtabs %}

![Xamarin Forms Accordion with VSM](accordion_images/Accordion_VSM.png)

You can download the entire source of this demo [here](https://github.com/SyncfusionExamples/Xamarin-Accordion-VisualStateManager).

>N When effects view is applied to the accordion by adding Visual as "Material", it is necessary to initialize the `Xamarin.Forms.FormsMaterial.Init` in iOS and Android.

## See also

[How to customize the Accordion icon color in Xamarin.Forms (SfAccordion)](https://www.syncfusion.com/kb/11443/)                                                                                                                                        
[How to work with RTL in Xamarin.Forms Accordion (SfAccordion)](https://www.syncfusion.com/kb/11444/)                                                                                                               
[How to customize the appearance of Accordion using VisualStateManager in Xamarin.Forms (SfAccordion)](https://www.syncfusion.com/kb/11497/)