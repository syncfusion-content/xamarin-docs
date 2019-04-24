---
layout: post
title: Add custom labels to SfChart axis | Syncfusion
description: Add, remove or modify the labels of SfChart axis
platform: xamarin
control: Chart
documentation: ug
---

## Add custom labels to SfChart axis

In order to add a custom label, you need to write a class derived from NumericalAxis class. You need to override [`OnCreatedLabels`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~OnCreateLabels.html) method, which will be called whenever new labels are going to be generated, and add, remove or modify the labels using [`VisibleLabels`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~VisibleLabels.html) properties. The following code sample demonstrates this:

{% highlight c# %}

public class NumericalAxisExt : NumericalAxis
{
    protected override void OnCreateLabels()
    {
        base.OnCreateLabels();
		
		//Using VisibleLabels collection you can define your custom labels
        VisibleLabels.Clear();
        ViewModel viewModel = BindingContext as ViewModel;

        for (int i = 0; i < viewModel.Data.Count; i++)
        {
            var data = viewModel.Data[i];
            VisibleLabels.Add(new ChartAxisLabel(data.XValue, data.XValue.ToString()));
        }
    }
}

{% endhighlight  %}

![Custom labels support in Xamarin.Forms Chart](images/custom_labels.png)

N>
- Labels are rendered only if the label position is present within the visible range.
- The labels should be created only if the user calls the base of [`OnCreateLabels`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~OnCreateLabels.html).