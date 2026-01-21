---

layout: post
title: Restrict User Selection in Xamarin Rating Control | Syncfusion
description: Learn how to restrict user selection in the Syncfusion Xamarin Rating (SfRating) control using the ReadOnly property.
platform: Xamarin
control: Rating
documentation: ug

---

# Restrict User Selection in Xamarin Rating (SfRating)

The [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control allows for either changeable or unchangeable rating values. This behavior is controlled by the [`ReadOnly`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_ReadOnly) property. Setting this property to `True` makes the rating value static, preventing user modifications. By default, this property is set to `False`, allowing user input.

{% tabs %}

{% highlight C# %}

	rating.ReadOnly=true;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" ReadOnly="true" />
	
{% endhighlight %}

{% endtabs %}

![ReadOnly Property in Action](images/readOnly.jpg)
