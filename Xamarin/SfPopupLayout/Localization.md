---
layout: post
title: Localization | SfPopupLayout | Xamarin | Syncfusion
description: How to set a Localized text for SfPopupLayout static texts.
platform: xamarin
control: SfPopupLayout
documentation: UG
---

# Localization 

Localization is the process of translating the application resources into different language for the specific cultures. SfPopupLayout uses the following static texts which can be localized in the application level.

* Title
* ACCEPT
* DECLINE
* Popup_message

To localize the SfPopupLayout please follow the below steps that has to be done in the application level.

* Adding a .resx file
* Convert platform specific language format to .NET format
* Applying the converted format

## Adding a .resx file

In the portable project of your application, add a `.resx` file inside the resources folder with **Build Action -> EmbeddedResource** Please follow the below conventions in naming the file.

File name should be of the format "Syncfusion control's Namespace" + "language code"
For example if you want to set culture as French, the file should be named as **Syncfusion.SfPopupLayout.XForms.fr-FR.resx**.

In the .resx file, based on the language you have to set the appropriate texts equivalent to the static texts.

N> You will have to create and add separate .resx files for individual languages.

![](SfPopupLayout_images/PopupLayoutResx.png)

## Convert platform specific language format to .NET format

To get the localized text from the added `.resx` file, declare an interface named ILocalize in your PCL project and implement the interface in each of the platform renderers. This will query the language which is set in the device using platform specific code and then convert this platform specific format to a .NET format.

Please refer the below code snippet to declare the interface in the PCL project.

