---
layout: post
title: Themes for Syncfusion Controls
description: This section explains about theming in Syncfusion controls and how to override the key values for further customization
platform: xamarin
control: General
documentation: ug
---

# Themes for Syncfusion Controls

Syncfusion themes allows you to apply common colors across all the Syncfusion controls to match your application theme by merging the following items your application resources.

* Common theme resource for theme which contains the colors for the corresponding keys
* Control style dictionaries for individual controls in which the keys are mapped with control properties

## Automatic style merging

while using more number of Syncfusion controls in the application, to make the process easier for merging the control style of those controls, we have provided SyncfusionThemeDictionary class. When you merge the common theme resources to this dictionary, we will merge control styles automatically. However, only the styles for the used controls will be merged. 

{% highlight xaml %}

<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <syncCore:LightTheme />
        </syncCore:SyncfusionThemeDictionary.MergedDictionaries>
    </syncCore:SyncfusionThemeDictionary>
</Application.Resources>

{% endhighlight %}

## Manual style merging

It is also possible to merge only the requried controls for which theming is needed. Here, you have to merge both the common resource and each control style manually as follows. Hence SyncfusionThemeDictionary is not required here.

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

We have the following set of common keys which are mapped to specific elements in all of our controls. To override the overall appearance of the theme, you can change the values for these keys as required.

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

Pleae check the below section to know about overriding both common and control specific keys.

### Overriding key values

You can override the default values for the keys as needed by changing the values for the keys after merging the common theme resources.

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

## Customizing the internal properties of the controls

With the introduction of theming support, it is also possible now to customize some of the internal properties for more customization of the controls. In the below example, we are customizing the internal properties of SfTextInputLayout. Similar to this, you can customize for other controls with key "ControlName" + "Theme". You can find the keys and the elements to which they are mapped for all the controls in this link.[link]

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



