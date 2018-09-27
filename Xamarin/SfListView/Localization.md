---
layout: post
title:  Localization in SfListView
description: How to set a Localized text for SfListView static texts
platform: xamarin
control: SfListView
documentation: ug
---

# Localization

ListView allows you to set a localized text for the `Load More` static word.

The following steps explains how to apply localization for this static word in ListView:

* Add a resx file
* Query the language set in the device
* Implement the interface

## Add a resx file

In PCL application, add the required `resx` file in the resources folder with EmbeddedResource build action. The file name should contain the culture code.    

Example:
Culture   = French
File Name = fr-Fr.resx

N> `resx` file should contain the full name of the control. e.g. Syncfusion.SfListView.XForms.fr.resx. Then, initialize a new instance of `ResourceManager` class that looks up the resources with specified root name in the given assembly.

{% tabs %}
{% highlight c# %}
SfListViewResourceManger.Manager = new ResourceManager(ResXPath,Assembly);

//ResXPath => Full path of the resx file

//Assembly => Application assembly (PCL) 
{% endhighlight %}
{% endtabs %}

## Query the language set in the device

Follow the steps to query the language:

1. Query the language set in the device using the platform specific code. The result will be in the platform specific format.
2. Convert this platform specific format to .NET format and set it to `Thread.CurrentThread.CurrentUICulture`.

For Android and iOS, it is mandatory to implement the previous steps. For UWP, it is not mandatory to implement the previous steps. Since the resources automatically recognizes the selected language on UWP. However, to set a specific language to the application irrespective of the selected language in the device, use `CultureInfo.CurrentUICulture`.

{% tabs %}
{% highlight c# %}
 // In PCL project of MainPage.xaml.cs file
 if (Device.RuntimePlatform == Device.iOS || Device.RuntimePlatform == Device.Android)
 {
    DependencyService.Get<ILocalize>().SetLocale(new CultureInfo("fr-Fr"));
 }

 // In UWP project project of MainPage.xaml.cs file
 CultureInfo.CurrentUICulture = new CultureInfo("fr-Fr");
{% endhighlight %}
{% endtabs %}

## Implement the interface

To get the localized text from the added `resx` file, implement an interface from PCL to Android and iOS renderer projects.

{% tabs %}
{% highlight c# %}
// In PCL Application add a ILocalize interface
public interface ILocalize
{
    CultureInfo GetCurrentCultureInfo();
    void SetLocale(CultureInfo cir);
}

public class PlatformCulture
{
    public PlatformCulture(string platformCultureString)
    {
        if (String.IsNullOrEmpty(platformCultureString))
            throw new ArgumentException("Expected culture identifier", "platformCultureString"); // in C# 6 use name of (platformCultureString)

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

    public string PlatformString { get; private set; }

    public string LanguageCode { get; private set; }

    public string LocaleCode { get; private set; }

    public override string ToString()
    {
        return PlatformString;
    }
}
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
// Implement the interface in Android renderer project.
public class Localize : ILocalize
{
    public void SetLocale(CultureInfo cir)
    {
        Thread.CurrentThread.CurrentCulture = cir;
        Thread.CurrentThread.CurrentUICulture = cir;
    }

    public CultureInfo GetCurrentCultureInfo()
    {
        var netLanguage = "en";
        var androidLocale = Java.Util.Locale.Default;
        netLanguage = AndroidToDotnetLanguage(androidLocale.ToString().Replace("_", "-"));

        // this gets called a lot - try/catch can be expensive so consider caching or something
        CultureInfo cir = null;
        try
        {
            cir = new CultureInfo(netLanguage);
        }
        catch
        {
            // iOS locale not valid .NET culture (eg. "en-ES" : English in Spain)
            // fallback to first characters, in this case "en"
            try
            {
                var fallback = ToDotnetFallbackLanguage(new PlatformCulture(netLanguage));
                cir = new CultureInfo(fallback);
            }
            catch
            {
                // iOS language not valid .NET culture, falling back to English
                cir = new CultureInfo("en");
            }
        }

        return cir;
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

{% tabs %}
{% highlight c# %}
// Implement the interface in iOS renderer project
public class Localize : ILocalize
{
    public void SetLocale(CultureInfo cir)
    {
        Thread.CurrentThread.CurrentCulture = cir;
        Thread.CurrentThread.CurrentUICulture = cir;
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
        CultureInfo cir = null;
        try
        {
            cir = new CultureInfo(netLanguage);
        }
        catch
        {
            // iOS locale not valid .NET culture (eg. "en-ES" : English in Spain)
            // fallback to first characters, in this case "en"
            try
            {
                var fallback = ToDotnetFallbackLanguage(new PlatformCulture(netLanguage));
                cir = new CultureInfo(fallback);
            }
            catch
            {
                // iOS language not valid .NET culture, falling back to English
                cir = new CultureInfo("en");
            }
        }

        return cir;
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

For UWP project, there is no need to implement the interface since, the resources automatically recognizes the selected language.
