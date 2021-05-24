---

layout: post
title: Restrict user Selection  in Xamarin Rating control | Syncfusion
description: Learn here all about Restrict user Selection  support in Syncfusion Xamarin Rating (SfRating) control and more.
platform: Xamarin
control: Rating
documentation: ug

---

# Restrict user Selection  in Xamarin Rating (SfRating)

SfRating control provides support for changeable or unchangeable values for Rating control. This is achieved by the `ReadOnly` property. When this property is set to True, the Rating value becomes unchangeable. By default, this property value is set to False.

{% tabs %}

{% highlight C# %}

	rating.ReadOnly=true;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" ReadOnly="true" />
	
{% endhighlight %}

{% endtabs %}

![readOnly](images/readOnly.jpg)


