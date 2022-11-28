---
layout: post
title: Localization in Xamarin Kanban Board control | Syncfusion
description: Learn here all about Localization support in Syncfusion Xamarin Kanban Board (SfKanban) control and more.
platform: xamarin
control: Kanban
documentation: ug
---

# Localization in Xamarin Kanban Board (SfKanban)

You can localize [`SfKanban`](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html) in all the platforms by adding a .resx file in a .NET Standard project alone. The following steps describe how to localize SfKanban in a project and you can download the complete sample from this [`link`](http://www.syncfusion.com/downloads/support/directtrac/general/ze/PCL_Local1653220814.zip).
 
N> Here, the resources have been already created for some cultures and shared them on [`Syncfusion GitHub`](https://github.com/syncfusion/xamarin-localized-texts) for your convenience. 

1. Add a new folder in the .NET Standard project named Resources.

2. Add resource files for the languages you wish to support, and set their Build Action to EmbeddedResource. The name of the resource file should be $name of the Syncfusion component$+$language code$+.resx. For example, if you add a resource file for the French culture, add the Syncfusion.SfKanban.XForms.fr-FR.resx file to Resources folder as illustrated in the following screenshot.

![Localization support in Xamarin.Forms Kanban](SfKanban_images\LocalizationResource.png)

3. Provide the French values for each key in the respective .resx files. Here, “ItemsCount” and “Max” are the keys, and “Fritems” and “frmax” are their respective French values.

{% capture codesnippet1 %}
{% highlight xml %}

<data name="ItemsCount" xml:space="preserve">
    <value>Fritems</value>
</data>
<data name="Max" xml:space="preserve">
    <value>frmax</value>
</data>

{% endhighlight %}
{% endcapture %}
{{ codesnippet1 | UnOrderList_Indent_Level_1 }}

4. Set the resource manager to [‘KanbanResourceManager.Manager’](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanResourceManager.html#Syncfusion_SfKanban_XForms_KanbanResourceManager_Manager) as demonstrated in the following code to get the resource manager from the users. For more details, refer [`Localization`](https://blog.syncfusion.com/post/localization-made-easy-for-syncfusion-xamarin-forms-components.aspx).

{% capture codesnippet2 %}
{% highlight C# %}

KanbanResourceManager.Manager = new ResourceManager("GettingStarted.Resources.Syncfusion.SfKanban.XForms", Application.Current.GetType().Assembly);

{% endhighlight %}
{% endcapture %}
{{ codesnippet2 | UnOrderList_Indent_Level_1 }}

## Localize at application level

You can also localize the text at application-level regardless of the language selected on the device. The following platform-specific codes are needed to localize the text at application-level. Use the [`DependencyServices`](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/app-fundamentals/dependency-service/introduction) to set this from .NET Standard project.

{% highlight C# %}

//For Android and iOS,
Thread.CurrentThread.CurrentUICulture = new CultureInfo("fr-FR");

//For UWP,
CultureInfo.CurrentUICulture = new CultureInfo("fr-FR");

{% endhighlight %}

![Localization support in Xamarin.Forms Kanban](SfKanban_images\LocalizationOutput.png)
