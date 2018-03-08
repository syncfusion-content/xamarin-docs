---
layout: post
title: Header and Footer in SfListView
description: Describes the Header and Footer features in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Header and Footer

This section explains how to define and customize the header and footer in the SfListView.

## Adding header and footer

The [SfListView](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView.html) allows adding and customizing appearance of the header and footer by setting the [SfListView.HeaderTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~HeaderTemplate.html) and [SfListView.FooterTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~FooterTemplate.html) properties.

To set the `HeaderTemplate`, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView"
                 ItemsSource="{Binding InboxInfo}"
                 ItemSize="100">
  <syncfusion:SfListView.HeaderTemplate>
    <DataTemplate>
      <Grid BackgroundColor="#4CA1FE" HeightRequest="45">
        <Label LineBreakMode="NoWrap"
               Margin="10,0,0,0" Text="Inbox" FontAttributes="Bold"
               FontSize="18" TextColor="White" HorizontalOptions="Center"
               VerticalOptions="Center"/>
      </Grid>
    </DataTemplate>
  </syncfusion:SfListView.HeaderTemplate>
</syncfusion:SfListView>
{% endhighlight %}
{% highlight c# %}
viewModel = new ViewModel ();
listView = new SfListView();
listView.ItemsSource = viewModel.InboxInfo;
listView.HeaderTemplate = new DataTemplate(() =>
{
   var grid = new Grid();
   grid.BackgroundColor = Color.FromHex("#4CA1FE");
   var headerLabel = new Label
   {
       BackgroundColor = Color.White,
       FontSize = 18,
       FontAttributes = FontAttributes.Bold,
       Text = "Inbox"
   };

   grid.Children.Add(headerLabel);

   return grid;
});
{% endhighlight %}
{% endtabs %}

## Customize the header and footer Size

The [SfListView](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView.html) allows customizing size of the header and footer items by setting the [SfListView.HeaderSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~HeaderSize.html) and [SfListView.FooterSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~FooterSize.html) properties. The default value is 40. These properties respond to runtime changes. Hence, it can be customized based on the requirement.

To customize the header and footer size, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" HeaderSize="70" FooterSize="60" />
{% endhighlight %}
{% highlight c# %}
listView.HeaderSize = 70;
listView.FooterSize = 60;
{% endhighlight %}
{% endtabs %}

N> For Vertical orientation, the header and footer size is considered as height and for Horizontal orientation, it will be considered as width.

## Stick the header and footer

The [SfListView](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView.html) allows sticking the header and footer items to view by enabling the [SfListView.IsStickyHeader](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~IsStickyHeader.html) and [SfListView.IsStickyFooter](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~IsStickyFooter.html) properties. If `SfListView.IsStickyHeader` is `true`, the header item will stick to top of the view. If `SfListView.IsStickyFooter` is `true`, the footer item will stick to bottom of the view.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" IsStickyHeader="True" 
                     IsStickyFooter="True" />          
{% endhighlight %}
{% highlight c# %}
listView.IsStickyHeader = true;
listView.IsStickyFooter = true;
{% endhighlight %}
{% endtabs %}

The following screenshot shows the output rendered when the header and footer is defined with `IsStickyHeader` as true and `IsStickyFooter` as true:

![](SfListView_images/SfListView-HeaderAndFooter.png)