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

The [`AnimationCompleted`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~AnimationCompleted_EV.html) event occurs when the ripple effect is completed. 

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

## SelectionChanged event

The [`SelectionChanged`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~SelectionChanged_EV.html) event occurs when this view selected.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView SelectionChanged="SelectionChanged">
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
        effectsView.SelectionChanged += SelectionChanged;
    }

    private void SelectionChanged(object sender, EventArgs e)
    {
        ...
    }
}

{% endhighlight %}

{% endtabs %}
