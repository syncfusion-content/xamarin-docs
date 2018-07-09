---
layout: post
title: Localization of Kanban
description: How to Localize the contents of Kanban control.
platform: xamarin
control: Kanban
documentation: ug
---

# Localization 

Localization is the process of translating the application resources into different languages for specific cultures. You can localize the SfKanban by adding a resource file. Application culture can be changed by setting the `DefaultThreadCurrentCulture` and `DefaultThreadCurrentUICulture` in the MainPage() constructor. 

In the following code example, application culture is configured to French language.

{% tabs %}
{% highlight c# %}
public MainPage()
{
    this.InitializeComponent();
	CultureInfo.DefaultThreadCurrentCulture = new CultureInfo("fr-FR");
    CultureInfo.DefaultThreadCurrentUICulture = new CultureInfo("fr-FR");
}
{% endhighlight %}
{% endtabs %}

To localize the SfKanban based on `DefaultThreadCurrentCulture` and `DefaultThreadCurrentUICulture` using resource files, use the following steps: 

1.Right-click the PCL project, click **Add** and then click **NewFolder**, name the folder as **Resources**.

2.Right-click the **Resources** folder, click **Add** and then click **NewItem**.

3.In Add New Item  dialog, click the Resource File and name the filename as **Syncfusion.SfKanban.Forms.[culture name].resx**. The culture name indicates name of language and country.

For example, you will have to give name as **Syncfusion.SfKanban.Forms.fr-FR.resx** for French culture.

![](SfKanban_images\LocalizationAddResource.png)

4.Add the Name/Value pair in Resource Designer of **Syncfusion.SfKanban.Forms.[culture name].resx** file and change its corresponding value to corresponding culture.

You can get the SfKanban’s key from default resource [Syncfusion.SfKanban.Forms.en-US.resx](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Syncfusion.SfKanban.Forms.en-US-2068260575.zip).

![](SfKanban_images\LocalizationOutput.png)

You can download the sample for localization of kanban from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/PCL_Local1653220814.zip)