---

layout: post
title: Enable View Range Selection in Xamarin Rating Control | Syncfusion
description: Learn how to utilize View Range Selection with CustomView in the Syncfusion Xamarin Rating (SfRating) control.
platform: Xamarin
control: Rating
documentation: ug

---

# Enable View Range Selection in Xamarin Rating (SfRating)

When using the `CustomView` in the [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control, only a single item is rated by default. To change the view of all rated `CustomView` items, employ the boolean property [`EnableViewRangeSelection`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_EnableViewRangeSelection).

> Note: The `EnableViewRangeSelection` property is applicable only when using `CustomViews`.

## Example Usage

Below are examples demonstrating how to set the `EnableViewRangeSelection` property:
{% tabs %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" EnableCustomView="True" ItemCount="5" EnableViewRangeSelection="True" />
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainPage()
{
    InitializeComponent();
    -------

    rating.EnableCustomView = true;
    rating.EnableViewRangeSelection = true;
    
    -------
}

{% endhighlight %}

{% endtabs %}

![EnableViewRangeSelection in SfRating](images/enableviewrangeselection.png)
