---
layout: post
title: Item Size Customization in Syncfusion Expander
description: Describes the Item Size Customization in SfExpander using ItemSize property and DynamicSizeMode property.
platform: xamarin
control: SfExpander
documentation: ug
---

# Item Size Customization in Xamarin Expander (SfExpander)

This section explains how to customize the item size in the SfExpander.

## AutoFit the expander based on content

You can dynamically resize the `SfExpander` content based on the content size using the [DynamicSizeMode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Expander.XForms~Syncfusion.XForms.Expander.DynamicSizeMode.html) property.

The control contains three types of `DynamicSizeMode,` they are:

 * Content: Autofit the content based on the content size.
 * Header: Autofit the header based on the header content size.
 * None: The dynamic changes of header and the content of a `SfExpander` will not be considered. It is a default value of `DynamicSizeMode`.
 
### DynamicSizeMode as Content
 
The content and layout of `SfExpander` get re-measured when its size is updated at runtime. You can add the `Label` control to expander content and set the DynamicSizeMode to `Content` to change the content size dynamically.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfExpander DynamicSizeMode="Content" IsExpanded="True">
    <syncfusion:SfExpander.Header>
        <Grid>
            <Label Text="Veggie burger" x:Name="label" FontSize="Large"/>
        </Grid>
    </syncfusion:SfExpander.Header>

    <syncfusion:SfExpander.Content>
        <Grid>
		    <Button Text="Change Content Text" TextColor="Black" x:Name="button1" BackgroundColor="BlueViolet" Clicked="button1_Clicked"/>
            <Label x:Name="label1" Text="Veggie burger, garden burger, or tofu burger uses a meat analogue, a meat substitute such as tofu, textured vegetable protein, seitan (wheat gluten), Quorn, beans, grains or an assortment of vegetables, which are ground up and formed into patties."/>
        </Grid>
    </syncfusion:SfExpander.Content>
</syncfusion:SfExpander>      
{% endhighlight %}
{% highlight c# %}
expander.DynamicSizeMode = DynamicSizeMode.Content;
private void button1_Clicked(object sender, EventArgs e)
{
   label1.Text = "Veggie burger, garden burger, or tofu burger uses a meat analogue, a meat substitute such as tofu, textured vegetable protein, seitan (wheat gluten), Quorn, beans, grains or an assortment of vegetables, which are ground up and formed into patties.It comes with the cheesiness of a pizza within a burger, instead of a regular patty. Basically, they look like a burger and taste like a pizza! The three main burger pizza options available in the store are: Classic Veg Burger Pizza , Premium Veg Burger Pizza , Classic Non-Veg.";
}
{% endhighlight %}
{% endtabs %}

![Xamarin Forms Expander DynamicSizeMode as Content](expander_images/Dynamic_size_content.gif)

### DynamicSizeMode as Header

The header and layout of the `SfExpander` get re-measured when its size is updated at runtime. You can add the `Label` control to the expander header and set the DynamicSizeMode to `Header` to change the header size dynamically.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfExpander DynamicSizeMode="Content" IsExpanded="True">
    <syncfusion:SfExpander.Header>
        <Grid>
		    <Button Text="Change Header Text" TextColor="Black" x:Name="button" BackgroundColor="BlueViolet" Clicked="button_Clicked"/>
            <Label Text="Veggie burger" x:Name="label" FontSize="Large"/>
        </Grid>
    </syncfusion:SfExpander.Header>

    <syncfusion:SfExpander.Content>
        <Grid>
            <Label x:Name="label1" Text="Veggie burger, garden burger, or tofu burger uses a meat analogue, a meat substitute such as tofu, textured vegetable protein, seitan (wheat gluten), Quorn, beans, grains or an assortment of vegetables, which are ground up and formed into patties."/>
        </Grid>
    </syncfusion:SfExpander.Content>
</syncfusion:SfExpander> 
{% endhighlight %}
{% highlight c# %}
expander.DynamicSizeMode = DynamicSizeMode.Header;
private void button_Clicked(object sender, EventArgs e)
{
   label.Text = "Veggie burger, garden burger, or tofu burger";
}
{% endhighlight %}
{% endtabs %}	

![Xamarin Forms Expander DynamicSizeMode as Header](expander_images/Dynamic_size_Header.gif)
