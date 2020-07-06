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

You can dynamically resize the `SfExpander` content based on the content size by using the [DynamicSizeMode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Expander.XForms~Syncfusion.XForms.Expander.DynamicSizeMode.html) property.

The control contains the following three types of `DynamicSizeMode`:

 * Content: Autofit the content based on the content size.
 * Header: Autofit the header based on the header content size.
 * None: The dynamic changes of header and content of a `SfExpander` will not be considered. It is a default value of `DynamicSizeMode`.
 
### DynamicSizeMode as Content
 
The Content of the `SfExpander` gets re-measured and layout when its size is updated at runtime. You can add the `Editor` control to Expander content and set DynamicSizeMode to `Content` to change the content size dynamically.

{% tabs %}
{% highlight xaml %}
  <syncfusion:SfExpander DynamicSizeMode="Content" IsExpanded="True">
                    <syncfusion:SfExpander.Header>
                        <Grid HeightRequest="50">
                            <Label Text="Veggie burger" VerticalTextAlignment="Center"/>
                        </Grid>
                    </syncfusion:SfExpander.Header>

                    <syncfusion:SfExpander.Content>
                        <Grid>
                            <Editor AutoSize="TextChanges" Text="Veggie burger, garden burger, or tofu burger uses a meat analogue, a meat substitute such as tofu, textured vegetable protein, seitan (wheat gluten), Quorn, beans, grains or an assortment of vegetables, which are ground up and formed into patties."/>
                        </Grid>
                    </syncfusion:SfExpander.Content>
    </syncfusion:SfExpander>      
{% endhighlight %}
{% highlight c# %}
     expander.DynamicSizeMode = DynamicSizeMode.Content;
{% endhighlight %}
{% endtabs %}

![Xamarin Forms Expander with Content](expander_images/Dynamic_size_content.png)

![Xamarin Forms Expander DynamicSizeMode as Content](expander_images/Dynamic_size_content_Ex.png)

### DynamicSizeMode as Header

The Header of the `SfExpander` gets re-measured and layout when its size is updated at runtime. You can add the `Editor` control to Expander header and set DynamicSizeMode to `Header` to change the header size dynamically.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfExpander DynamicSizeMode="Content" IsExpanded="True">
                    <syncfusion:SfExpander.Header>
                        <Grid HeightRequest="50">
                            <Editor Text="Veggie burger" AutoSize="TextChanges" FontSize="Large"/>
                        </Grid>
                    </syncfusion:SfExpander.Header>

                    <syncfusion:SfExpander.Content>
                        <Grid>
                            <Label Text="Veggie burger, garden burger, or tofu burger uses a meat analogue, a meat substitute such as tofu, textured vegetable protein, seitan (wheat gluten), Quorn, beans, grains or an assortment of vegetables, which are ground up and formed into patties."/>
                        </Grid>
                    </syncfusion:SfExpander.Content>
</syncfusion:SfExpander> 
{% endhighlight %}
{% highlight c# %}
     expander.DynamicSizeMode = DynamicSizeMode.Header;
{% endhighlight %}
{% endtabs %}	

![Xamarin Forms Expander with Header](expander_images/Dynamic_size_Header.png)

![Xamarin Forms Expander DynamicSizeMode as Header](expander_images/Dynamic_size_Header_Ex.png)
