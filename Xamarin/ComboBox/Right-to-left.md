---
layout: post
title: Right to left(RTL) in Xamarin ComboBox control | Syncfusion
description: Learn here all about Right to left(RTL) support in Syncfusion Xamarin ComboBox (SfComboBox) control and more.
platform: xamarin
control: SfComboBox
documentation: UG
---

# Right to left(RTL) in Xamarin ComboBox (SfComboBox)

[`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) supports to change the layout direction of the control in the right-to-left direction by setting the [`FlowDirection`](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.visualelement.flowdirection?view=xamarin-forms#Xamarin_Forms_VisualElement_FlowDirection) to [`RightToLeft`](https://devblogs.microsoft.com/xamarin/right-to-left-localization-xamarin-forms) or by changing the device language.

{% tabs %}
{% highlight xaml %}
<combobox:SfComboBox FlowDirection="RightToLeft">
</combobox:SfComboBox>
{% endhighlight %}
{% highlight c# %}
combobox.FlowDirection = FlowDirection.RightToLeft;
{% endhighlight %}
{% endtabs %}

>**Note**
For implementing the[`FlowDirection`](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.visualelement.flowdirection?view=xamarin-forms#Xamarin_Forms_VisualElement_FlowDirection) in the control, Xamarin.Forms package version must be 3.0 and above. Please refer [`RightToLeft`](https://devblogs.microsoft.com/xamarin/right-to-left-localization-xamarin-forms) to get more details about [`RightToLeft`](https://devblogs.microsoft.com/xamarin/right-to-left-localization-xamarin-forms) flow direction in Xamarin.Forms.

### Android
For Android, add `android:supportsRtl="true"` in your application tag of `AndroidManifest.xml` file, and make sure your `MinSDKVersion` is 17+. By changing the device language / enabling the device's `Force RTL layout` can achieve the [`RightToLeft`](https://devblogs.microsoft.com/xamarin/right-to-left-localization-xamarin-forms) layout direction in Calendar.

{% tabs %}
{% highlight xml %}
<manifest ... >
<uses-sdk android:minSdkVersion="17" ... />
<application ... android:supportsRtl="true">
</application>
</manifest>
{% endhighlight %}
{% endtabs %}

### iOS
For iOS, add the [`RightToLeft`](https://devblogs.microsoft.com/xamarin/right-to-left-localization-xamarin-forms) language in the `CFBundleLocalizations` section of your `Info.plist` file, and make sure you’re targeting iOS 9+.

{% tabs %}
{% highlight xml %}
<resources>
<key>CFBundleDevelopmentRegion</key>
<string>en</string>
<key>CFBundleLocalizations</key>
<array>
<string>en</string>
<string>ar</string>
</array>
</resources>
{% endhighlight %}
{% endtabs %}

![info plist](images/RTL/ComboBox_iosplist.png)

### UWP
For UWP, you need to set [`FlowDirection`](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.visualelement.flowdirection?view=xamarin-forms#Xamarin_Forms_VisualElement_FlowDirection) to [`RightToLeft`](https://devblogs.microsoft.com/xamarin/right-to-left-localization-xamarin-forms) in the `MainPage.cs` file of the `UWP` project.

{% tabs %}
{% highlight c# %}
public MainPage()
{
…
this.FlowDirection = FlowDirection.RightToLeft;
LoadApplication (new App ());
…
}
{% endhighlight %}
{% endtabs %}

![RTL in Xamarin.Forms ComboBox](images/RTL/Xamarin.Forms-ComboBox-rtl.png)

The complete RTL sample is available in this [link](https://github.com/SyncfusionExamples/rtl-sample-combobox).
