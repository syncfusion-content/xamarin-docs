---
layout: post
title: Data source in Syncfusion segmented control for Xamarin.Forms
description: Learn how to add data source in segmented control
platform: Xamarin
control: SegmentedControl
documentation: ug
---

# Populating data source

The segmented control can be populated from a collection of strings, views, or a collection of objects in a built-in class.

## String collection

The segmented control provides the collection of strings as a data source.

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl  
    VisibleSegmentsCount="3"
    SelectedIndex="2"
    BorderColor="#3F3F3F"
    FontColor="Black"
    Color="Transparent"
    SelectionTextColor="#02A0AE"> 
<segmentCollection:List x:TypeArguments="x:String">
<x:String>Formals</x:String>
<x:String>Casuals</x:String>
<x:String>Trendy</x:String>
</segmentCollection:List>
</buttons:SfSegmentedControl>

{% endhighlight %}

{% highlight c# %}

public partial class SegmentedControlSample : ContentPage
{
SfSegmentedControl segmentedControl;
public SegmentedControlSample()
{
InitializeComponent();
segmentedControl = new SfSegmentedControl();
List<String> clothList = new List<String>
{
    "Formals","Casuals","Trendy"
};
segmentedControl.ItemsSource = clothList;
segmentedControl.Color = Color.Transparent;
segmentedControl.VisibleSegmentsCount = 3;
segmentedControl.SelectedIndex = 2;
segmentedControl.BorderColor = Color.FromHex("#3F3F3F");
segmentedControl.FontColor = Color.Black;
segmentedControl.SelectionTextColor = Color.FromHex("#02A0AE");
this.Content = segmentedControl;
}
}

{% endhighlight %}

{% endtabs %}

![](images/Data-source/Xamarin_Forms_string.png)

## Segment items

The segmented control customize the text or icons, or use other built-in customization options available for the segments. Segment item collections can also be used.

The items inside the ItemsSource can be added in the code behind as below.

{% highlight c# %}

public class ViewModel: INotifyPropertyChanged
{
private ObservableCollection<SfSegmentItem> sizeCollection = new ObservableCollection<SfSegmentItem>();
public ObservableCollection<SfSegmentItem> SizeCollection
{
get { return sizeCollection; }
set { sizeCollection = value; }
}
public ViewModel()
{
SizeCollection = new ObservableCollection<SfSegmentItem>
{
new SfSegmentItem(){Text="XS",FontColor=Color.FromHex("#3F3F3F")}, 
new SfSegmentItem(){Text="S",FontColor=Color.FromHex("#3F3F3F")},
new SfSegmentItem(){Text="M",FontColor=Color.FromHex("#3F3F3F")},
new SfSegmentItem(){Text="L",FontColor=Color.FromHex("#3F3F3F")},
new SfSegmentItem(){Text="XL",FontColor=Color.FromHex("#3F3F3F")},
};
}
}

{% endhighlight %}

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl 
    x:Name="segmentedControl"
    CornerRadius="20"
    BorderColor="#2C7BBC"
    SelectionTextColor="White"
    Color="White"
    FontColor="#3F3F3F"
    VisibleSegmentsCount="5"
    ItemsSource="{Binding SizeCollection}">
</buttons:SfSegmentedControl>

{% endhighlight %}

{% highlight c# %}

public partial class SegmentedControlSample : ContentPage
{
private SfSegmentedControl segmentedControl;
private ViewModel viewModel = new ViewModel();

public SegmentedControlSample()
{
InitializeComponent();
segmentedControl = new SfSegmentedControl();
segmentedControl.BindingContext = viewModel;
segmentedControl.ItemsSource = viewModel.SizeCollection;
segmentedControl.CornerRadius = 20;
segmentedControl.Color = Color.White;
segmentedControl.VisibleSegmentsCount = 5;
segmentedControl.BorderColor = Color.FromHex("#2C7BBC");
segmentedControl.FontColor = Color.FromHex("#3F3F3F");
segmentedControl.SelectionTextColor = Color.White;

this.Content = segmentedControl;
}
}

{% endhighlight %}

{% endtabs %} 

![](images/Data-source/Xamarin_Forms_SegmentItemCollection.png)    

## Custom views

Custom views or images can be added as segments in the segmented control.

The items inside the ItemsSource can be added in the code behind as below.

{% highlight c# %}

public class ViewModel : INotifyPropertyChanged
{
private ObservableCollection<View> viewCollection = new ObservableCollection<View>();
public ObservableCollection<View> ViewCollection
{
get { return viewCollection; }
set { viewCollection = value; }
}
private Button ResetViewButton = new Button
{
Text = "Reset",
TextColor = Color.FromHex("#979797"),
BackgroundColor = Color.White,
BorderColor = Color.FromHex("#979797"),
BorderWidth = 1,
HeightRequest = 50,
VerticalOptions = LayoutOptions.Center
};
private Button GoViewButton = new Button
{
Text = "Go",
TextColor = Color.FromHex("#979797"),
BackgroundColor = Color.White,
BorderColor = Color.FromHex("#979797"),
BorderWidth = 1,
HeightRequest = 50,
VerticalOptions = LayoutOptions.Center
};
public ViewModel()
{
ViewCollection = new ObservableCollection<View>
{ 
    ResetViewButton,
    GoViewButton
};
}
}
{% endhighlight %}

{% tabs %}

{% highlight xaml %}
<buttons:SfSegmentedControl
    BorderColor="Transparent" 
    HeightRequest="80"
    HorizontalOptions="Center"
    x:Name="segmentedControl"
    VisibleSegmentsCount="2"
    Color="Transparent"
    ItemsSource="{Binding ViewCollection}"
    SegmentPadding="30">
<buttons:SfSegmentedControl.SelectionIndicatorSettings>
<buttons:SelectionIndicatorSettings
    Color="Transparent">
</buttons:SelectionIndicatorSettings>
</buttons:SfSegmentedControl.SelectionIndicatorSettings>
</buttons:SfSegmentedControl>

 {% endhighlight %}

{% highlight c# %}
      
segmentedControl.BindingContext = viewModel;
segmentedControl.ItemsSource = viewModel.ViewCollection;
segmentedControl.BorderColor = Color.Transparent;
segmentedControl.HeightRequest = 80;
segmentedControl.HorizontalOptions = LayoutOptions.Center;
segmentedControl.VisibleSegmentsCount = 2;
segmentedControl.Color = Color.Transparent;
segmentedControl.SegmentPadding = 30;
SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
selectionIndicator.Color = Color.Transparent;
selectionIndicator.Position = SelectionIndicatorPosition.Fill;
selectionIndicator.StrokeThickness = 10;
segmentedControl.SelectionIndicatorSettings = selectionIndicator;
this.Content = segmentedControl;

{% endhighlight %}

{% endtabs %}

![](images/Data-source/Xamarin_Forms_ViewCollection.png)


