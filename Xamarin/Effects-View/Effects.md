---
layout: post
title: Effects in Xamarin Effects View control | Syncfusion®
description: Learn here all about Effects support in Syncfusion® Xamarin Effects View (SfEffectsView) control and more.
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Effects in Xamarin Effects View (SfEffectsView)

The [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) control provides modern effects such as highlight, ripple, selection, scaling, and rotation. This section explains about these effects.

## Highlight

`SfEffects.Highlight` is a smooth transition on the background color of [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html).

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

The `SfEffects.Ripple` is a growable circle, which is initially placed on the tapped location, and it grows till the whole layout is filled. `SfEffects.Ripple` is rendered based on [`InitialRippleFactor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_InitialRippleFactor).

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

`SfEffects.Scale` is a smooth transition on the size of the [`SfEffectsView.Content`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) from actual size to the size calculated based on [`ScaleFactor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_ScaleFactor) in pixels.

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

`SfEffects.Selection` is a smooth color transition to indicate whether the [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) state is selected or not.

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

`SfEffects.Rotation` provides a circular movement to [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) around the center of the [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) based on the specified [`Angle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_Angle).

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

The [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) control provides support to apply multiple [`SfEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffects.html) in combination. The following are some valid combinations of [`SfEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffects.html):

### Highlight and ripple

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

### Highlight and selection

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

### Ripple and selection

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

### Highlight, ripple and selection

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

### Scale and selection

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
