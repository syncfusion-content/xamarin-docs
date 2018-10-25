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

N> Here, the resources have been already created for some cultures and shared them on [`Syncfusion GitHub`](https://github.com/syncfusion/xamarin-localized-texts) for your convenience.

1. Add a new folder in the .NET Standard project named Resources.

2. Add resource files for the languages you wish to support and set their Build Action to EmbeddedResource. The name of the resource file should be $name of the Syncfusion component$+$language code$+.resx. For example, if you add a resource file for the French culture, add the Syncfusion.SfChart.XForms.fr-FR.resx file to Resources folder as illustrated in the following screenshot.

![Localization support in Xamarin.Forms DateTimeRangeNavigator](localization_images/LocalizationResource.png)

3. Provide French values for each key in the respective .resx files. Here, “Quarter” and “Week” are the keys, and “Trimestre” and “La semaine” are their respective French values.

{% highlight xml %}

<data name="Quarter" xml:space="preserve">
  <value>Trimestre</value>
</data>
<data name="Week" xml:space="preserve">
  <value>La semaine</value>
</data>  

{% endhighlight %} 

4. Set the resource manager to [‘RangeNavigatorResourceManager.Manager’](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.RangeNavigatorResourceManager~Manager.html) to get the resource manager from users as demonstrated in the following code sample. For more details, please refer [`Localization`](https://blog.syncfusion.com/post/localization-made-easy-for-syncfusion-xamarin-forms-components.aspx).

{% highlight C# %}

RangeNavigatorResourceManager.Manager = new ResourceManager("GettingStarted.Resources.Syncfusion.SfChart.XForms", Application.Current.GetType().Assembly);

{% endhighlight %} 

## Localize at application level

You can also localize the text at application-level regardless of the language selected on the device. The following platform-specific codes are needed to localize the text at application-level. Use the [`DependencyServices`](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/app-fundamentals/dependency-service/introduction) to set this from .NET Standard project.

{% highlight C# %}

//For Android and iOS,
Thread.CurrentThread.CurrentUICulture = new CultureInfo("fr-FR");

//For UWP,
CultureInfo.CurrentUICulture = new CultureInfo("fr-FR");

{% endhighlight %} 

![Localization support in Xamarin.Forms DateTimeRangeNavigator](localization_images/RangeNavigatorLocalization.png)