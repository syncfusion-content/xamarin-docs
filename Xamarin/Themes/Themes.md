---
layout: post
title: Themes for Syncfusion Controls
description: This section explains about theming in Syncfusion controls and how to override the key values for further customization
platform: xamarin
control: General
documentation: ug
---

# Themes for Syncfusion Controls

Syncfusion themes allows you to apply uniform colors across all the Syncfusion controls to match your application theme by merging the following items in your application resources.

* Common theme resource dictionary
* Control style resource dictionaries

## Common theme resource dictionary

This resource file contains the keys and its respective values for all the controls. These keys will be mapped to our control properties and when this resource is merged in the application resources, theme will be applied for the used control in the application. 

## Control style resource dictionaries

There is a control style resource dictonary for each and every control in which the actual mapping between the keys declared in common theme resource dictionary and public properties of that control is done. 

As mentioned earlier, it is needed to merge both these common theme resource dictionary and the control style resource dictionaries for the used controls to apply theme. There are two ways to merge these control style resource dictonaries as explained below.

## Automatic merging

While using more number of Syncfusion controls in an application, to make the process easier for merging the control style dictionary of those controls, we have provided SyncfusionThemeDictionary class for automatic merging. When the common theme resource dictionary is merged to this dictionary, control style resource dictionaries will be merged automatically. However, only the styles for the used controls will be merged. 

{% highlight xaml %}

<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <syncCore:LightTheme />
        </syncCore:SyncfusionThemeDictionary.MergedDictionaries>
    </syncCore:SyncfusionThemeDictionary>
</Application.Resources>

{% endhighlight %}

## Manual merging

It is also possible to merge only the required control style dictionaries for which theming is needed. Here, it is needed to merge both the common resource and each control style dictionary manually as follows. Hence, SyncfusionThemeDictionary is not required here.

{% highlight xaml %}

<Application.Resources>
        <ResourceDictionary>
            < ResourceDictionary.MergedDictionaries>
                <syncCore:LightTheme />
                <textinputlayout:SfTextInputLayoutStyles/>
            </ ResourceDictionary.MergedDictionaries>
        </ ResourceDictionary >
</Application.Resources>

{% endhighlight %}

## Common and control specific keys

In common theme resource dictionary, we have the following set of keys which are mapped to specific elements in all of our controls. To override the overall appearance of the theme, you can change the values for these keys as required.

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

In addition to that, you can also the override the keys which are specific to the controls. You can find the keys and the elements to which they are mapped for all the controls in this link.[link]

Please check the below section to know about overriding both common and control specific keys.

### Overriding key values

You can override the default values for the keys as needed by changing the values for the keys after merging the common theme resource dictionary.

{% highlight xaml %}

<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <syncCore:LightTheme />
            <ResourceDictionary>
                <Color x:Key="SyncPrimaryColor">Green</Color>
                <Color x:Key="SfTextInputLayoutHintColor">Red</Color>
            </ResourceDictionary>
        </syncCore:SyncfusionThemeDictionary.MergedDictionaries>
    </syncCore:SyncfusionThemeDictionary>
</Application.Resources>

{% endhighlight %}

You can find the sample in this link [link].

## Customization without resource dictionaries

It is also possible to customize the controls without merging common theme resource and control style resource dictionaries in the application resources. 

In the below example, we are customizing the UI elements of SfTextInputLayout by merging the resource with key name 'SfTextInputLayoutTheme' and in the next line, we set the values for the required keys. Similar to this, we can customize for the other controls by merging the resource with key name "ControlName" + "Theme" and in the next line, we can set the values for the required keys of that control. 

You can find the keys and the elements to which they are mapped for all the controls in this link.[link]

{% highlight xaml %}

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

{% endhighlight %}