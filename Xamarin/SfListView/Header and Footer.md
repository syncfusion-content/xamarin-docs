---
layout: post
title: Header and Footer | SfListView | Xamarin | Syncfusion
description: How to enable header and footer, about properties and customizations available for header and footer in a SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Header and Footer

This section explains you about how to define and customize the header and footer in SfListView and about properties which provides different functionalities for header and footer.

## Customization of Header and Footer

[SfListView](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView.html) let’s you to customize the appearance of header and footer by using [SfListView.HeaderTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~HeaderTemplate.html) and [SfListView.FooterTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~FooterTemplate.html) properties.

The following example illustrates how to set the `HeaderTemplate` in SfListView.

{% tabs %}
{% highlight xaml %}
<xmlns:sync="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">

  <sync:SfListView x:Name="listView" 
                   ItemsSource="{Binding InboxInfo}"
                   ItemSize="100">
    <sync:SfListView.HeaderTemplate>
     <DataTemplate>
        <Grid BackgroundColor="#4CA1FE" HeightRequest="45">
          <Label LineBreakMode="NoWrap"
                 Margin="10,0,0,0" Text="Inbox" FontAttributes="Bold"
                 FontSize="18" TextColor="White" HorizontalOptions="Center" VerticalOptions="Center"/>
        </Grid>
      </DataTemplate>
    </sync:SfListView.HeaderTemplate>
  </sync:SfListView>
{% endhighlight %}
{% highlight c# %}
using Syncfusion.ListView.XForms;
using Xamarin.Forms;

namespace GettingStarted
{
    public class App : Application
    {
        SfListView listView;
        ViewModel viewModel;
        public App()
        {
            viewModel = new ViewModel ();
            listView = new SfListView();
            listView.ItemSize = 100;
            listView.ItemsSource = viewModel.InboxInfo;
            listView.HeaderTemplate = new DataTemplate(() =>
            {
                var grid = new Grid();
                grid.BackgroundColor = Color.FromHex("#4CA1FE");
                var headerlabel = new Label
                {
                    BackgroundColor = Color.White,
                    FontSize = 18,
                    FontAttributes = FontAttributes.Bold,
                    Text = "Inbox"
                };

                grid.Children.Add(headerlabel);

                return grid;
            });
            MainPage = new ContentPage { Content = listView };
        }
    }
} 
{% endhighlight %}
{% endtabs %}

## Customize the Header and Footer Size

[SfListView](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView.html) allows you to customize the size of the header and footer items by setting the [SfListView.HeaderSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~HeaderSize.html) and [SfListView.FooterSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~FooterSize.html) properties. The default value is 40. These properties respond to runtime changes and hence you can customize it based on your requirement.

The following code example illustrates how to customize the header and footer size in SfListView.

{% tabs %}
{% highlight xaml %}
<listView:SfListView x:Name="listView" HeaderSize="70" FooterSize="60" />
{% endhighlight %}
{% highlight c# %}
listView.HeaderSize = 70;
listView.FooterSize = 60;
{% endhighlight %}
{% endtabs %}

## Stick the Header and Footer

[SfListView](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView.html) allows you to stick the header and footer items to view by enabling the properties [SfListView.IsStickyHeader](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~IsStickyHeader.html) and [SfListView.IsStickyFooter](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~IsStickyFooter.html). If `SfListView.IsStickyHeader` is `true`, the header item is stick to top of the view and `SfListView.IsStickyFooter` is `true`, the footer item is stick to bottom of the view.

{% tabs %}
{% highlight xaml %}
<listView:SfListView x:Name="listView" IsStickyHeader="True" 
                     IsStickyFooter="True" />          
{% endhighlight %}
{% highlight c# %}
listView.IsStickyHeader = true;
listView.IsStickyFooter = true;
{% endhighlight %}
{% endtabs %}