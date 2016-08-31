---
layout: post
title: Linear Tick Settings in LinearGauge
description: Learn how to define settings of linear ticks in LinearGauge
platform: Xamarin
control: LinearGauge
documentation: ug
---

# Settings Ticks 

Ticks are categorized into two type as major and minor. These ticks are arranged with respect to the specified frequency i.e., Interval of the linear scale. The minor ticks are displayed using the `MinorTicksPerInterval` property.

{% tabs %}

{% highlight xaml %}

<linear:SfLinearGauge.Scales>
	<linear:LinearScale x:Name="scale" MinimumValue="0" MaximumValue="100" Interval="20" ScaleBarLength="100" ScaleBarColor="#FAECEC" MinorTicksPerInterval="1" ScaleBarSize="13" ScalePosition="BackWard" >
		<linear:LinearScale.MajorTickSettings>
			<linear:LinearTickSettings x:Name="major" Length="10" Thickness="1" Color="Red" />
		</linear:LinearScale.MajorTickSettings>
		<linear:LinearScale.MinorTickSettings>
			<linear:LinearTickSettings x:Name="minor" Length="5" Thickness="1" Color="Yellow" />
		</linear:LinearScale.MinorTickSettings>
	</linear:LinearScale>
</linear:SfLinearGauge.Scales>
	
{% endhighlight %}

{% highlight C# %}
ObservableCollection<LinearScale> scales = new ObservableCollection<LinearScale>();
LinearScale scale = new LinearScale();
LinearTickSettings minor = new LinearTickSettings ();
minor.Length = 5;
minor.Color = Color.FromRgb (152, 152, 0);
minor.Thickness = 1;
scale.MinorTickSettings = minor;
	
//Major Ticks setting
LinearTickSettings major = new LinearTickSettings ();
major.Length = 10;
major.Color = Color.FromRgb (229, 0, 0);
major.Thickness = 1;
scale.MajorTickSettings = major; 
    
scales.Add(scale);
linearGauge.Scales = (scales);
	
{% endhighlight %}

{% endtabs %}


![](images/LinearTickSettings.png)

