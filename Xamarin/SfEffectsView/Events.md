---
layout: post
title: Events in Syncfusion EffectsView
description: How to hook the event in Syncfusion EffectsView
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Events

## AnimationCompleted event

The [`AnimationCompleted`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~AnimationCompleted_EV.html) event occurs when the effects completed. When the effects rendered on direct interaction, this event will trigger on touch up and when applied programmatically, it will trigger immediately on its completion.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView AnimationCompleted="AnimationCompleted">
    ...
</syncEffectsView:SfEffectsView>
  
{% endhighlight %}

{% highlight C# %} 

public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        var effectsView = new SfEffectsView();
        effectsView.AnimationCompleted += AnimationCompleted;
    }

    private void AnimationCompleted(object sender, EventArgs e)
    {
        ...
    }
}

{% endhighlight %}

{% endtabs %}

N> The [`AnimationCompleted`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~AnimationCompleted_EV.html) event is not applicable for `SfEffects.Selection`.

## SelectionChanged event

The [`SelectionChanged`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~SelectionChanged_EV.html) event occurs when the [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) is selected or unselected.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView LongPressEffects="Selection" SelectionChanged="SelectionChanged">
    ...
</syncEffectsView:SfEffectsView>
  
{% endhighlight %}

{% highlight C# %} 

public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        var effectsView = new SfEffectsView();
        effectsView.LongPressEffects = SfEffects.Selection;
        effectsView.SelectionChanged += EffectsView_SelectionChanged;
    }

    private void SelectionChanged(object sender, EventArgs e)
    {
        ...
    }
}

{% endhighlight %}

{% endtabs %}
