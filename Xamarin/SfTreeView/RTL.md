---
layout: post
title: RTL | TreeView for Xamarin.Forms | Syncfusion
description: Describes how to enable right-to-left localization treeview.
platform: xamarin
control: SfTreeView
documentation: ug
---

# Right-to-left localization

 TreeView supports right-to-left localization by setting the [VisualElement.FlowDirection](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.visualelement.flowdirection?view=xamarin-forms#Xamarin_Forms_VisualElement_FlowDirection) on a page, or root layout to `FlowDirection.RightToLeft` or by device's flow direction.

## Platform setup

Specific platform setup in application is required to enable right-to-left localization.

### Android
 
  In `AndroidManifest.xml` file, `<uses-sdk>` node sets the `android:minSdkVersion` attribute to `API 17 or higher on Android`, and the `<application>` node sets the `android:supportsRtl` attribute to `true`:

{% tabs %}
{% highlight xml %}

<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android" android:versionCode="1" android:versionName="1.0" package="com.companyname.RTLTreeView">
    <uses-sdk android:minSdkVersion="21" android:targetSdkVersion="27" />
    <application android:label="RTLTreeView.Android" android:supportsRtl="true"></application>
</manifest>

{% endhighlight %}
{% endtabs %}

Right-to-left localization can then be tested by changing the device/emulator to use the right-to-left language, or by enabling `Force RTL layout direction` in `Settings > Developer Options`.

### iOS

The required right-to-left locale should be added as a supported language to the array items for the `CFBundleLocalizations` key in `Info.plist`. The following example shows Arabic having been added to the array for the `CFBundleLocalizations` key:

{% tabs %}
{% highlight xml %}

<key>CFBundleLocalizations</key>
<array>
    <string>en</string>
    <string>ar</string>
</array>

{% endhighlight %}
{% endtabs %}

Right-to-left localization can then be tested by changing the device/emulator to use any of right-to-left language.

N> Right-to-left localization requires the use of `iOS 9` or higher, and `API 17` or higher on Android.

### Universal Windows Platform (UWP)
The required language resources should be specified in the `<Resources>` node of the `Package.appxmanifest` file. The following example shows `Arabic` language having been added to the <Resources> node:

{% tabs %}
{% highlight xml %}

<Resources>
    <Resource Language="x-generate"/>
    <Resource Language="en" />
    <Resource Language="ar" />
</Resources>

{% endhighlight %}
{% endtabs %}

For more information regarding platform setup for right-to-left localization you can refer [this](https://blog.xamarin.com/right-to-left-localization-xamarin-forms/) link.

## FlowDirection

`Flowdirection` gets or sets the direction in which UI elements flow within any parent element that controls their layout, and should be set to one of the FlowDirection enumeration values:

* `LeftToRight` - Indicates that view will be laid out left to right. This is the default when the view has no parent.
* `RightToLeft` - Indicates that view will be laid out right to left.
* `MatchParent` -	Indicates that the view's layout direction will match the parent view's layout direction.

N> The default `FlowDirection` property value for an element without a parent is `LeftToRight`, while the default `FlowDirection` for an element with a parent is `MatchParent`.

## Device flow direction

 TreeView responds to the device's flow direction based on the selected language. It can be achieved by setting the [FlowDirection]((https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.visualelement.flowdirection?view=xamarin-forms#Xamarin_Forms_VisualElement_FlowDirection) property on a page, or root layout, to the [Device.FlowDirection](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.device.flowdirection?view=xamarin-forms#Xamarin_Forms_Device_FlowDirection) value:

{% tabs %}
{% highlight xaml %}

<ContentPage FlowDirection="{x:Static Device.FlowDirection}" />

{% endhighlight %}
{% highlight c# %}

this.FlowDirection = Device.FlowDirection;

{% endhighlight %}
{% endtabs %}

All child elements of the page, or root layout, will by default then inherit the `Device.FlowDirection` value.Hence `TreeView` will also inherit the device's `FlowDirection`.

