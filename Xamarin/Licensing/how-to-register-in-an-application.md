---
layout: post
title: Register license key in Xamarin.Forms  | Syncfusion
description: Learn here about how to register Syncfusion® Xamarin license key for Xamarin application for license validation.
platform: xamarin
control: Essential Studio<sup>®</sup>
documentation: ug
---


# Register Syncfusion<sup>®</sup> License key in Xamarin application

The generated license key is just a string that needs to be registered before any Syncfusion<sup>®</sup> control is initiated. The following code is used to register the license.

{% tabs %}
{% highlight c# %}
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
{% endhighlight %}
{% endtabs %}

N> * Place the license key between double quotes.  Also, ensure that Syncfusion.Licensing.dll is referenced in your project where the license key is being registered.
* Syncfusion<sup>®</sup> license validation is done offline during application execution and does not require internet access.  Apps registered with a Syncfusion<sup>®</sup> license key can be deployed on any system that does not have an internet connection.

I> Syncfusion<sup>®</sup> license keys can be validated during the Continuous Integration (CI) processes to ensure proper licensing and prevent licensing errors during deployment. Refer to the [CI License Validation](https://help.syncfusion.com/xamarin/licensing/licensing-faq/ci-license-validation) section for detailed instructions on how to implement it.

### Xamarin.Forms

You can register the license key in **App.xaml.cs** constructor before InitializeComponent(). If App constructor not available in **App.xaml.cs**, create the "App()" constructor in **App.xaml.cs** and register the license key inside the constructor.

{% tabs %}
{% highlight c# %}
public App()
{
	//Register Syncfusion<sup>®</sup> license
	Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
	
	InitializeComponent();
	
	MainPage = new App1.MainPage();
}
{% endhighlight %}
{% endtabs %}

If you are developing an application using Gorilla Player SDK, it is must to register the Syncfusion<sup>®</sup> license key in Xamarin.Forms.Android, Xamarin.Forms.iOS, and Xamarin.Forms.UWP.


### Xamarin.Forms.Android

Register the license key in **OnCreate** override method of your main activity class before initializing any Syncfusion<sup>®</sup> control.

{% tabs %}
{% highlight c# %}
protected override void OnCreate(Bundle savedInstanceState)
{
	//Register Syncfusion<sup>®</sup> license
	Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");

	base.OnCreate(savedInstanceState);

	// Set our view from the "main" layout resource
	SetContentView(Resource.Layout.Main);
}
{% endhighlight %}
{% endtabs %}
 

### Xamarin.Forms.iOS

Register the license key in **FinishedLaunching** override method of **AppDelegate.cs**

{% tabs %}
{% highlight c# %}
public override bool FinishedLaunching(UIApplication application, NSDictionary launchOptions)
{
	//Register Syncfusion<sup>®</sup> license
	Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");

	// create a new window instance based on the screen size
	Window = new UIWindow(UIScreen.MainScreen.Bounds);

	// If you have defined a root view controller, set it here:
	// Window.RootViewController = myViewController;

	// make the window visible
	Window.MakeKeyAndVisible();

	return true;
} 
{% endhighlight %}
{% endtabs %}

### Xamarin.Forms.UWP

Register the license key in **App.xaml.cs** constructor before InitializeComponent() in C#. If App constructor not available in **App.xaml.cs**, create the "App()" constructor in **App.xaml.cs** and register the license key inside the constructor. In Visual Basic, register the licensing code in **App.xaml.vb** file before OnLaunched event.

{% tabs %}
{% highlight c# %}
public App()
{
	//Register Syncfusion<sup>®</sup> license
	Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");

	this.InitializeComponent();
	this.Suspending += OnSuspending;
}
{% endhighlight %}

{% highlight vb %}
Public Sub New()
	'Register Syncfusion<sup>®</sup> License
	Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY")
End Sub

Protected Overrides Sub OnLaunched(e As Windows.ApplicationModel.Activation.LaunchActivatedEventArgs)

...

End Sub
{% endhighlight %}

{% endtabs %}

If you are using **Prism Framework** in your application, register the license key before InitializeComponent in OnInitialized method of **App.Xaml.cs**

{% tabs %}
{% highlight c# %}
protected override async void OnInitialized()
{
	//Register Syncfusion<sup>®</sup> license
    Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
 
    InitializeComponent();
 
    await NavigationService.NavigateAsync("NavigationPage/MainPage");
}
{% endhighlight %}
{% endtabs %}

N> Refer to this [link](https://help.syncfusion.com/xamarin/licensing/licensing-errors) for common licensing errors
