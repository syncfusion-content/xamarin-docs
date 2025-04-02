---
layout: post
title: Right to left(RTL) in Xamarin Scheduler control | Syncfusion<sup>&reg;</sup>
description: Learn here all about Right to left(RTL) support in Syncfusion<sup>&reg;</sup> Xamarin Scheduler (SfSchedule) control and more.
platform: xamarin
control: SfSchedule
documentation: ug
---

# Right to left(RTL) in Xamarin Scheduler (SfSchedule)

SfSchedule supports to change the layout direction of the control in the right-to-left direction by setting the [FlowDirection](https://learn.microsoft.com/en-us/dotnet/api/xamarin.forms.visualelement.flowdirection?view=xamarin-forms#Xamarin_Forms_VisualElement_FlowDirection) to `RightToLeft` or by changing the device language.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule FlowDirection="RightToLeft">
</schedule:SfSchedule>
{% endhighlight %}
{% highlight c# %}
schedule.FlowDirection = FlowDirection.RightToLeft;
{% endhighlight %}
{% endtabs %}

>**Note**
For implementing the `FlowDirection` in the control, Xamarin.Forms package version must be 3.0 and above. Please refer [RightToLeft](https://learn.microsoft.com/en-us/xamarin/xamarin-forms/app-fundamentals/localization/right-to-left) to get more details about `RightToLeft` flow direction in Xamarin.Forms.

### Android
For Android, add `android:supportsRtl="true"` in your application tag of `AndroidManifest.xml` file, and make sure your `MinSDKVersion` is 17+. By changing the device language / enabling the device's `Force RTL layout` can achieve the `RightToLeft` layout direction in Schedule.

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

![info plist](Localization_images/scheduleiosplist.png)

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

N> You can refer to our [Xamarin Scheduler](https://www.syncfusion.com/xamarin-ui-controls/xamarin-scheduler) feature tour page for its groundbreaking feature representations. You can also explore our [Xamarin Scheduler example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/Schedule) to understand how to schedule and manage appointments.
