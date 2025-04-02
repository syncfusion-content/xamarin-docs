---

layout: post
title: Appearance Customization in Xamarin Rating control | Syncfusion
description: Learn here all about Appearance Customization support in Syncfusion Xamarin Rating (SfRating) control and more.
platform: Xamarin
control: Rating
documentation: ug

---

# Appearance Customization in Xamarin Rating (SfRating)

We can customize the rated and unrated items Color, Stroke width and Stroke color using the following properties of [`SfRatingSettings`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingSettings.html).

* [`RatedFill`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingSettings.html#Syncfusion_SfRating_XForms_SfRatingSettings_RatedFill)
* [`UnRatedFill`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingSettings.html#Syncfusion_SfRating_XForms_SfRatingSettings_UnRatedFill)
* [`RatedStroke`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingSettings.html#Syncfusion_SfRating_XForms_SfRatingSettings_RatedStroke)
* [`UnRatedStroke`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingSettings.html#Syncfusion_SfRating_XForms_SfRatingSettings_UnRatedStroke)
* [`RatedStrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingSettings.html#Syncfusion_SfRating_XForms_SfRatingSettings_RatedStrokeWidth)
* [`UnRatedStrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingSettings.html#Syncfusion_SfRating_XForms_SfRatingSettings_UnRatedStrokeWidth)
 
## Set Fill Color

[`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control has support to set the fill color for the selected and unselected items.

### Selected Items

The [`RatedFill`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingSettings.html#Syncfusion_SfRating_XForms_SfRatingSettings_RatedFill) property fills the rated item with the specified solid color in the [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control.

{% tabs %}

{% highlight xaml %}

    <rating:SfRating Value="3">
    <rating:SfRating.RatingSettings>
    <rating:SfRatingSettings RatedFill="Red"/>
    </rating:SfRating.RatingSettings>
    </rating:SfRating>
	
{% endhighlight %}

{% highlight C# %}

    SfRating rating= new SfRating();
    rating.Value = 3;
    SfRatingSettings ratingSettings = new SfRatingSettings();
    ratingSettings.RatedFill = Color.Red;
    rating.RatingSettings = ratingSettings;
           
{% endhighlight %}

{% endtabs %}

![Rated item fill color](images/ratedFill.jpg)

### Unselected Items

The [`UnRatedFill`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingSettings.html#Syncfusion_SfRating_XForms_SfRatingSettings_UnRatedFill) property fills the unrated item with the specified solid color in the [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control.

{% tabs %}

{% highlight xaml %}

    <rating:SfRating Value="3">
    <rating:SfRating.RatingSettings>
    <rating:SfRatingSettings UnRatedFill="Gray"/>
    </rating:SfRating.RatingSettings>
    </rating:SfRating>

{% endhighlight %}

{% highlight C# %}

    SfRating rating= new SfRating();
    rating.Value = 3;
    SfRatingSettings ratingSettings = new SfRatingSettings();
    ratingSettings.UnRatedFill = Color.Gray;
    rating.RatingSettings = ratingSettings;

{% endhighlight %}

{% endtabs %}

![Unrated item fill color](images/unRatedFill.jpg)

## Set Stroke Color

[`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control has support to set the stroke color for the selected and unselected items.

### Selected Items

The [`RatedStroke`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingSettings.html#Syncfusion_SfRating_XForms_SfRatingSettings_RatedStroke) property sets the stroke for the rated item with the specified solid color for the selected items in the [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control.

{% tabs %}

{% highlight xaml %}

    <rating:SfRating Value="3">
    <rating:SfRating.RatingSettings>
    <rating:SfRatingSettings RatedStroke="Black"/>
    </rating:SfRating.RatingSettings>
    </rating:SfRating>
	
{% endhighlight %}

{% highlight C# %}

    SfRating rating= new SfRating();
    rating.Value = 3;
    SfRatingSettings ratingSettings = new SfRatingSettings();
    ratingSettings.RatedStroke=Color.Black;
    rating.RatingSettings = ratingSettings;	

{% endhighlight %}

{% endtabs %}

![Rated item stroke color](images/ratedStroke.jpg)

### Unselected Items

The [`UnRatedStroke`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingSettings.html#Syncfusion_SfRating_XForms_SfRatingSettings_UnRatedStroke) property sets the stroke for the unrated area with the specified solid color in the [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control.

{% tabs %}

{% highlight xaml %}

    <rating:SfRating Value="3">
    <rating:SfRating.RatingSettings>
    <rating:SfRatingSettings UnRatedStroke="Black"/>
    </rating:SfRating.RatingSettings>
    </rating:SfRating>

{% endhighlight %}

{% highlight C# %}

    SfRating rating= new SfRating();
    rating.Value = 3;
    SfRatingSettings ratingSettings = new SfRatingSettings();
    ratingSettings.UnRatedStroke = Color.Black;
    rating.RatingSettings = ratingSettings;

{% endhighlight %}

{% endtabs %}

![Unrated item stroke color](images/unRatedStroke.jpg)
 
## Set Stroke Width

[`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control has support to set the stroke width for the selected and unselected items.

### Selected Items

The [`RatedStrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingSettings.html#Syncfusion_SfRating_XForms_SfRatingSettings_RatedStrokeWidth) property sets the stroke width for the rated item with the specified value in the [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control.

{% tabs %}

{% highlight xaml %}

    <rating:SfRating Value="3">
    <rating:SfRating.RatingSettings>
    <rating:SfRatingSettings RatedStrokeWidth="3"/>
    </rating:SfRating.RatingSettings>
    </rating:SfRating>

{% endhighlight %}

{% highlight C# %}

    SfRating rating= new SfRating();
    rating.Value = 3;
    SfRatingSettings ratingSettings = new SfRatingSettings();
    ratingSettings.RatedStrokeWidth=3;
    rating.RatingSettings = ratingSettings;

{% endhighlight %}

{% endtabs %}

![Rated item stroke width](images/ratedStrokeThickness.jpg)

### Unselected Items

The [`UnRatedStrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingSettings.html#Syncfusion_SfRating_XForms_SfRatingSettings_UnRatedStrokeWidth) property sets the stroke width for the unrated item with the specified value in the [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control.

{% tabs %}

{% highlight xaml %}

    <rating:SfRating Value="3">
    <rating:SfRating.RatingSettings>
    <rating:SfRatingSettings UnRatedStrokeWidth="3"/>
    </rating:SfRating.RatingSettings>
    </rating:SfRating>
	
{% endhighlight %}

{% highlight C# %}

    SfRating rating= new SfRating();
    rating.Value = 3;
    SfRatingSettings ratingSettings = new SfRatingSettings();
    ratingSettings.UnRatedStrokeWidth=3;
    rating.RatingSettings = ratingSettings;

{% endhighlight %}

{% endtabs %}

![Unrated item stroke width](images/unRatedStrokeThickness.jpg)
