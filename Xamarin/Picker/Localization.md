---
layout: post
title: Localization of Syncfusion Xamarin.Forms Picker
description: This topic describe about the support to Localize the contents Xamarin.Forms Picker in all the platforms by adding a.resx file.
platform: xamarin
control: SfPicker
documentation: ug
---

# Localization for Xamarin.Forms Picker

You can localize `Picker` in all the platforms by adding a.resx file in a.NET Standard project alone. The following steps describe how to localize SfPicker in a project and you can download the complete sample from this [`link`](http://www.syncfusion.com/downloads/support/directtrac/general/ze/PickerLocalization868148122.zip).

> **NOTE**: Here, the resources have been already created for some cultures and shared them on [`Syncfusion GitHub`](https://github.com/syncfusion/xamarin-localized-texts) for your convenience.

1. Add a new folder in the .NET Standard project named Resources.

2. Add resource files for the languages you wish to support, and set their Build Action to EmbeddedResource. The name of the resource file should be $name of the Syncfusion component$+$language code$+.resx. For example, if you add a resource file for the French culture, add the Syncfusion.SfPicker.XForms.fr-FR.resx file to Resources folder as illustrated in the following screenshot.

![Localization support in Xamarin.Forms Picker](images/PickerLocalization.png)

3. Provide the French values for each key in the respective .resx files. Here, “Cancel” and “Ok” are the keys, and “Annuler” and “D'accord” are their respective French values.

{% highlight xml %}

<data name="Cancel" xml:space="preserve">
  <value>Annuler</value>
</data>
<data name="Ok" xml:space="preserve">
  <value>D'accord</value>
</data>  

{% endhighlight %} 

4. Set the resource manager to `PickerResourceManager.Manager` as demonstrated in the following code to get the resource manager from the users. For more details, refer [`Localization`](https://blog.syncfusion.com/post/localization-made-easy-for-syncfusion-xamarin-forms-components.aspx).

{% highlight C# %}

 PickerResourceManager.Manager = new ResourceManager("PickerLocalization.Resources.Syncfusion.SfPicker.XForms", Application.Current.GetType().Assembly);

{% endhighlight %} 

## Localize at application level

You can also localize the text at application-level regardless of the language selected on the device. The following platform-specific codes are needed to localize the text at application-level.
{% highlight C# %}

//For Android and iOS,
Thread.CurrentThread.CurrentUICulture = new CultureInfo("fr-FR");

//For UWP,
CultureInfo.CurrentUICulture = new CultureInfo("fr-FR");

{% endhighlight %} 

![Localization support in Xamarin.Forms SfPicker](images/Xamarin.Forms SfPicker.jpg)