---
layout: post
title: Display Type
description: Different display types available in Syncfusion TabView control for Xamarin.Forms platform
platform: Xamarin.Forms
control: TabView
documentation: ug
---

# Display Type

Tab view will display the title of each tab item by default. It can be changed to any of the below type.

* Text only.
* Image only.
* Image with text.
* No header.

![](images/Display-Type/tabstyle01.png)


It can be changed by settings the `DisplayMode` property of `SfTabView`.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView VisibleHeaderCount="3" DisplayMode="ImageWithText" >

{% endhighlight %}

{% highlight C# %}

tabView.DisplayMode = TabDisplayMode.ImageWithText;

{% endhighlight %}

{% endtabs %}

`No header` can be used when header is not needed for the tab view control, so content space will be occupied in the entire available height.

N> Image appearance in the header can be achieved through font icons.

## How to change the selection color for text and font icons?

Selected index can be differentiated by setting `SelectionColor` property of `SfTabItem`.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabItem 
			Title="Calls"
			SelectionColor="Green">
			
{% endhighlight %}

{% highlight C# %}

var tabViewItem = new SfTabItem()
			{
				Title = "Calls",
				TitleFontColor = Color.Green,
			}
			
{% endhighlight %}

{% endtabs %}

Further customizations of header are discussed in the below sections.

* How to customize text appearance of the header title?
* How to set and customize font icons appearance in the header?
* Setting font file for font icons.

## How to customize text appearance of the header title?

{% tabs %}

{% highlight xaml %}

tabView:SfTabItem 
			Title="Calls"
			TitleFontAttributes="Bold"
			TitleFontColor="Red"
			TitleFontSize="22">

			
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

## How to set and customize font icons appearance in the header?

Add the font file into your application by following the below steps for each platform.

**Adding font file for iOS**

* Add the font file with Build Action: `BundleResource`, and
* Update the `Info.plist` file (Fonts provided by application, or UIAppFonts, key).

**Adding font file for Android**

* Add the font file to the `Assets` folder in the application project and set Build Action: `AndroidAsset`.

**Setting font file for font icons**

{% tabs %}

{% highlight xaml %}

<ResourceDictionary>
	<OnPlatform x:TypeArguments="x:String" x:Key="fontfamily" iOS="TabIcons" Android="TabIcons.ttf" />
</ResourceDictionary>

	// . . . //

<tabview:SfTabItem Title="Calls"
	IconFont="a"
	FontIconFontColor="LightBlue"
	FontIconFontSize="20"
	FontIconFontFamily="{StaticResource fontfamily}">
			
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
