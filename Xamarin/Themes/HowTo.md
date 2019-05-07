---
layout: post
title: How to customize theming in Syncfusion controls
description: This section explains about unique customizations in theming in Syncfusion controls
platform: xamarin
control: General
documentation: ug
---

## Switching between light theme and dark theme

To switch to light theme from dark theme, use the following code snippet.

{% highlight C# %} 
void UpdateTheme(object sender, System.EventArgs e)
{
    ICollection<ResourceDictionary> mergedDictionaries = Application.Current.Resources.MergedDictionaries;
    var darkTheme = mergedDictionaries.OfType<DarkTheme>().FirstOrDefault();
    if (darkTheme != null)  
    {
        mergedDictionaries.Remove(darkTheme);
    }
    mergedDictionaries.Add(new LightTheme());
}

{% endhighlight %}

Similary, to switch to dark theme from light theme, remove the light theme resource, and add the dark theme resource dictionary.