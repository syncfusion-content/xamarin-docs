---
layout: post
title: Right-to-left | Rich Text Editor | Xamarin.Forms | Syncfusion
description: Describes how Syncfusion Rich Text Editor control works on right-to-left localization in Xamarin.Forms platform.
platform: xamarin
control: Rich Text Editor
documentation: UG
---

# Right to left(RTL)

Rich Text Editor provides support to change the layout direction of the control in the right-to-left direction by setting the [FlowDirection](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.visualelement.flowdirection?view=xamarin-forms#Xamarin_Forms_VisualElement_FlowDirection) to `RightToLeft` or by changing the device language.

{% tabs %}
{% highlight xaml %}
<Grid>	
	<richtexteditor:SfRichTextEditor FlowDirection="RightToLeft" />
</Grid>
{% endhighlight %}
{% highlight c# %}
	richTextEditor.FlowDirection = FlowDirection.RightToLeft;
{% endhighlight %}
{% endtabs %}

>**Note**
For implementing the `FlowDirection` in the control, Xamarin.Forms package version must be 3.0 and above. Refer to [RightToLeft](https://blog.xamarin.com/right-to-left-localization-xamarin-forms) to get more details about `RightToLeft` flow direction in Xamarin.Forms.

### Android
For Android, add `android:supportsRtl="true"` to your application tag of `AndroidManifest.xml` file, and make sure your `MinSDKVersion` is 17+. By changing the device language or enabling the device's `Force RTL layout`, you can achieve the `RightToLeft` layout direction in Rich Text Editor.

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
For iOS, add the `RightToLeft` language to the `CFBundleLocalizations` section of your `Info.plist` file, and make sure your are targeting iOS 9+.

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

![info plist](SfRichTextEditor_Images/iosplist.png)

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
![RTL in Xamarin.Forms Rich Text Editor](SfRichTextEditor_Images/RTL.png)
	