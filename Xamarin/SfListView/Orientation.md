---
layout: post
title: Orientation | SfListView | Xamarin | Syncfusion
description: Orientation with SfListView
platform: xamarin
control: SfListView
documentation: ug
---

# Orientation

[SfListView](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView.html) allows you to layout every item in the [SfListView.ItemsSource](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemsSource.html) property in either vertical or horizontal orientation by setting [SfListView.Orientation](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~Orientation.html). The default orientation is vertical.

{% tabs %}
{% highlight xaml %}
<xmlns:sync="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">

<sync:SfListView x:Name="listView" Orientation="Horizontal" />
{% endhighlight %}
{% highlight c# %}
listView.Orientation = Orientation.Horizontal;
{% endhighlight %}
{% endtabs %}
