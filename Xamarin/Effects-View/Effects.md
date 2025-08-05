---
layout: post
title: Effects in Xamarin Effects View Control | Syncfusion
description: Explore the various effects supported by the Syncfusion Xamarin Effects View (SfEffectsView) control, including highlight, ripple, selection, scaling, and rotation.
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Effects in Xamarin Effects View (SfEffectsView)

The [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) control offers modern visual effects such as highlight, ripple, selection, scaling, and rotation. This section provides an overview of these effects.

## Highlight

`SfEffects.Highlight` applies a smooth transition to the background color of the [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html).

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    TouchDownEffects="Highlight"
    HighlightColor="#FF0000">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    TouchDownEffects = SfEffects.Highlight,
    HighlightColor = Color.FromHex("#FF0000")
};

{% endhighlight %}

{% endtabs %}

![Highlight effect](Effects_images/EffectsView_Highlight.png)

## Ripple

The `SfEffects.Ripple` effect creates a growing circle, starting from the tapped location and expanding to fill the entire layout. This effect is rendered based on the [`InitialRippleFactor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_InitialRippleFactor).

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView TouchDownEffects="Ripple">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView()
{
    TouchDownEffects = SfEffects.Ripple,
};

{% endhighlight %}

{% endtabs %}

![Ripple effect](Effects_images/EffectsView_Ripple.gif)

## Scale

`SfEffects.Scale` provides a smooth transition, changing the size of the [`SfEffectsView.Content`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) from its actual size to a size determined by the [`ScaleFactor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_EffectsView_SfEffectsView_ScaleFactor).

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    ScaleFactor="0.85"
    TouchDownEffects="None"
    TouchUpEffects="None"
    LongPressEffects="Scale">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    ScaleFactor = 0.85,
    TouchDownEffects = SfEffects.None,
    TouchUpEffects = SfEffects.None,
    LongPressEffects = SfEffects.Scale
};

{% endhighlight %}

{% endtabs %}

![Scale effect](Effects_images/EffectsView_Scale.png)

## Selection

`SfEffects.Selection` provides a smooth color transition to indicate whether the [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) is selected.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    LongPressEffects="Selection"
    SelectionColor="#FF0000">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    LongPressEffects = SfEffects.Selection,
    SelectionColor = Color.FromHex("#FF0000")
};

{% endhighlight %}

{% endtabs %}

![Selection effect](Effects_images/EffectsView_Selection.png)

## Rotation

`SfEffects.Rotation` applies a circular movement to the [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html), rotating around its center based on the specified [`Angle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_Angle).

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    TouchDownEffects="Rotation"
    Angle="180">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    TouchDownEffects = SfEffects.Rotation,
    Angle = 180,
};

{% endhighlight %}

{% endtabs %}

## Combinations

The [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) control allows the application of multiple [`SfEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffects.html) in combination. Here are some valid combinations of `SfEffects`:

### Highlight and Ripple

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView TouchDownEffects="Highlight,Ripple">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView()
{
    TouchDownEffects = SfEffects.Highlight | SfEffects.Ripple
};

{% endhighlight %}

{% endtabs %}

### Highlight and Selection

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    LongPressEffects="Selection"
    TouchDownEffects="Highlight">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView()
{
    LongPressEffects = SfEffects.Selection,
    TouchDownEffects = SfEffects.Highlight
};

{% endhighlight %}

{% endtabs %}

### Ripple and Selection

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    TouchDownEffects="Ripple"
    TouchUpEffects="Selection">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView()
{
    TouchDownEffects = SfEffects.Ripple,
    TouchUpEffects = SfEffects.Selection
};

{% endhighlight %}

{% endtabs %}

### Highlight, Ripple, and Selection

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    LongPressEffects="Selection"
    TouchDownEffects="Highlight,Ripple">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView()
{
    LongPressEffects = SfEffects.Selection,
    TouchDownEffects = SfEffects.Highlight | SfEffects.Ripple,
};

{% endhighlight %}

{% endtabs %}

### Scale and Selection

{% tabs %} 

{% highlight xaml %} 

 <syncEffectsView:SfEffectsView LongPressEffects="Scale,Selection">
     ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView()
{
    LongPressEffects = SfEffects.Scale | SfEffects.Selection
};

{% endhighlight %}

{% endtabs %}
