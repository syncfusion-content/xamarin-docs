---
layout: post
title: Features in Syncfusion EffectsView
description: Different effects available in EffectsView
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Effects

The [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) control provides support to ripple effect, highlight effect, and more. This section explains about different effects available in the effects view control.

## Highlight

`SfEffects.Highlight` is a smooth transition on the background color of the [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html).

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView
    HighlightColor="#FF0000"
    TouchDownEffects="Highlight">
    ...
    
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    HighlightColor = Color.FromHex("#FF0000"),
    TouchDownEffects = SfEffects.Highlight,
};

{% endhighlight %}

{% endtabs %}

![Highlight effect](Effects_images/Highlight.gif)

## Ripple

The `SfEffects.Ripple` is a growable circle, which is initially placed on the tapped location, and it grows till the whole layout is filled. `SfEffects.Ripple` is rendered based on [`InitialRippleFactor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~InitialRippleFactor.html).

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView TouchDownEffects="Ripple">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView()
{
    TouchDownEffects = SfEffects.Ripple,
};

{% endhighlight %}

{% endtabs %}

![Ripple effect](Effects_images/Ripple.png)

## Scale

`SfEffects.Scale` is a smooth transition from actual size of the object to the size calculated based on [`ScaleFactor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~ScaleFactor.html) in pixels.

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView
    ScaleFactor="0.85"
    TouchDownEffects="None"
    TouchUpEffects="None"
    LongPressEffects="Scale">
    ...
</sync:SfEffectsView>

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

![Scale effect](Effects_images/Scale.gif)

## Selection

`SfEffects.Selection` is a smooth color transition to indicate the view state is moved to selected state.

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView
    LongPressEffects="Selection"
    SelectionColor="#FF0000">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    SelectionColor = Color.FromHex("#FF0000"),
    LongPressEffects = SfEffects.Selection
};

{% endhighlight %}

{% endtabs %}

![Selection effect](Effects_images/SelectionEffect.gif)

## Rotation

`SfEffects.Rotation` provides a circular movement to the [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) around the center of the [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) based on the specified [`Angle`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~Angle.html). 

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView
    Angle="180"
    TouchDownEffects="Rotation">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    Angle = 180,
    TouchDownEffects = SfEffects.Rotation
};

{% endhighlight %}

{% endtabs %}

## Combinations

The [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) control provides support to apply multiple [`SfEffects`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffects.html) in combination. The following are some valid combinations of [`SfEffects`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffects.html):

### Highlight and Ripple

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView TouchDownEffects="Highlight,Ripple">
    ...
</sync:SfEffectsView>

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

<sync:SfEffectsView
    LongPressEffects="Selection"
    TouchDownEffects="Highlight">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView()
{
    TouchDownEffects = SfEffects.Highlight,
    LongPressEffects = SfEffects.Selection
};

{% endhighlight %}

{% endtabs %}

### Ripple and Selection

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView
    TouchDownEffects="Ripple"
    TouchUpEffects="Selection">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView()
{
    TouchDownEffects = SfEffects.Ripple,
    TouchUpEffects = SfEffects.Selection
};

{% endhighlight %}

{% endtabs %}

### Highlight, Ripple and Selection

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView
    LongPressEffects="Selection"
    TouchDownEffects="Highlight,Ripple">
    ...
</sync:SfEffectsView>

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

            <sfEffectsView:SfEffectsView LongPressEffects="Scale,Selection">
                <Label Text="Sign up" FontAttributes="Bold" FontSize="18" HeightRequest="50" HorizontalTextAlignment="Center"  VerticalTextAlignment="Center" />
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView()
            {
                LongPressEffects = SfEffects.Scale | SfEffects.Selection,
                Content = new Label()
                {
                    Text = "Sign up",
                    HeightRequest = 50,
                    FontAttributes = FontAttributes.Bold,
                    FontSize = 18,
                    HorizontalTextAlignment = TextAlignment.Center,
                    VerticalTextAlignment = TextAlignment.Center,
                }
            };
            this.Content = effectsView;

{% endhighlight %}

{% endtabs %}
