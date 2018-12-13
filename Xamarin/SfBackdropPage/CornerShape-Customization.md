---
layout: post
title: Corner shape customization of Syncfusion Backdrop Page
description: How to customize a corner shape
platform: xamarin
control: SfBackdropPage
documentation: ug
---

# Corner Shape Customization

Essential Backdrop Page supports corner shape customization that are illustrated as follows.

## Adjust the shape of front layer

The SfBackdropPage allows to adjust the edge shape of the front layer which can be adjusted using the EdgeShape property.

### Display edge shape as curve
The EdgeShape property of the SfBackdropPage allows the user to set the curve shape to the edge of the front layer.

{% tabs %} 

{% highlight xaml %} 

<backdrop:SfBackdropPage.FrontLayer>
        <backdrop:BackdropFrontLayer EdgeShape="Curve">
            <Grid />
        </backdrop:BackdropFrontLayer>
</backdrop:SfBackdropPage.FrontLayer> 


{% endhighlight %}

{% highlight C# %} 

this.FrontLayer = new BackdropFrontLayer()
            {
                Content = new Grid
                {
				
                },
				EdgeShape = EdgeShape.Curve
            };

{% endhighlight %}

{% endtabs %}

### Display edge shape as flat

The EdgeShape property of the SfBackdropPage allows the user to set the flat shape to the edge of the front layer.

{% tabs %} 

{% highlight xaml %} 

<backdrop:SfBackdropPage.FrontLayer>
        <backdrop:BackdropFrontLayer EdgeShape="Flat">
            <Grid />
        </backdrop:BackdropFrontLayer>
</backdrop:SfBackdropPage.FrontLayer> 


{% endhighlight %}

{% highlight C# %} 

this.FrontLayer = new BackdropFrontLayer()
            {
                Content = new Grid
                {
				
                },
				EdgeShape = EdgeShape.Flat
            };

{% endhighlight %}

{% endtabs %}


## Set corner radius of front layer

The SfBackdropPage allows to set the corner radius for the front layer. 

### Customize rIght corner radius of front layer

The right corner radius of the front layer in the SfBackdropPage can be set by using the RightCornerRadius property.

{% tabs %} 

{% highlight xaml %} 

<backdrop:SfBackdropPage.FrontLayer>
        <backdrop:BackdropFrontLayer RightCornerRadius="30">
            <Grid />
        </backdrop:BackdropFrontLayer>
</backdrop:SfBackdropPage.FrontLayer> 


{% endhighlight %}

{% highlight C# %} 

this.FrontLayer = new BackdropFrontLayer()
            {
                Content = new Grid
                {
				
                },
				RightCornerRadius = 30
            };

{% endhighlight %}

{% endtabs %}

### Customize left corner radius of front layer

The left corner radius of the front layer in the SfBackdropPage can be set by using the LeftCornerRadius property.

{% tabs %} 

{% highlight xaml %} 

<backdrop:SfBackdropPage.FrontLayer>
        <backdrop:BackdropFrontLayer LeftCornerRadius="30">
            <Grid />
        </backdrop:BackdropFrontLayer>
</backdrop:SfBackdropPage.FrontLayer> 


{% endhighlight %}

{% highlight C# %} 

this.FrontLayer = new BackdropFrontLayer()
            {
                Content = new Grid
                {
				
                },
				LeftCornerRadius = 30
            };

{% endhighlight %}

{% endtabs %}
