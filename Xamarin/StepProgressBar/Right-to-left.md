---
layout: post
title: Right-to-left | StepProgressBar | Xamarin.Forms | Syncfusion
description: Describes how Syncfusion StepProgressBar control works on right-to-left localization in Xamarin.Forms platform.
platform: xamarin
control: StepProgressBar
documentation: UG
---

# Right to left (RTL)

StepProgressBar provides support to change the layout direction of the control in the right-to-left direction by setting the [FlowDirection](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.visualelement.flowdirection?view=xamarin-forms#Xamarin_Forms_VisualElement_FlowDirection) to `RightToLeft` or by changing the device language.

{% tabs %}
{% highlight xaml %}
	<progressBar:SfStepProgressBar FlowDirection="RightToLeft" >			
	</progressBar:SfStepProgressBar>
{% endhighlight %}
{% highlight c# %}
stepProgressBar.FlowDirection = FlowDirection.RightToLeft;
{% endhighlight %}
{% endtabs %}

>**Note**
For implementing the `FlowDirection` in the control, Xamarin.Forms package version must be 3.0 and above. Refer to [RightToLeft](https://blog.xamarin.com/right-to-left-localization-xamarin-forms) to get more details about `RightToLeft` flow direction in Xamarin.Forms.

### Android
For Android, add `android:supportsRtl="true"` to your application tag of `AndroidManifest.xml` file, and make sure your `MinSDKVersion` is 17+. By changing the device language or enabling the device's `Force RTL layout`, you can achieve the `RightToLeft` layout direction in StepProgressBar.

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
For iOS, add the `RightToLeft` language to the `CFBundleLocalizations` section of your `Info.plist` file, and make sure you are targeting iOS 9+.

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

![info plist](overview_images/StepProgressBar_iosplist.png)

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

![RTL in Xamarin.Forms StepProgressBar](overview_images/RTL.png)