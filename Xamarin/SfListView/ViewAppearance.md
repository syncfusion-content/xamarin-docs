---
layout: post
title: View Appearance in SfListView
description: Describes about view appearance and different functionalities in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# View Appearance

The SfListView allows customizing appearance of the underlying data and provides different functionalities to the end-user.

## Defining the item template

A template can be used to present the data in a way that makes sense for the application by using different controls. The SfListView allows customizing appearance of view by setting the [ItemTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTemplate.html) property. By default the [SfLabel](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfLabel.html) is used to present the list of data.

## Defining the data template selector

The SfListView allows customizing appearance of the each item with different templates based on specific constraints using the [DataTemplateSelector](https://developer.xamarin.com/api/type/Xamarin.Forms.DataTemplateSelector/). You can choose a `DataTemplate` for each item at runtime based on the value of data-bound property using `DataTemplateSelector`.

### Create a data template selector

Create the custom class inherits from `DataTemplateSelector`, and override the `OnSelectTemplate` method to return the `DataTemplate` for that item. At runtime, the SfListView invokes the `OnSelectTemplate` method for each item and passes the data object as parameter.

{% highlight c# %}

class MyDataTemplateSelector : Xamarin.Forms.DataTemplateSelector
{

   private readonly DataTemplate incomingDataTemplate;
   private readonly DataTemplate outgoingDataTemplate;

   public MyDataTemplateSelector()
   {
      this.incomingDataTemplate = new DataTemplate(typeof(IncomingViewCell));
      this.outgoingDataTemplate = new DataTemplate(typeof(OutgoingViewCell));      
   }

   protected override DataTemplate OnSelectTemplate(object item, BindableObject container)
   {
      var message = item as Message;
      if (message == null)
         return null;
      return message.IsIncoming ? this.incomingDataTemplate : this.outgoingDataTemplate;
   }

}

{% endhighlight %}

### Applying the data template selector to the SfListView

Assign that custom `DataTemplateSelector` to the [ItemTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTemplate.html) of the SfListView either in XAML or C#.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             x:Class="DataTemplateSelector.MainPage"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             xmlns:local="clr-namespace:DataTemplateSelector;assembly=DataTemplateSelector">
  <ContentPage.Resources>
    <ResourceDictionary>
      <local:MyDataTemplateSelector x:Key="MessageTemplateSelector" />
    </ResourceDictionary>
  </ContentPage.Resources>
  <Grid>
    <syncfusion:SfListView x:Name="ListView"
                           ItemTemplate="{StaticResource MessageTemplateSelector}"
                           ItemsSource="{Binding Messages}"
                           ItemSize="100">
    </syncfusion:SfListView>
  </Grid>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
public class MainPageCs : ContentPage
{
   public MainPageCs()
   {
      var viewModel = new MainPageViewModel();
      BindingContext = viewModel;
      Content = new SfListView()
      {
          ItemSize = 100,
          ItemsSource = viewModel.Messages,
          ItemTemplate = new MyDataTemplateSelector()
      };
   }
}
{% endhighlight %}
{% endtabs %}

Now run the application to render the following output. You can also download the entire source code of this demo from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Listview_DataTemplateSelector659971950).

![](SfListView_images/SfListView-DataTemplateSelector.png)

## Defining the item size

The SfListView allows customizing the size of items by setting the [ItemSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemSize.html) property. The default value of this property is 40. This property responds to runtime changes. Hence, it can be customized based on the requirement.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" ItemSize="60" />
{% endhighlight %}
{% highlight c# %}
listView.ItemSize = 60;
{% endhighlight %}
{% endtabs %}

N> For Vertical orientation, the item size is considered as height and for Horizontal orientation, it will be considered as width.

## Set spacing between items

The SfListView allows specifying spacing between the each item in the list by setting the [ItemSpacing](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemSpacing.html) property. Generate the space around the item. The default value of this property is 0. This property responds to runtime changes. Hence it can be customized based on the requirement.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" ItemSpacing="5,0,0,0" />
{% endhighlight %}
{% highlight c# %}
listView.ItemSpacing = new Thickness(5, 0, 0, 0)
{% endhighlight %}
{% endtabs %}

## Orientation

The SfListView allows you to layout every item in the [SfListView.ItemsSource](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemsSource.html) property in either vertical or horizontal orientation by setting the [SfListView.Orientation](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~Orientation.html). The default orientation is `Vertical`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" Orientation="Horizontal" />
{% endhighlight %}
{% highlight c# %}
listView.Orientation = Orientation.Horizontal;
{% endhighlight %}
{% endtabs %}

![](SfListView_images/SfListView-Orientation.png)

## Defining the scrollbar visibility

The SfListView provides an option to enable or disable the `Scrollbar` visibility by using the [IsScrollBarVisible](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~IsScrollBarVisible.html) property. By default, the value will be `true`.  

N> Due to some restrictions in native ScrollView renderer in Xamarin.Forms, you cannot change the `IsScrollBarVisible` value at runtime. It can be defined only while initializing the SfListView. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" IsScrollBarVisible="False" />
{% endhighlight %}
{% highlight c# %}
listView.IsScrollBarVisible = false; 
{% endhighlight %}
{% endtabs %}

## Animate the item using OnItemAppearing method 

SfListView provides a support for animate the items by using an [OnItemAppearing](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ListViewItem~OnItemAppearing.html) virtual method. It's raised when the items appears in the view on scrolling, loading and navigating from one page to another page. To apply the animation effect for items, follow the steps,

### Extension class for ItemGenerator

{% highlight c# %}
public class ItemGeneratorExt : ItemGenerator
{
    public SfListView listView;
	
    public ItemGeneratorExt(SfListView listView) : base(listView)
    {
        this.listView = listView;
    }

    protected override ListViewItem OnCreateListViewItem(int itemIndex, ItemType type, object data = null)
    {
        if (type == ItemType.Record)
            return new ListViewItemExt(this.listView);
        return base.OnCreateListViewItem(itemIndex, type, data);
    }
}
{% endhighlight %}

### Initialize and assign ItemGenerator extension to ListView

{% highlight c# %}
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        this.listView.ItemGenerator = new ItemGeneratorExt(this.listView);
    }
}
{% endhighlight %}

### Extension class for ListViewItem
 
To apply the animation for items while appearing, override the [OnItemAppearing](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ListViewItem~OnItemAppearing.html) method.

{% highlight c# %}
public class ListViewItemExt : ListViewItem
{
    private SfListView listView;

    public ListViewItemExt(SfListView listView)
    {
        this.listView = listView
    }

    protected override void OnItemAppearing()
    {
        this.Opacity = 0;
        this.FadeTo(1, 400, Easing.SinInOut);
        base.OnItemAppearing();
    }
}
{% endhighlight %}

Here `FadeTo` animation is applied for [ListViewItem](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ListViewItem.html), while comes in the view. The screenshot shows the output of the item animation on scrolling. You can also download the entire source code of this demo from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/ItemAppearing-659512864.zip).

![](SfListView_images/SfListView-ItemAppearingAnimation.gif)