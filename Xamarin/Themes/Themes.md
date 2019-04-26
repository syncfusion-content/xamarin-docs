---
layout: post
title: Applying themes
description: This section explains about theming in Syncfusion controls and how to override the key values for further customization
platform: xamarin
control: General
documentation: ug
---

Syncfusion themes allow you apply colors across all the Syncfusion controls with a uniform approach and provide consistent look and feel to your applications. This section covers the following topics:

* Applying light and dark themes
* Overrding the default theme
* Creating your own theme

## Applying light and dark themes

By default, Syncfusion provides support for light and dark themes. As names suggest, these themes will have colors with light and dark color contrasts, respectively.

To apply themes to your application, merge the following items:

* Theme resource dictionary
* Control style resource dictionaries

#### Theme resource dictionary

This resource dictionary contains *keys* and their respective color codes for all the Syncfusion controls. Currently, the following two theme resource dictionaries are available:

* Light theme resource dictionary
* Dark theme resource dictionary

#### Control style resource dictionaries

Each Syncfusion control has a separate control style resource dictionary, whose styles are mapped to the keys declared in [theme resource dictionary](https://help.syncfusion.com/xamarin/themes/themes#theme-resource-dictionary) as a ['DynamicResource'](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/styles/xaml/dynamic).

{% highlight xaml %}
<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
xmlns:inputLayout="clr-namespace:Syncfusion.XForms.TextInputLayout;assembly=Syncfusion.Core.XForms"
xmlns:chart="clr-namespace:Syncfusion.SfChart.XForms;assembly=Syncfusion.SfChart.XForms" 
...>
<Application.Resources>
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                <!-- Theme resource dictionary -->
                <syncTheme:DarkTheme />
                <!-- Control style resource dictionaries -->
                <chart:SfChartStyles />
                <inputLayout:SfTextInputLayoutStyles />
            </ResourceDictionary.MergedDictionaries>
        </ResourceDictionary>
</Application.Resources>

....

</Application>

{% endhighlight %}

### Merging the dictionaries

You can merge the theme resource dictionary and control style resource dictionaries in the following two ways:

#### Manual merging

For manual merging, both the theme resource dictionary and each control style resource dictionary need to be merged for the required controls in the application resources as follows.

{% highlight xaml %}
<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
xmlns:inputLayout="clr-namespace:Syncfusion.XForms.TextInputLayout;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
        <ResourceDictionary>
            < ResourceDictionary.MergedDictionaries>
                <!-- Theme resource dictionary -->
                <syncTheme:LightTheme />
                <!-- Control style resource dictionaries -->
                <chart:SfChartStyles />
                <inputLayout:SfTextInputLayoutStyles />
            </ ResourceDictionary.MergedDictionaries>
        </ ResourceDictionary >
</Application.Resources>

....

</Application>

{% endhighlight %}

#### Automatic merging

When using more number of Syncfusion controls in an application, to make the process easier for merging the control style dictionaries of the controls, the SyncfusionThemeDictionary class has been provided for automatic merging. When the theme resource dictionary is merged to this dictionary, control style resource dictionaries will be merged automatically. However, only the styles for the controls used in the application will be merged.

{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>

<Application.Resources>
    <syncTheme:SyncfusionThemeDictionary>
        <syncTheme:SyncfusionThemeDictionary.MergedDictionaries>
            <!-- Theme resource dictionary -->
            <syncTheme:LightTheme />
        </syncTheme:SyncfusionThemeDictionary.MergedDictionaries>
    </syncTheme:SyncfusionThemeDictionary>
</Application.Resources>

....

</Application>

{% endhighlight %}

## Overriding the default theme

The theme resource dictionary contains a set of keys that are mapped to styles in control style dictionaries. The default appearance of themes can be customized by overriding the key values.

The following section explains how to override both the primary and control specific keys.

### Overriding the primary keys

The theme resource dictionary contains the following set of primary keys that are mapped to the UI elements of all the controls. To override the primary colors of theme, change the values for these keys as required. You can find the keys and the UI elements to which they are mapped to all the controls in this [documentation](https://help.syncfusion.com/xamarin/themes/keys).

* SyncPrimaryColor
* SyncPrimaryLightColor
* SyncPrimaryDarkColor
* SyncPrimaryForegroundColor
* SyncPrimaryLightForegroundColor
* SyncPrimaryDarkForegroundColor
* SyncSuccessColor
* SyncErrorColor
* SyncWarningColor
* SyncInfoColor

{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <syncCore:LightTheme />
            <ResourceDictionary>
                <Color x:Key="SyncPrimaryColor">Green</Color>
            </ResourceDictionary>
        </syncCore:SyncfusionThemeDictionary.MergedDictionaries>
    </syncCore:SyncfusionThemeDictionary>
</Application.Resources>

....

</Application>

{% endhighlight %}

### Overriding the control specific keys

In addition to the primary keys, the theme resource dictionary also contains the keys that are specific to each controls; these keys can also be overridden. You can find the keys and the UI elements to which they are mapped to all the controls in this [documentation](https://help.syncfusion.com/xamarin/themes/keys).

{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <syncCore:LightTheme />
            <ResourceDictionary>
                <Color x:Key="SfTextInputLayoutHintColor">Red</Color>
            </ResourceDictionary>
        </syncCore:SyncfusionThemeDictionary.MergedDictionaries>
    </syncCore:SyncfusionThemeDictionary>
</Application.Resources>

....

</Application>

{% endhighlight %}

## Creating your own theme

As an alternative approach to the above methods, you can also create your own theme. To create own theme, first, you need to merge the resource, whose key name should be "ControlName" + "Theme" based on the controls, e.g., SfChartTheme and SfTextInputLayoutTheme. You can find this key for each control in this [documentation](https://help.syncfusion.com/xamarin/themes/keys). After merge the control name, you need to merge the required color resources with keys based on the UI elements that need to be customized. You can find the keys and the UI elements to which they are mapped to all the controls in this [documentation](https://help.syncfusion.com/xamarin/themes/keys).

Using this approach, you can create your own theme to all the controls or for specifc controls you need. 

{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfTextInputLayoutTheme">CustomTheme</x:String> 
                <Color x:Key="SfTextInputLayoutCounterLabelColor">Blue</Color> 
                <Color x:Key="SfTextInputLayoutCounterLabelDisabledColor">Green</Color>
            </ResourceDictionary>
        </syncCore:SyncfusionThemeDictionary.MergedDictionaries>
    </syncCore:SyncfusionThemeDictionary>
</Application.Resources>

....

</Application>

{% endhighlight %}

 

