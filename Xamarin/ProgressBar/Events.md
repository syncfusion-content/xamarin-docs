---
layout: post
title: Events
platform: xamarin
control: ProgressBar
documentation: ug
---

# Events

## ValueChanged

This event is triggered when the progress value is changed. This event contains the following event argument.

* [`Progress`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.ProgressValueEventArgs.html#Syncfusion_XForms_ProgressBar_ProgressValueEventArgs_Progress): Represents the progress value.

The following code sample demonstrates how to customize the color of a progress indicator based on progress using this event. 

{% tabs %} 

{% highlight xaml %}

<progressBar:SfLinearProgressBar Progress="100" x:Name="LinearProgressBar" ValueChanged="ProgressBarBase_OnValueChanged">

</progressBar:SfLinearProgressBar>

{% endhighlight %}

{% highlight c# %}
private void ProgressBarBase_OnValueChanged(object sender, ProgressValueEventArgs e)
{   
    if (e.Progress < 50)
    {
        this.LinearProgressBar.ProgressColor = Color.Red;
    }
    else if (e.Progress >= 50)
    {
        this.LinearProgressBar.ProgressColor = Color.Green; 
    }
}

{% endhighlight %}

{% endtabs %} 

## ProgressCompleted

This event is triggered when the progress attains the [`Maximum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.ProgressBarBase.html#Syncfusion_XForms_ProgressBar_ProgressBarBase_Maximum) value. This event contains the following argument.

* [`Progress`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.ProgressValueEventArgs.html#Syncfusion_XForms_ProgressBar_ProgressValueEventArgs_Progress): Represents the progress value.

The following code sample demonstrates how to customize the progress bar when progress reaches maximum using this event. 

{% tabs %} 

{% highlight xaml %}

<progressBar:SfCircularProgressBar x:Name="CircularProgressBar" Minimum="100" Maximum="500" Progress="500" ProgressCompleted="ProgressBarBase_OnProgressCompleted" >

    <progressBar:SfCircularProgressBar.Content>

        <Label Text="Start" FontSize="15" x:Name="Label"></Label>

    </progressBar:SfCircularProgressBar.Content>

</progressBar:SfCircularProgressBar>

{% endhighlight %}

{% highlight c# %}

private void ProgressBarBase_OnProgressCompleted(object sender, ProgressValueEventArgs e)
{
    if (e.Progress.Equals(this.CircularProgressBar.Maximum))
    {
        // Changed the label text when progress reaches maximum value.
        this.Label.Text = "Completed";  
    }
}
{% endhighlight %}

{% endtabs %} 