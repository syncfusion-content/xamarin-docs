---
layout: post
title: Display Mode in Xamarin Segmented Control | Syncfusion<sup>&reg;</sup>
description: Explore different display mode options in Syncfusion<sup>&reg;</sup> Xamarin Segmented Control (SfSegmentedControl).
platform: Xamarin
control: SegmentedControl
documentation: ug
---

# Display Mode in Xamarin Segmented Control (SfSegmentedControl)

Depending on the application, different scenarios may require varied display modes for effective communication. The segmented control supports three options: icons, text, or a combination of both.

## Text

By default, items populated in the segmented control are displayed as text.

Add the following namespace for loading data collections in string format:

{% highlight xaml %}

xmlns:segmentCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"

{% endhighlight %}

{% tabs %}

{% highlight xaml %}

<buttons:SfSegmentedControl 
    x:Name="segmentedControl" 
    Margin="10,0"
    CornerRadius="15"
    SegmentHeight="50"
    BorderColor="Transparent"
    SelectedIndex="1"
    Color="#048EAC"
    FontSize="22"
    DisplayMode="Text"
    VisibleSegmentsCount="3"
    FontColor="#FFFFFF"
    SelectionTextColor="#048EAC"
    VerticalOptions="Center"
    HorizontalOptions="Center">
    <segmentCollection:List x:TypeArguments="x:String">
    <x:String>Day</x:String>
    <x:String>Week</x:String>
    <x:String>Month</x:String>
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

    List<String> periodsList = new List<String>
    {
           "Day","Week","Month"
    };
    segmentedControl.ItemsSource = periodsList;
    segmentedControl.DisplayMode = SegmentDisplayMode.Text;
    segmentedControl.Color = Color.FromHex("#048EAC");
    segmentedControl.SegmentHeight= 50;
    segmentedControl.VisibleSegmentsCount = 3;
    segmentedControl.CornerRadius = 15;
    segmentedControl.HeightRequest = 50;
    segmentedControl.SelectedIndex = 1;
    segmentedControl.BorderColor = Color.Transparent;
    segmentedControl.FontColor = Color.FromHex("#FFFFFF");
    segmentedControl.FontSize = 22;
    segmentedControl.VerticalOptions = LayoutOptions.Center;
    segmentedControl.HorizontalOptions = LayoutOptions.Center;
    segmentedControl.SelectionTextColor = Color.FromHex("#048EAC");
    this.Content = segmentedControl;
}
}

{% endhighlight %}

{% endtabs %}

![Display Mode as Text in segmented control](images/Display-mode/Xamarin_Forms_Text.png)

## Image 

Items populated in the segmented control can also be displayed as icons.

The data source for the segmented control can be set as follows:

