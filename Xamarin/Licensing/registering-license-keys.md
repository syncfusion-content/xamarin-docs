---
layout: post
title: About Essential Studio Xamarin Licensing | Syncfusion
description: Learn here about Syncfusion Essential Studio Xamarin license key, how to generate the license key, how to register the license key, and more details.
platform: Xamarin
control: Essential Studio
documentation: ug
---


# License Key Registration

The generated license key is just a string that needs to be registered before any Syncfusion control is initiated. The following code is used to register the license.

{% tabs %}
{% highlight c# %}
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
{% endhighlight %}
{% endtabs %}

N> Place the license key between double quotes.  Also, ensure that Syncfusion.Licensing.dll is referenced in your project where the license key is being registered.


You can register the license key in **App.xaml.cs** constructor before InitializeComponent(). If App constructor not available in **App.xaml.cs**, create the "App()" constructor in **App.xaml.cs** and register the license key inside the constructor.

{% tabs %}
{% highlight c# %}
public App()
{
	//Register Syncfusion license
	Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
	
	InitializeComponent();
	
	MainPage = new App1.MainPage();
}
{% endhighlight %}
{% endtabs %}

N> If you are developing an application using Gorilla Player SDK, it is must to register the Syncfusion license key in Xamarin.Forms.Android, Xamarin.Forms.iOS, and Xamarin.Forms.UWP.
   Refer [this link](https://help.syncfusion.com/xamarin/licensing/licensing#xamarinandroid) to register Syncfusion license key in Xamarin.Forms.Android
   Refer [this link](https://help.syncfusion.com/xamarin/licensing/licensing#xamarinios) to register Syncfusion license key in Xamarin.Forms.iOS
   Refer [this link](https://help.syncfusion.com/xamarin/licensing/licensing#uwp) to register Syncfusion license key in Xamarin.Forms.UWP



If you are using **Prism Framework** in your application, register the license key before InitializeComponent in OnInitialized method of **App.Xaml.cs**

{% tabs %}
{% highlight c# %}
protected override async void OnInitialized()
{
	//Register Syncfusion license
    Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
 
    InitializeComponent();
 
    await NavigationService.NavigateAsync("NavigationPage/MainPage");
}
{% endhighlight %}
{% endtabs %}

N> Refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/licensing-errors) for common licensing errors