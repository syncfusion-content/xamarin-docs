---
layout: post
title: Right to left (RTL) in Xamarin DataForm control | Syncfusion
description: Learn here all about Right to left (RTL) support in Syncfusion Xamarin DataForm (SfDataForm) control and more.
platform: xamarin
control: SfDataForm
documentation: UG
---

# Right to left (RTL) in Xamarin DataForm (SfDataForm)

SfDataForm supports to change the layout direction of the control in the right-to-left direction by setting the [FlowDirection](https://learn.microsoft.com/en-us/dotnet/api/xamarin.forms.visualelement.flowdirection?view=xamarin-forms#Xamarin_Forms_VisualElement_FlowDirection) to `RightToLeft` or by changing the device language.

{% tabs %}
{% highlight xaml %}
<dataForm:SfDataForm FlowDirection="RightToLeft">
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.FlowDirection = FlowDirection.RightToLeft;
{% endhighlight %}
{% endtabs %}

>**Note**
For implementing the `FlowDirection` in the control, Xamarin.Forms package version must be 3.0 and above. Please refer [RightToLeft](https://devblogs.microsoft.com/xamarin/right-to-left-localization-xamarin-forms/) to get more details about `RightToLeft` flow direction in Xamarin.Forms.

### Android
For Android, add `android:supportsRtl="true"` in your application tag of `AndroidManifest.xml` file, and make sure your `MinSDKVersion` is 17+. By changing the device language / enabling the device's `Force RTL layout` can achieve the `RightToLeft` layout direction in DataForm.

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
For iOS, add the `RightToLeft` language in the `CFBundleLocalizations` section of your `Info.plist` file, and make sure you’re targeting iOS 9+.

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

![info plist](SfDataForm_images/DataForm_iosplist.png)

### UWP
For UWP, you need to set `FlowDirection` to `RightToLeft` in the `MainPage.cs` file of the `UWP` project.

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

![RTL in Xamarin.Forms DataForm](SfDataForm_images/DataForm_RTL.png)

## See also

[How to customize the input direction of custom text editor in platform renderer](https://www.syncfusion.com/kb/9043/how-to-customize-the-input-direction-of-custom-text-editor-in-platform-renderer)                                                                                                                                                                                                                                                                                                                                                                                                        