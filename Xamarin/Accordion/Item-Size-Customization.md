---
layout: post
title: Item Size Customization in Syncfusion Accordion
description: Describes the Item Size Customization in SfAccordion using ItemSize property and DynamicSizeMode property.
platform: xamarin
control: SfAccordion
documentation: ug
---

# Item Size Customization in Xamarin Accordion (SfAccordion)

This section explains how to customize the item size in the SfAccordion.

## AutoFit the accordion based on content

You can dynamically resize the `SfAccordion` content based on the content size using the [DynamicSizeMode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Expander.XForms~Syncfusion.XForms.Expander.DynamicSizeMode.html) property.

The control contains three types of `DynamicSizeMode,` they are:

 * Content: Autofit the content based on the content size.
 * Header: Autofit the header based on the header content size.
 * None: The dynamic changes of header and the content of a `SfAccordion` will not be considered. It is a default value of the `DynamicSizeMode.`
 
### DynamicSizeMode as Content
 
The content and layout of the `SfAccordion` get re-measured when its size is updated at runtime. You can add the `Label` control to the accordion content and set the DynamicSizeMode to `Content` to change the content size dynamically.

{% tabs %}
{% highlight xaml %}
<StackLayout>
    <Button x:Name="button" Text="DynamicSizeMode as Content" Clicked="Button_Clicked"/>
    <syncfusion:SfAccordion x:Name="accordion" DynamicSizeMode="Content" >
        <syncfusion:AccordionItem>
            <syncfusion:AccordionItem.Header>
                <Grid>
                    <Image Source="menu.png" Margin="3" Aspect="AspectFit"/>
                    <Label x:Name="label1" TextColor="#495F6E" Text="Items" FontSize="16" VerticalOptions="CenterAndExpand"/>
                </Grid>
            </syncfusion:AccordionItem.Header>

            <syncfusion:AccordionItem.Content>
                <Grid>
                    <Label x:Name="veg" TextColor="#303030" FontSize="16" Text="Veggie burger" IsVisible="True"/>
                    <Label x:Name="garden"  TextColor="#303030" FontSize="16" Text="Garden burger" Grid.Row="1" IsVisible="True"/>
                    <Label x:Name="tofu" TextColor="#303030" FontSize="16" Text="Tofu burger" IsVisible="False" Grid.Row="2" HorizontalOptions="Start"/>
                    <Label x:Name="total" TextColor="#303030" FontSize="16" Text="Total Amount Paid" IsVisible="False"  FontAttributes="Bold" Grid.Row="3"/>
                    <Label x:Name="vegrate"  TextColor="#303030" FontSize="16" HorizontalOptions="End" Text="₹200.00" Grid.Column="1" IsVisible="True"/>
                    <Label x:Name="gardenrate" TextColor="#303030" FontSize="16" HorizontalOptions="End" Text="₹300.00" Grid.Row="1" IsVisible="True" Grid.Column="1"/>
                    <Label x:Name="tofurate"  TextColor="#303030" FontSize="16" HorizontalOptions="End" IsVisible="False" Text="₹450.00" Grid.Row="2" Grid.Column="1"/>
                    <Label x:Name="amount"  TextColor="#303030" FontSize="16" HorizontalOptions="End" IsVisible="False" Text="₹950.00" FontAttributes="Bold" Grid.Row="3" Grid.Column="1"/>
                </Grid>
            </syncfusion:AccordionItem.Content>
        </syncfusion:AccordionItem>
    </syncfusion:SfAccordion>
</StackLayout>
{% endhighlight %}
{% highlight c# %}
accordion.DynamicSizeMode = DynamicSizeMode.Content;
private void Button_Clicked(object sender, EventArgs e)
{
    if (!tofu.IsVisible)
    {
        tofu.IsVisible = true;
        tofurate.IsVisible = true;
    }
    else if (!total.IsVisible)
    {
        total.IsVisible = true;
        amount.IsVisible = true;
    }
    else
    {
        total.IsVisible = false;
        amount.IsVisible = false;
        tofu.IsVisible = false;
        tofurate.IsVisible = false;
    }
}
{% endhighlight %}
{% endtabs %}

![Xamarin Forms Accordion DynamicSizeMode as Content](accordion_images/Dynamic_size_content.gif)

### DynamicSizeMode as Header

The header and layout of the `SfAccordion` get re-measured when its size is updated at runtime. You can add the `Label` control to the accordion header and set the DynamicSizeMode to `Header` to change the header size dynamically.

{% tabs %}
{% highlight xaml %}
<StackLayout>
    <Button x:Name="button" Text="DynamicSizeMode as Header" Clicked="Button_Clicked"/>
    <syncfusion:SfAccordion x:Name="accordion" DynamicSizeMode="Header" >
        <syncfusion:AccordionItem>
            <syncfusion:AccordionItem.Header>
                <Grid>
                    <Image Source="menu.png" Margin="3" Aspect="AspectFit"/>
                    <Label x:Name="label1" TextColor="#495F6E" Text="Items" FontSize="16" VerticalOptions="CenterAndExpand"/>
                </Grid>
            </syncfusion:AccordionItem.Header>

            <syncfusion:AccordionItem.Content>
                <Grid>
                    <Label x:Name="veg" TextColor="#303030" FontSize="16" Text="Veggie burger" IsVisible="True"/>
                    <Label x:Name="garden"  TextColor="#303030" FontSize="16" Text="Garden burger" Grid.Row="1" IsVisible="True"/>
                    <Label x:Name="vegrate"  TextColor="#303030" FontSize="16" HorizontalOptions="End" Text="₹200.00" Grid.Column="1" IsVisible="True"/>
                    <Label x:Name="gardenrate" TextColor="#303030" FontSize="16" HorizontalOptions="End" Text="₹300.00" Grid.Row="1" IsVisible="True" Grid.Column="1"/>
                </Grid>
            </syncfusion:AccordionItem.Content>
        </syncfusion:AccordionItem>
    </syncfusion:SfAccordion>
</StackLayout>    
{% endhighlight %}
{% highlight c# %}
accordion.DynamicSizeMode = DynamicSizeMode.Header;
private void Button_Clicked(object sender, EventArgs e)
{
    if (label1.FontSize == 16)
    {
        label1.FontSize = 28;
    }
    else if (label1.FontSize == 28)
    {
        label1.FontSize = 35;
    }
}
{% endhighlight %}
{% endtabs %}	

![Xamarin Forms Accordion DynamicSizeMode as Header](accordion_images/Dynamic_size_header.gif)