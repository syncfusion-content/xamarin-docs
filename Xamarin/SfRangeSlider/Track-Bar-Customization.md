---
layout: post
title: TrackBar Customization of Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to customize the TrackBar appearance for RangeSlider control in Xamarin.Forms
platform: Xamarin
control: RangeSlider
documentation: ug
---
# TrackBar Customization 

### Customizing track height

The thickness of track bar can be customized by setting the TrackThickness property of SfRangeSlider. 

{% tabs %}
{% highlight xaml %}`

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TrackCustomization" 
             xmlns:slider="clr-namespace:Syncfusion.SfRangeSlider.XForms;assembly=Syncfusion.SfRangeSlider.XForms"
             x:Class="TrackCustomization.MainPage">
             <ContentPage.Content>
               <slider:SfRangeSlider Orientation="Horizontal"
                                    TrackThickness="10"
                                    RangeStart="0"
                                    RangeEnd="2"/>
             </ContentPage.Content>
</ContentPage>
	
{% endhighlight %}

{% highlight c# %}


using Syncfusion.SfRangeSlider.XForms; 
using Xamarin.Forms;

namespace TrackCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRangeSlider slider = new SfRangeSlider();
            slider.Orientation = Orientation.Horizontal;
            slider.RangeStart = 0;
            slider.RangeEnd = 2;
            slider.TrackThickness = 10;
            Content = slider;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![](Track_Customization_Images/Track_Thickness.png)

### Customizing dragged area height

The thickness for a selected range or selected portion of track bar can be customized by setting the TrackSelectionThickness property of SfRangeSlider.

{% tabs %}

{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TrackCustomization" 
             xmlns:slider="clr-namespace:Syncfusion.SfRangeSlider.XForms;assembly=Syncfusion.SfRangeSlider.XForms"
             x:Class="TrackCustomization.MainPage">
    <ContentPage.Content>
      <slider:SfRangeSlider Orientation="Horizontal"
                            TrackSelectionThickness="10"
                            RangeStart="10"
                            RangeEnd="30"/>
      </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfRangeSlider.XForms;
using Xamarin.Forms;

namespace TrackCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRangeSlider slider = new SfRangeSlider();
            slider.Orientation = Orientation.Horizontal;
            slider.TrackSelectionThickness = 10;
            slider.RangeStart = 10;
            slider.RangeEnd = 30;
            Content = slider;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![](Track_Customization_Images/Track_SelectionThickness.png)

### Customizing track color

The color of track bar can be customized by setting the TrackColor property of SfRangeSlider.

{% tabs %}

{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TrackCustomization" 
             xmlns:slider="clr-namespace:Syncfusion.SfRangeSlider.XForms;assembly=Syncfusion.SfRangeSlider.XForms"
             x:Class="TrackCustomization.MainPage">
    <ContentPage.Content>
       <slider:SfRangeSlider Orientation="Horizontal"
                             TrackColor="Maroon"
                             RangeStart="10"
                             RangeEnd="40"/>
      </ContentPage.Content>
</ContentPage>
	
	
{% endhighlight %}

{% highlight c# %}
using Syncfusion.SfRangeSlider.XForms;
using Xamarin.Forms;

namespace TrackCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRangeSlider slider = new SfRangeSlider();
            slider.Orientation = Orientation.Horizontal;
            slider.TrackColor = Color.Maroon;
            slider.RangeStart = 10;
            slider.RangeEnd = 40;
            Content = slider;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![](Track_Customization_Images/Track_Color.png)

### Customizing dragged area color

The color for a selected range or selected portion of track bar can be customized by setting the TrackSelectionColor property of SfRangeSlider.

{% tabs %}

{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TrackCustomization" 
             xmlns:slider="clr-namespace:Syncfusion.SfRangeSlider.XForms;assembly=Syncfusion.SfRangeSlider.XForms"
             x:Class="TrackCustomization.MainPage">
    <ContentPage.Content>
      <slider:SfRangeSlider Orientation="Horizontal"
                          TrackSelectionColor="Red"
                          RangeStart="10"
                          RangeEnd="40"/>
      </ContentPage.Content>
</ContentPage>
	 
{% endhighlight %}

{% highlight c# %}
using Syncfusion.SfRangeSlider.XForms;
using Xamarin.Forms;

namespace TrackCustomization
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRangeSlider slider = new SfRangeSlider();
            slider.Orientation = Orientation.Horizontal;
            slider.TrackSelectionColor = Color.Red;
            slider.RangeStart = 10;
            slider.RangeEnd = 40;
            Content = slider;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![](Track_Customization_Images/Track_SelectionColor.png)



