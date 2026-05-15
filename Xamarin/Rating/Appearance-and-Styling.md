---

layout: post
title: Appearance and Styling in Xamarin Rating Control | Syncfusion
description: Learn how to customize the appearance and styling in the Syncfusion Xamarin Rating (SfRating) control, including item size, count, and spacing.
platform: Xamarin
control: Rating
documentation: ug

---

# Appearance and Styling in Xamarin Rating (SfRating)

If the default view does not meet your needs, you can customize the `SfRating` control in Xamarin.Forms. This control allows you to modify the size, item count, and spacing between rating items to better fit your application design requirements.
## Set Size

Use the [`ItemSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_ItemSize) property to define the size of the rating items.

> Note: The default value for this property is 50.
{% tabs %}

{% highlight xaml %}

	<rating:SfRating ItemSize="20" />
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainPage()
{
    InitializeComponent();
    rating = new SfRating();
    rating.ItemSize = 20;
}

{% endhighlight %}

{% endtabs %}

![SfRating layout customization](images/layoutSize.jpg)

## Set Number of Items

The [`ItemCount`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_ItemCount) property sets the number of rating items to be displayed. 

N> The default property value is 5.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating ItemCount="4" />
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainPage()
{
    InitializeComponent();
    rating = new SfRating();
    rating.ItemCount = 4;
}

{% endhighlight %}

{% endtabs %}

![Set number of rating items](images/fourstar.jpg)
 
## Set Space between Items

The [`ItemSpacing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_ItemSpacing) property sets the spacing between the rating items. 

N> By default, property value is 5.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating ItemSpacing="20" />
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainPage()
{
    InitializeComponent();
    rating = new SfRating();
    rating.ItemSpacing = 20;
}

{% endhighlight %}

{% endtabs %}

![Space between rating items](images/layoutSpace.jpg) 

## Rating Settings

This section explains about various rating settings available in the [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control.

{% tabs %}

{% highlight xaml %}

     <rating:SfRating  Value="3">
        <rating:SfRating.RatingSettings>
            <rating:SfRatingSettings RatedFill="Red" UnRatedFill="Blue" RatedStrokeWidth="3" UnRatedStrokeWidth="2" />
        </rating:SfRating.RatingSettings>
     </rating:SfRating>

{% endhighlight %}

{% highlight c# %}

SfRating rating;
SfRatingSettings ratingSettings;
public MainPage()
{
    InitializeComponent();
    rating = new SfRating();
    ratingSettings = new SfRatingSettings();
    ratingSettings.RatedFill = Color.Red;
    ratingSettings.UnRatedFill = Color.Blue;
    ratingSettings.RatedStrokeWidth = 3;
    ratingSettings.UnRatedStrokeWidth = 2;
    rating.RatingSettings = ratingSettings;
}

{% endhighlight %}

{% endtabs %}
