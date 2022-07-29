---

layout: post
title: Enable View Range Selection in Xamarin Rating control | Syncfusion
description: Learn here all about Enable View Range Selection support in Syncfusion Xamarin Rating (SfRating) control and more.
platform: Xamarin
control: Rating
documentation: ug

---

# Enable View Range Selection in Xamarin Rating (SfRating)

When using CustomView in SfRating, Only one item will be rated. If you need to change the view of all rated CustomView items, Use the [`EnableViewRangeSelection`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_EnableViewRangeSelection) boolean property.

N> The EnableViewRangeSelection property is used only for CustomViews. 

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

![SfRating EnableViewRangeSelection](images/enableviewrangeselection.png)
