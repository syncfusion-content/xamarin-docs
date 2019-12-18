---
layout: post
title: Syncfusion.Xamarin.Forms Shimmer types
description: Different built-in Shimmer types and custom view support available in Essential Xamarin.Forms Shimmer.
platform: xamarin
control: SfShimmer
documentation: ug
---

# Shimmer Types

## Built-in types

The following different built-in shimmer types are available in Shimmer:

* `Persona`
* `Profile`
* `Article`
* `Video`
* `Feed`
* `Shopping`

You can use the built-in shimmer types by setting the [`Type`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.Shimmer.SfShimmer~Type.html) of [`SfShimmer`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.Shimmer.SfShimmer.html).

{% tabs %} 

{% highlight xaml %} 

        <shimmer:SfShimmer x:Name="shimmer" VerticalOptions="FillAndExpand" Type="Profile">
                <shimmer:SfShimmer.Content>
                     <StackLayout>
                        <Label Text="Content is loaded!" HorizontalOptions="CenterAndExpand" VerticalOptions="CenterAndExpand"/>
                      </StackLayout>
                </shimmer:SfShimmer.Content>
        </shimmer:SfShimmer>

{% endhighlight %}

{% highlight C# %} 

            shimmer = new SfShimmer()
            {
                Type = ShimmerTypes.Profile,
                VerticalOptions = LayoutOptions.FillAndExpand,
                Content = new Label
                {
                    Text = "Content is loaded!"
                }
            };
            this.Content = shimmer;

{% endhighlight %}

{% endtabs %}

![The built-in shimmer types for Xamarin.Forms](Shimmer-Types_images/ShimmerTypes.gif)

