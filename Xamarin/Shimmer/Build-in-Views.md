---
layout: post
title: Syncfusion.Xamarin.Forms Shimmer types
description: This section describes the different build-in Shimmer types available in Essential Xamarin.Forms Shimmer control.
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

You can use the built-in shimmer types by setting the [`Type`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Shimmer.SfShimmer.html#Syncfusion_XForms_Shimmer_SfShimmer_Type) of [`SfShimmer`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Shimmer.SfShimmer.html).

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

![The built-in shimmer types for Xamarin.Forms](Build-in-views_images/ShimmerTypes.gif)

