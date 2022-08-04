---

layout: post
title: Restrict user Selection  in Xamarin Rating control | Syncfusion
description: Learn here all about Restrict user Selection  support in Syncfusion Xamarin Rating (SfRating) control and more.
platform: Xamarin
control: Rating
documentation: ug

---

# Restrict user Selection  in Xamarin Rating (SfRating)

[`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control provides support for changeable or unchangeable values for Rating control. This is achieved by the [`ReadOnly`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_ReadOnly) property. When this property is set to True, the Rating value becomes unchangeable. By default, this property value is set to False.

{% tabs %}

{% highlight C# %}

	rating.ReadOnly=true;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" ReadOnly="true" />
	
{% endhighlight %}

{% endtabs %}

![readOnly](images/readOnly.jpg)


