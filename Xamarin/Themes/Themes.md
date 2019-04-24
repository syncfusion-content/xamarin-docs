---
layout: post
title: Applying themes
description: This section explains about theming in Syncfusion controls and how to override the key values for further customization
platform: xamarin
control: General
documentation: ug
---

Syncfusion themes allow you apply colors across all the Syncfusion controls through uniform approach which provides consistent look and feel for your application. In this section, we will cover the following items. 

* Applying light and dark theme
* Overrding the default theme
* Creating your own theme

## Applying light and dark theme

By default, we provide support for light and dark themes. As the name suggests, these themes will have colors which has lighter and darker color contrasts respectively.

In order to apply themes for your application, it is needed to merge the following items.

* Theme resource dictionary
* Control style resource dictionaries

#### Theme resource dictionary

This resource dictionary contains *keys* and their respective color codes for all the Syncfusion controls. Currently, there are two theme resource dictionaries.

1. Light theme resource dictionary
2. Dark theme resource dictionary

#### Control style resource dictionaries

Each Syncfusion control has a separate control style resource dictionary whose styles are mapped to the keys declared in [theme resource dictionary](https://help.syncfusion.com/xamarin/themes/themes#theme-resource-dictionary) as a ['DynamicResource'](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/styles/xaml/dynamic).

{% highlight xaml %}
<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
xmlns:inputLayout="clr-namespace:Syncfusion.XForms.TextInputLayout;assembly=Syncfusion.Core.XForms"
xmlns:chart="clr-namespace:Syncfusion.SfChart.XForms;assembly=Syncfusion.SfChart.XForms" 
...>
<Application.Resources>
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                <!-- Theme resource dictionary -->
                <syncTheme:LightTheme />
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

You can merge the theme resource dictionary and control style resource dictionaries in the following two ways.

#### Manual merging

For manual merging, both the theme resource dictionary and each control style resource dictionaries need to be merged for the required controls in the application resources as follows.

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

When using more number of Syncfusion controls in an application, to make the process easier for merging the control style dictionaries of the controls, the SyncfusionThemeDictionary class has been provided for automatic merging. When the theme resource dictionary is merged to this dictionary, control style resource dictionaries will be merged automatically. However, only the styles for the controls which are used in the application will be merged.

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

The theme resource dictionary contains set of keys which are mapped to the style in control style dictionaries. It is possible to customize the default theme appearance by overriding these key values.

The following section explains how to override both the primary and control specific keys.

### Overriding the primary colors

The theme resource dictionary contains the following set of primary keys which are mapped to the UI elements of all the controls. To override the primary colors, you can change the values for these keys as required. You can find the keys and the elements to which they are mapped for all the controls in this [link](https://help.syncfusion.com/xamarin/themes/keys).

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

In addition to the primary keys, the theme resource dictionary also contains the keys that are specific to each controls which can also be overridden. You can find the keys and the elements to which they are mapped for all the controls in this [link](https://help.syncfusion.com/xamarin/themes/keys).

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

As an alternative approach to the above methods, it is also possible to create your very own theme. For this, first you need to merge the unique key for each controls. This key name should be "ControlName" + "Theme" e.g. SfChartTheme, SfTextInputLayoutTheme. You can find this key for each control in this [link](https://help.syncfusion.com/xamarin/themes/keys). Once it is done, you need to merge the required resources with the keys. You can find these keys and the elements to which they are mapped for all the controls in this [link](https://help.syncfusion.com/xamarin/themes/keys).

Using this approach, you can create your own theme for all the controls or only the specifc controls which are needed. 

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

 





