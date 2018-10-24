---
layout: post
title: Localization of Xamarin.Forms Chart
description: How to localize the labels in Xamarin.Forms Chart.
platform: xamarin
control: Chart
documentation: ug
---

# Localization 


You can set localization for [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html) in all the platforms by adding a .resx file in a .NET Standard project alone. The following steps describe how to set localization for SfChart in a project and you can download the complete sample [`here`](https://github.com/SyncfusionExamples/how-to-localize-the-labels-in-xamarin-forms-sfchart).

N> Here, resources have been already created for some cultures and shared them on the [`Syncfusion GitHub`](https://github.com/syncfusion/xamarin-localized-texts) for your convenience.

1. Add a new folder in the .NET Standard project named Resources.

2. Add resource files for the languages you wish to support and set their Build Action to EmbeddedResource. The name of the resource file should be $name of the Syncfusion component$+$language code$+.resx. For example, if you add a resource file for French culture. Then, add the Syncfusion.SfChart.XForms.fr-FR.resx file to Resources folder as illustrated in the following screenshot.

3. Provide French values for each key in the respective .resx files. Here, “Close” and “High” are the keys, and “Fermer” and “Haute” are their respective French values.

{% highlight xaml %}

<data name="Close" xml:space="preserve">
  <value>Fermer</value>
</data>
<data name="High" xml:space="preserve">
  <value>Haute</value>
</data>  

{% endhighlight %} 

4. Set the resource manager to [‘ChartResourceManager.Manager’](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartResourceManager~Manager.html) to get the resource manager from the user as illustrated in the following code sample. For more details, please click [`here`](https://blog.syncfusion.com/post/localization-made-easy-for-syncfusion-xamarin-forms-components.aspx).

{% highlight C# %}

ChartResourceManager.Manager = new ResourceManager("GettingStarted.Resources.Syncfusion.SfChart.XForms", Application.Current.GetType().Assembly);

{% endhighlight %} 