{% tabs %}
{% highlight c# %}

public interface ILocalize
{
    CultureInfo GetCurrentCultureInfo();
    void SetLocale(CultureInfo cultureInfo);
}
public class PlatformCulture
{
    public PlatformCulture(string platformCultureString)
    {
        if (String.IsNullOrEmpty(platformCultureString))
            throw new ArgumentException("Expected culture identifier", "platformCultureString"); // in C# 6 use NameOf(platformCultureString)

        PlatformString = platformCultureString.Replace("_", "-"); // .NET expects dash, not underscore
        var dashIndex = PlatformString.IndexOf("-", StringComparison.Ordinal);
        if (dashIndex > 0)
        {
            var parts = PlatformString.Split('-');
            LanguageCode = parts[0];
            LocaleCode = parts[1];
        }
        else
        {
            LanguageCode = PlatformString;
            LocaleCode = "";
        }
    }

    public string PlatformString
    {
        get; private set;
    }

    public string LanguageCode
    {
        get; private set;
    }

    public string LocaleCode
    {
        get; private set;
    }

    public override string ToString()
    {
        return PlatformString; ;
    }
}

{% endhighlight %}
{% endtabs %}


Refer the below codes to implement the interface in Android renderer project.
{% tabs %}
{% highlight c# %}

public class Localize : ILocalize

{

    public void SetLocale(CultureInfo cultureInfo)
    {
        Thread.CurrentThread.CurrentCulture = cultureInfo;
        Thread.CurrentThread.CurrentUICulture = cultureInfo;
    }

    public CultureInfo GetCurrentCultureInfo()
    {
        var netLanguage = "en";
        var androidLocale = Java.Util.Locale.Default;
        netLanguage = AndroidToDotnetLanguage(androidLocale.ToString().Replace("_", "-"));

        // this gets called a lot - try/catch can be expensive so consider caching or something
        CultureInfo cultureInfo = null;
        try
        {
            cultureInfo = new CultureInfo(netLanguage);
        }
        catch
        {
            // iOS locale not valid .NET culture (eg. "en-ES" : English in Spain)
            // fallback to first characters, in this case "en"
            try
            {
                var fallback = ToDotnetFallbackLanguage(new PlatformCulture(netLanguage));
                cultureInfo = new CultureInfo(fallback);
            }
            catch
            {
                // iOS language not valid .NET culture, falling back to English
                cultureInfo = new CultureInfo("en");
            }
        }

        return cultureInfo;
    }



    private string AndroidToDotnetLanguage(string androidLanguage)
    {
        var netLanguage = androidLanguage;

        //certain languages need to be converted to CultureInfo equivalent
        switch (androidLanguage)
        {
            case "ms-BN":   // "Malaysian (Brunei)" not supported .NET culture
            case "ms-MY":   // "Malaysian (Malaysia)" not supported .NET culture
            case "ms-SG":   // "Malaysian (Singapore)" not supported .NET culture
                netLanguage = "ms"; // closest supported
                break;
            case "in-ID":  // "Indonesian (Indonesia)" has different code in  .NET 
                netLanguage = "id-ID"; // correct code for .NET
                break;
            case "gsw-CH":  // "Schwiizertüütsch (Swiss German)" not supported .NET culture
                netLanguage = "de-CH"; // closest supported
                break;
                // add more application-specific cases here (if required)
                // ONLY use cultures that have been tested and known to work
        }

        return netLanguage;
    }

    private string ToDotnetFallbackLanguage(PlatformCulture platformCulture)
    {
        var netLanguage = platformCulture.LanguageCode; // use the first part of the identifier (two chars, usually);

        switch (platformCulture.LanguageCode)
        {
            case "gsw":
                netLanguage = "de-CH"; // equivalent to German (Switzerland) for this app
                break;
                // add more application-specific cases here (if required)
                // ONLY use cultures that have been tested and known to work
        }

        return netLanguage;
    }

}
{% endhighlight %}
{% endtabs %}

Refer the below codes to implement the interface in iOS renderer project.
{% tabs %}
{% highlight c# %}

public class Localize : ILocalize
{
    public void SetLocale(CultureInfo cultureInfo)
    {
        Thread.CurrentThread.CurrentCulture = cultureInfo;
        Thread.CurrentThread.CurrentUICulture = cultureInfo;
    }

    public CultureInfo GetCurrentCultureInfo()
    {
        var netLanguage = "en";
        if (NSLocale.PreferredLanguages.Length > 0)
        {
            var pref = NSLocale.PreferredLanguages[0];

            netLanguage = iOSToDotnetLanguage(pref);
        }

        // this gets called a lot - try/catch can be expensive so consider caching or something
        CultureInfo cultureInfo = null;
        try
        {
            cultureInfo = new CultureInfo(netLanguage);
        }
        catch
        {
            // iOS locale not valid .NET culture (eg. "en-ES" : English in Spain)
            // fallback to first characters, in this case "en"
            try
            {
                var fallback = ToDotnetFallbackLanguage(new PlatformCulture(netLanguage));
                cultureInfo = new CultureInfo(fallback);
            }
            catch
            {
                // iOS language not valid .NET culture, falling back to English
                cultureInfo = new CultureInfo("en");
            }
        }

        return cultureInfo;
    }
    private string iOSToDotnetLanguage(string iOSLanguage)
    {
        var netLanguage = iOSLanguage;

        //certain languages need to be converted to CultureInfo equivalent
        switch (iOSLanguage)
        {
            case "ms-MY":   // "Malaysian (Malaysia)" not supported .NET culture
            case "ms-SG":   // "Malaysian (Singapore)" not supported .NET culture
                netLanguage = "ms"; // closest supported
                break;
            case "gsw-CH":  // "Schwiizertüütsch (Swiss German)" not supported .NET culture
                netLanguage = "de-CH"; // closest supported
                break;
                // add more application-specific cases here (if required)
                // ONLY use cultures that have been tested and known to work
        }

        return netLanguage;
    }

    private string ToDotnetFallbackLanguage(PlatformCulture platCulture)
    {
        var netLanguage = platCulture.LanguageCode; // use the first part of the identifier (two chars, usually);

        switch (platCulture.LanguageCode)
        {
            // 
            case "pt":
                netLanguage = "pt-PT"; // fallback to Portuguese (Portugal)
                break;
            case "gsw":
                netLanguage = "de-CH"; // equivalent to German (Switzerland) for this app
                break;
                // add more application-specific cases here (if required)
                // ONLY use cultures that have been tested and known to work
        }

        return netLanguage;
    }
}

{% endhighlight %}
{% endtabs %}

Implementation of the interface is not required for UWP project, since the resources automatically recognizes the selected language on UWP.

## Applying the converted format 

After implementing the necessary interface and creating the necessary .resx files, now in your App.Xaml.cs file of the PCL project, after setting the root/main page of your application, initialize a new instance of the `ResourceManager` class and set it to the [PopupLayoutResourceManager.Manager](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayoutResourceManager~Manager.html) property to look up into resources with the specified root name in the given assembly. Now using `DependencyService` call the implemented interface's `SetLocale()` with the necessary language code as parameter. Please refer the below code snippet.

{% tabs %}
{% highlight c# %}

public partial class App : Application
{
    public App()
    {
        InitializeComponent();

        MainPage = new GettingStarted.MainPage();
        
        if (Device.RuntimePlatform == Device.iOS || Device.RuntimePlatform == Device.Android)
        {
            PopupLayoutResourceManger.Manager = new ResourceManager("GettingStarted.Resources.Syncfusion.SfPopupLayout.XForms", this.GetType().GetTypeInfo().Assembly);
            // the ResourceManager class constructor has two parameters.
            // 1. ResXPath => Full path of the resx file in the application. Here in the above line GettingStarted refers to the namespace of the Application
            // 2. Assembly => Application assembly (PCL)
    
            // Sets the required culture to the static texts in the control.
            DependencyService.Get<ILocalize>().SetLocale(new CultureInfo("fr-FR"));
        }
    }
} 

{% endhighlight %}
{% endtabs %}

For Android and iOS, it is mandatory to implement the above steps. For UWP, it is not mandatory to implement the above items, since the resources automatically recognizes the selected language on UWP. However, if you want to set language specific to the application irrespective of the selected language in the device, you can set it by using `CultureInfo.CurrentUICulture` in UWP platform specific project.

Refer the below code example to localize the text in UWP platform.

MainPage.Xaml.cs
{% tabs %}
{% highlight c# %}

public MainPage()
{
    this.InitializeComponent();
    SfPopupLayoutRenderer.Init();
    // Applying localization for UWP
    CultureInfo.CurrentUICulture = new CultureInfo("fr");
    LoadApplication(new SwitchSample.App());
}

{% endhighlight %}
{% endtabs %}

You can download the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SfGrid_Sample1621493322).