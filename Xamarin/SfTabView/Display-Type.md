---
layout: post
title: Display Type
description: Different display types available in Syncfusion TabView control for Xamarin.Forms platform
platform: Xamarin.Forms
control: TabView
documentation: ug
---

# Display Type

By default, the tab view control displays the title of each tab item. It can be changed to any of the following types:

* Text only
* Image only
* Image with text
* No header

![](images/Display-Type/tabstyle01.png)


The tab view can be changed by setting the `DisplayMode` property of `SfTabView`.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView VisibleHeaderCount="3" DisplayMode="ImageWithText" >

{% endhighlight %}

{% highlight C# %}

tabView.DisplayMode = TabDisplayMode.ImageWithText;

{% endhighlight %}

{% endtabs %}

The "no header" type can be used when the header is not needed for the tab view control. So, the content space will be occupied to the entire available height.

N> Image appearance in the header can be achieved through font icons.

## How to change the selection color for text and font icons?

The selected index can be differentiated by setting the `SelectionColor` property of `SfTabItem`.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabItem Title="Calls" SelectionColor="Green">
			
{% endhighlight %}

{% highlight C# %}

var tabViewItem = new SfTabItem()
	{
	Title = "Calls",
	TitleFontColor = Color.Green,
	}
	
{% endhighlight %}

{% endtabs %}

The further customizations of header are discussed in the following sections:

## How to customize text appearance of the header title?

{% tabs %}

{% highlight xaml %}

<tabView:SfTabItem Title="Calls" TitleFontAttributes="Bold" TitleFontColor="Red" TitleFontSize="22">
			
{% endhighlight %}

{% highlight C# %}

var tabViewItem = new SfTabItem()
	{
		Title = "Calls",
		Content = allContactsGrid,
		TitleFontAttributes = FontAttributes.Bold,
		TitleFontColor = Color.Red,
		TitleFontSize = 22
	}
			
{% endhighlight %}

{% endtabs %}

## How to set and customize the font icons' appearance in the header?

Add the font file to your application by using the following steps for each platform:

**Adding font file for iOS**

1. Add the font file with the following build action: `BundleResource`.
2. Update the `Info.plist` file (fonts that are provided by application, UIAppFonts, or key).

**Adding font file for Android**

Add the font file to the `Assets` folder in the application project, and set the following build action: `AndroidAsset`.

**Setting font file for font icons**

{% tabs %}

{% highlight xaml %}

<ResourceDictionary>
<OnPlatform x:TypeArguments="x:String" x:Key="fontFamily" iOS="TabIcons" Android="TabIcons.ttf" />
</ResourceDictionary>

	// . . . //

<tabview:SfTabItem Title="Calls"
IconFont="a"
FontIconFontColor="LightBlue"
FontIconFontSize="20"
FontIconFontFamily="{StaticResource fontFamily}">
			
{% endhighlight %}

{% highlight C# %}

var tabViewItem = new SfTabItem
	{
	Title = "Calls",
	Content = allContactsGrid,
	IconFont = "a", // setting value for font icons as mentioned in *.ttf.
	FontIconFontFamily = Device.RuntimePlatform == "iOS" ? "TabIcons" : "TabIcons.ttf",
	FontIconFontColor = Color.LightBlue,
	FontIconFontSize =  20
	};


{% endhighlight %}

{% endtabs %}
