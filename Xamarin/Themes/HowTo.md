---
layout: post
title: How to customize theming in Syncfusion controls
description: Learn here about how to switch between light and dark themes in Syncfusion Xamarin controls and more details.
platform: xamarin
control: General
documentation: ug
---

# Switching between light theme and dark theme

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

Similarly, to switch to dark theme from light theme, remove the light theme resource, and add the dark theme resource dictionary.