> Note: In this documentation, a ttf file is generated using Metro Studio, and a custom icon text name “6” is provided. Learn more from this [link](https://help.syncfusion.com/metro-studio/export-icon-font#customization).

{% highlight c# %}

public class ViewModel
{
    private ObservableCollection<SfSegmentItem> imageCollection;
    public ObservableCollection<SfSegmentItem> ImageCollection
    {
        get { return imageCollection; }
        set { imageCollection = value; }
    }

    public ViewModel()
    {
        ImageCollection = new ObservableCollection<SfSegmentItem>
        {
            new SfSegmentItem(){IconFont = "6", FontIconFontColor=Color.FromHex("#FFFFFF"), FontColor=Color.FromHex("#FFFFFF")},          
            new SfSegmentItem(){IconFont = "6", FontIconFontColor=Color.FromHex("#FFFFFF"), FontColor=Color.FromHex("#FFFFFF")},     
            new SfSegmentItem(){IconFont = "6", FontIconFontColor=Color.FromHex("#FFFFFF"), FontColor=Color.FromHex("#FFFFFF")},          
        };
    }
}
{% endhighlight %}

{% tabs %}

{% highlight xaml %}

<ContentPage.BindingContext>
    <local:ViewModel/>
</ContentPage.BindingContext>
<buttons:SfSegmentedControl 
    x:Name="segmentedControl" 
    DisplayMode="Image"
    SelectedIndex="1"
    ItemsSource = "{Binding ImageCollection}"
    VisibleSegmentsCount="3"
    SelectionTextColor="#FFFFFF"
</buttons:SfSegmentedControl>

{% endhighlight %}

{% highlight c# %}

public partial class SegmentedControlSample : ContentPage
{
    private ViewModel viewModel = new ViewModel();
    SfSegmentedControl segmentedControl;

    public SegmentedControlSample()
    {
        segmentedControl = new SfSegmentedControl();
        segmentedControl.ItemsSource = viewModel.ImageCollection;
        segmentedControl.DisplayMode = SegmentDisplayMode.Image;
        segmentedControl.SelectedIndex = 1;
        segmentedControl.VisibleSegmentsCount = 3;
        segmentedControl.SelectionTextColor = Color.FromHex("#FFFFFF");
        this.Content = segmentedControl;
        this.BindingContext = viewModel;
    }
}

{% endhighlight %}

{% endtabs %}

![Display Mode as Image in segmented control](images/Display-mode/Xamarin_Forms_Image.png)

## Image with Text

Items in the segmented control can be displayed as icons with accompanying text.

> Note: Refer to the previous note on generating a ttf file using Metro Studio for icon text names, detailed [here](https://help.syncfusion.com/metro-studio/export-icon-font#customization).
{% highlight c# %}

public class ViewModel 
{
    private ObservableCollection<SfSegmentItem> imageTextCollection;
    public ObservableCollection<SfSegmentItem> ImageTextCollection
    {
        get { return imageTextCollection; }
        set { imageTextCollection = value; }
    }

    public ViewModel()
    {
        imageTextCollection = new ObservableCollection<SfSegmentItem>
        {
            new SfSegmentItem(){IconFont = "6", FontIconFontColor=Color.FromHex("#FFFFFF"), FontColor=Color.FromHex("#FFFFFF"), Text = "Day"},          
            new SfSegmentItem(){IconFont = "6", FontIconFontColor=Color.FromHex("#FFFFFF"), FontColor=Color.FromHex("#FFFFFF"), Text = "Week"},     
            new SfSegmentItem(){IconFont = "6", FontIconFontColor=Color.FromHex("#FFFFFF"), FontColor=Color.FromHex("#FFFFFF"), Text = "Month"          
        };
    }
}

{% endhighlight %}

{% tabs %}

{% highlight xaml %}

<ContentPage.BindingContext>
    <local:ViewModel/>
</ContentPage.BindingContext>
<buttons:SfSegmentedControl 
    x:Name="segmentedControl" 
    Margin="10,0"
    CornerRadius="15"
    SelectedIndex="1"
    SelectedIndex="1"
    ItemsSource = "{Binding ImageTextCollection}"
    DisplayMode="ImageWithText"
    VisibleSegmentsCount="3"
    FontIconFontFamily = "segment.ttf"
</buttons:SfSegmentedControl>

{% endhighlight %}

{% highlight c# %}

public partial class SegmentedControlSample : ContentPage
{
    private ViewModel viewModel = new ViewModel();
    private SfSegmentedControl segmentedControl;

    public SegmentedControlSample()
    {
        segmentedControl = new SfSegmentedControl();
        segmentedControl.ItemsSource = viewModel.ImageTextCollection;
        segmentedControl.DisplayMode = SegmentDisplayMode.ImageWithText;
        segmentedControl.SelectedIndex = 1;
        segmentedControl.VisibleSegmentsCount = 3;
        segmentedControl.SelectionTextColor = Color.FromHex("#FFFFFF");
        segmentedControl.FontIconFontFamily = "segment.ttf";
        this.Content = segmentedControl;
        this.BindingContext= viewModel();
    }
}

{% endhighlight %}

{% endtabs %}

![Display Mode as ImageWithText in segmented control](images/Display-mode/Xamarin_Forms_ImagewithText.png)

## How to Set Font Icons Using a ttf File?

Refer to this [link](https://help.syncfusion.com/metro-studio/export-icon-font) for guidance on acquiring font icons. Follow the platform-specific steps to add the font file to your application:

**Adding Font File for iOS**

1. Add the font family inside the `Resource` folder of the iOS project.
2. Add the font file with the build action: `BundleResource`.
3. Update the `Info.plist` file by adding the fonts provided by the application under `UIAppFonts` or a similar key.

**Adding Font File for Android**

Add the font file to the `Assets` folder in the application project, and configure the build action as `AndroidAsset`.

**Adding Font File for UWP**

Add the font family inside the UWP application project.

N> For iOS alone, FontFamily property is declared without succeeding with .ttf and for android and UWP platform font family name is defined followed by .ttf.

{% tabs %}

{% highlight xaml %}

 FontIconFontFamily = "segment"

{% endhighlight %}

{% highlight c# %}

segmentedControl.FontIconFontFamily = "segment";

{% endhighlight %}

{% endtabs %}
