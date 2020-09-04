---
layout: post
title: How to apply the FontIcon for Syncfusion chip control | Xamarin.Forms
description: Learn how to apply the font icon to the Sfchip and its customization options with its available basic features in Xamarin.Forms
platform: xamarin
control: Chips
documentation: ug
---

# Setting the FontIcon to SfChip

SfChip is supported to display the font icon by setting `FontImageSource` to its [ImageSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) property with following below steps.

## Custom font file should be added to all the platform projects in specific location

* `Android` - Add a custom font file in the `Assets` folder and set the `Build Action` to `AndroidAsset` for the font file.
* `iOS` - Add a custom font file in the `Resources` folder and set the `Build Action` to `BundleResource`. Then, ensure that the copy to output directory is set to `AlwaysCopy`.
* `UWP` - Add a custom font file in the `Assets` folder and the set `Build Action` to `Content`.

N> For iOS, you should be added a custom font file in the info.plist file as demonstrated in below.

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


Create the instance for `FontImageSource` and set to [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) property of SfChip as shown in the below code snippet.

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


N> FontImageSource supported from Xamarin.Forms version 3.6 onwards.

![Xamarin.Forms chip group icon font support](images/FontIcon.png)