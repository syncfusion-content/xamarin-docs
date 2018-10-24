---
layout: post
title: Localization of Xamarin.Forms SfDateTimeRangeNavigator
description: How to localize the labels in Xamarin.Forms SfDateTimeRangeNavigator.
platform: xamarin
control: SfDateTimeRangeNavigator
documentation: ug
---

## Localization 

You can set localization for [`SfDateTimeRangeNavigator`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html) in all the platforms by adding a .resx file in a .NET Standard project alone. The following steps describe how to set localization for SfDateTimeRangeNavigator in a project. 

N> Here, resources have been already created for some cultures and shared them on the [`Syncfusion GitHub`](https://github.com/syncfusion/xamarin-localized-texts) for your convenience.

1. Add a new folder in the .NET Standard project named Resources.

2. Add resource files for the languages you wish to support and set their Build Action to EmbeddedResource. The name of the resource file should be $name of the Syncfusion component$+$language code$+.resx. For example, if you add a resource file for French culture. Then, add the Syncfusion.SfChart.XForms.fr-FR.resx file to Resources folder as illustrated in the following screenshot.

3. Provide French values for each key in the respective .resx files. Here, “Quarter” and “Week” are the keys, and “Trimestre” and “La semaine” are their respective French values.

{% highlight xml %}

<data name="Quarter" xml:space="preserve">
  <value>Trimestre</value>
</data>
<data name="Week" xml:space="preserve">
  <value>La semaine</value>
</data>  

{% endhighlight %} 

4. Set the resource manager to [‘RangeNavigatorResourceManager.Manager’](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.RangeNavigatorResourceManager~Manager.html) to get the resource manager from the user as illustrated in the following code sample. For more details, please click [`here`](https://blog.syncfusion.com/post/localization-made-easy-for-syncfusion-xamarin-forms-components.aspx).

{% highlight C# %}

RangeNavigatorResourceManager.Manager = new ResourceManager("GettingStarted.Resources.Syncfusion.SfChart.XForms", Application.Current.GetType().Assembly);

{% endhighlight %} 

## Localize at the application level

We have seen how the application can be localized for the chosen language of the device. However, we can also localize the text at the application level regardless of the language selected on the device. The following platform-specific codes are needed to achieve this. Use the dependency services to set this from the .NET Standard project.

{% highlight C# %}

//For Android and iOS,
Thread.CurrentThread.CurrentUICulture = new CultureInfo("fr-FR");

//For UWP,
CultureInfo.CurrentUICulture = new CultureInfo("fr-FR");

{% endhighlight %} 

