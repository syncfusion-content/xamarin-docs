---
layout: post
title: BindableLayout | Accordion for Xamarin.Forms | Syncfusion
description: This section described about how to bind AccordionItem to Xamarin.Forms Accordion (SfAccordion) using BindableLayout.
platform: xamarin
control: SfAccordion
documentation: ug
---

# BindableLayout in Xamarin Accordion (SfAccordion)

The [SfAccordion](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html) allows you to set a collection of items by setting the `BindableLayout.ItemsSource` and `BindableLayout.ItemTemplate` properties. The Accordion supports Bindable Layout in Xamarin.Forms version 3.5 and above.

## Creating Data Model

Create a simple data model to bind the data for `SfAccordion` as shown in the following code example in a new class file, and save it as ItemInfo.cs file:

{% tabs %}
{% highlight c# %}
public class ItemInfo
{
    public string Name { get; set; }
    public string Description { get; set; }
}
{% endhighlight %}
{% endtabs %}

Create a model repository class with the ItemInfo collection property initialized with required number of data objects in a new class file as shown in the following code example, and save it as ItemInfoRepository.cs file.

{% tabs %}
{% highlight c# %}
public class ItemInfoRepository
{
    public ObservableCollection<ItemInfo> Info { get; set; }

    public ItemInfoRepository()
    {
        Info = new ObservableCollection<ItemInfo>();
        Info.Add(new ItemInfo() { Name = "Cheese burger", Description = "Hamburger accompanied with melted cheese. The term itself is a portmanteau of the words cheese and hamburger. The cheese is usually sliced, then added a short time before the hamburger finishes cooking to allow it to melt." });
        Info.Add(new ItemInfo() { Name = "Veggie burger", Description = "Veggie burger, garden burger, or tofu burger uses a meat analogue, a meat substitute such as tofu, textured vegetable protein, seitan (wheat gluten), Quorn, beans, grains or an assortment of vegetables, which are ground up and formed into patties." });
        Info.Add(new ItemInfo() { Name = "Barbecue burger", Description = "Prepared with ground beef, mixed with onions and barbecue sauce, and then grilled. Once the meat has been turned once, barbecue sauce is spread on top and grilled until the sauce caramelizes." });
        Info.Add(new ItemInfo() { Name = "Chili burger", Description = "Consists of a hamburger, with the patty topped with chili con carne."});
    }
}
{% endhighlight %}
{% endtabs %}

Set the ViewModel instance as BindingContext of your page to bind properties of ViewModel to `SfAccordion`.

{% tabs %} 
{% highlight xaml %}
<ContentPage.BindingContext>
    <local:ItemInfoRepository/>
</ContentPage.BindingContext>
{% endhighlight %}
{% highlight c# %}
this.BindingContext = new ItemInfoRepository();      
{% endhighlight %}
{% endtabs %}

## Binding data to SfAccordion

`SfAccordion` can be bounded with data by setting the ItemsSource property of BindableLayout.

The following code example binds the collection created in previous step to the `Bindable.ItemsSource` property.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Accordion;assembly=Syncfusion.Expander.XForms"
             xmlns:local="clr-namespace:AccordionBindableLayout"
             x:Class="AccordionBindableLayout.MainPage">
    <syncfusion:SfAccordion x:Name="Accordion" BindableLayout.ItemsSource="{Binding Info}"/>
</ContentPage>      
{% endhighlight %}
{% highlight c# %}
SfAccordion Accordion = new SfAccordion();
BindableLayout.SetItemsSource(Accordion, viewModel.Info);
{% endhighlight %}
{% endtabs %}

## Defining the AccordionItem

The [SfAccordion](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html) accepts `AccordionItem` as its child element. The appearance of each `AccordionItem` can be defined by setting the `BindableLayout.ItemTemplate` property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfAccordion x:Name="Accordion" BindableLayout.ItemsSource="{Binding Info}">
    <BindableLayout.ItemTemplate>
        <DataTemplate>
            <syncfusion:AccordionItem>
                <syncfusion:AccordionItem.Header>
                    <Grid>
                        <Label Text="{Binding Name}"/>
                    </Grid>
                </syncfusion:AccordionItem.Header>
                <syncfusion:AccordionItem.Content>
                    <Grid>
                        <Label Text="{Binding Description}"/>
                    </Grid>
                </syncfusion:AccordionItem.Content>
            </syncfusion:AccordionItem>
        </DataTemplate>
    </BindableLayout.ItemTemplate>
</syncfusion:SfAccordion>     
{% endhighlight %}
{% highlight c# %}
SfAccordion Accordion = new SfAccordion();
DataTemplate ItemTemplate = new DataTemplate(() =>
{
    AccordionItem accordionItem = new AccordionItem();
    var headerGrid = new Grid();
    var header = new Label();
    header.SetBinding(Label.TextProperty, new Binding("Name"));
    headerGrid.Children.Add(header);
    accordionItem.Header = headerGrid;
    var contentGrid = new Grid();
    var content = new Label();
    content.SetBinding(Label.TextProperty, new Binding("Description"));
    contentGrid.Children.Add(content);
    accordionItem.Content = contentGrid;
    return accordionItem;
});
BindableLayout.SetItemTemplate(Accordion, ItemTemplate);
BindableLayout.SetItemsSource(Accordion, viewModel.Info);
{% endhighlight %}
{% endtabs %}

![Xamarin Forms Accordion with Bimdable Layout](accordion_images/xamarin-forms-accordion.png)

You can download the entire source of this demo [here](https://github.com/SyncfusionExamples/Xamarin-Populate-Accordion-Items-using-Bindable-Layout).

## Events

### Get the index of expanded or collapsed accordion item.

You can get the index of the interacted `AccordionItem` by using the [Collapsed](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html). It will occur after an AccordionItem is collapsed when tapping on the Header. The [ExpandedAndCollapsedEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.ExpandedAndCollapsedEventArgs.html) properties provides data for the `collapsed` event.  

{% tabs %}
{% highlight xaml %}
<syncfusion:SfAccordion x:Name="Accordion" Collapsed="Accordion_Collapsed">
{% endhighlight %}
{% highlight c# %}
Accordion.Collapsed += Accordion_Collapsed;
private void Accordion_Collapsed(object sender, Syncfusion.XForms.Accordion.ExpandedAndCollapsedEventArgs e)
{
    var value = e.Index.ToString();
    DisplayAlert("Index", value, "ok");
}
{% endhighlight %}
{% endtabs %}		

Using the [Expanded](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html) event, you can get the index of the interacted `AccordionItem.` It will occur after an AccordionItem is expanded when tapping on the Header. The [ExpandedAndCollapsedEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.ExpandedAndCollapsedEventArgs.html) properties provides data for the `expanded` event.  

{% tabs %}
{% highlight xaml %}
<syncfusion:SfAccordion x:Name="Accordion" Expanded="Accordion_Expanded">
{% endhighlight %}
{% highlight c# %}
Accordion.Expanded += Accordion_Expanded;
private void Accordion_Expanded(object sender, Syncfusion.XForms.Accordion.ExpandedAndCollapsedEventArgs e)
{
    var value = e.Index.ToString();
    DisplayAlert("Index", value, "ok");
}
{% endhighlight %}
{% endtabs %}

### Restricting the accordion item expanding and collapsing 

The [Collapsing](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html) event occurs while collapsing an `AccordionItem` when tapping on the Header. You can cancel the collapsing action by using the `Cancel` property in the event args. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfAccordion x:Name="Accordion" Collapsing="Accordion_Collapsing">
{% endhighlight %}
{% highlight c# %}
Accordion.Collapsing += Accordion_Collapsing;
private void Accordion_Collapsing(object sender, ExpandingAndCollapsingEventArgs e)
{
   e.cancel = true;
}
{% endhighlight %}
{% endtabs %}

You can also get the index of the interacted `AccordionItem` by using the `index` property of the [ExpandingAndCollapsingEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.ExpandingAndCollapsingEventArgs.html).

{% tabs %}
{% highlight c# %}
private void Accordion_Collapsing(object sender, ExpandingAndCollapsingEventArgs e)
{
    var value = e.Index.ToString();
    DisplayAlert("Index", value, "ok");
}
{% endhighlight %}
{% endtabs %}

The [Expanding](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html) event occurs while expanding an `AccordionItem` when tapping on the Header. You can cancel the expanding action by using the `Cancel` property in the event args. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfAccordion x:Name="Accordion" Expanding="Accordion_Expanding">
{% endhighlight %}
{% highlight c# %}
Accordion.Expanding += Accordion_Expanding;
private void Accordion_Expanding(object sender, ExpandingAndCollapsingEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

You can also get the index of the interacted `AccordionItem` by using the `index` property of the [ExpandingAndCollapsingEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.ExpandingAndCollapsingEventArgs.html).

{% tabs %}
{% highlight c# %}
private void Accordion_Expanding(object sender, ExpandingAndCollapsingEventArgs e)
{
    var value = e.Index.ToString();
    DisplayAlert("Index",value, "ok");
}
{% endhighlight %}
{% endtabs %}

## See also

[How to bind ViewModel data to Accordion in Xamarin.Forms (SfAccordion)](https://www.syncfusion.com/kb/11404/)                                                                                                                                                                                                                              
[How to work with Accordion with SfListView in Xamarin.Forms (SfAccordion)](https://www.syncfusion.com/kb/11448/)`                                                                                                                                                             
