---
layout: post
title: How to Apply the FontIcon for Syncfusion Chip Control | Xamarin.Forms
description: Learn how to apply a font icon to the SfChip and customize its features in Xamarin.Forms.
platform: Xamarin
control: Chips
documentation: ug
---

# Setting the FontIcon to SfChip

The SfChip control supports displaying a font icon by setting the `FontImageSource` to its [ImageSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) property. Follow these steps to configure it:

## Add a Custom Font File to All Platform Projects
- **Android:** Add the custom font file to the `Assets` folder and set the `Build Action` to `AndroidAsset` for the font file.
- **iOS:** Add the custom font file to the `Resources` folder, set the `Build Action` to `BundleResource`, and ensure the copy to output directory is set to `AlwaysCopy`.
- **UWP:** Add the custom font file to the `Assets` folder and set the `Build Action` to `Content`.

> Note: For iOS, you must add the custom font file in the `info.plist` file as demonstrated below.

{% tabs %}

{% highlight xaml %}

<dict>
...
<key>UIAppFonts</key>
<array>
<string>chip_Segoe MDL2 Assets.ttf</string>
...
</array>
</dict>

{% endhighlight %}

{% endtabs %}

Create an instance of `FontImageSource` and set it to the [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) property of SfChip, as shown in the code snippet below.

{% tabs %}

{% highlight xaml %}

<buttons:SfChip x:Name="Chip" 
                Text="Syncfusion" 
                ShowIcon="True">
    <buttons:SfChip.ImageSource>
        <FontImageSource Glyph="&#xEB52;" 
                         Size="40">
                <FontImageSource.FontFamily>
                    <OnPlatform x:TypeArguments="x:String" >
                        <On Platform="Android" Value="chip_Segoe MDL2 Assets.ttf#Segoe MDL2 Assets"/>
                        <On Platform="UWP" Value="Assets/chip_Segoe MDL2 Assets.ttf#Segoe MDL2 Assets"/>
                        <On Platform="iOS" Value="Segoe MDL2 Assets"/>
                    </OnPlatform>
                </FontImageSource.FontFamily>
        </FontImageSource>
    </buttons:SfChip.ImageSource> 
</buttons:SfChip>

{% endhighlight %}

{% highlight c# %}
 
 SfChip chip = new SfChip();
 chip.ShowIcon = true;
 chip.Text = "Syncfusion"; 

 var fontImageSource = new FontImageSource();
 fontImageSource.Glyph = "\uEB52";
 fontImageSource.Size = 40;

 if (Device.RuntimePlatform == Device.Android)
 {
     fontImageSource.FontFamily = "chip_Segoe MDL2 Assets.ttf#Segoe MDL2 Assets";
 }
 else if(Device.RuntimePlatform == Device.UWP)
 {
     fontImageSource.FontFamily = "Assets/chip_Segoe MDL2 Assets.ttf#Segoe MDL2 Assets";
 }
 else if(Device.RuntimePlatform == Device.iOS)
 {
     fontImageSource.FontFamily = "Segoe MDL2 Assets";
 }
            
 chip.ImageSource = fontImageSource;

{% endhighlight %}

{% endtabs %}

> Note: FontImageSource is supported from Xamarin.Forms version 3.6 onwards.

![Xamarin.Forms Chip Group Icon Font Support](images/FontIcon.png)
