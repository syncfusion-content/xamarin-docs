---
layout: post
title: Localization | SfPopupLayout |Xamarin| Syncfusion
description:  How to set a Localized text for SfPopupLayout static texts
platform: Xamarin
control: SfPopupLayout
documentation: ug
--- 

# Localization 

SfPopupLayout allows you to set a localized text for the following static words:

* Title
* ACCEPT
* DECLINE
* Popup_message

The following steps explains how to apply the localization for the above texts in our SfDataGrid.

* Add a resx file
* Querying the language which is set in the device
* Implement the interface

## Add a resx file

In PCL application, Needs to add a required `resx` files in the Resources folder with Build Action should be as EmbeddedResource. Also, File name should contains culture code.    

Example:
Culture   = French
File Name = fr-FR.resx

N> `resx` file should contain control full name like below image, Ex: Syncfusion.SfPopupLayout.XForms.fr.resx.

![](GettingStarted_images/LocalizationResxFile.png)

After that needs to Initializes a new instance of the `ResourceManager` class that looks up resources with the specified root name in the given assembly.

{% tabs %}
{% highlight c# %}

SfPopupLayoutResourceManger.Manager = new ResourceManager(ResXPath,Assembly);

//ResXPath => Full path of the resx file

//Assembly => Application assembly (PCL) 

{% endhighlight %}
{% endtabs %}

## Querying the language which is set in the device

1. Query the language which is set in the device using platform specific code. The result will be in platform specific format.
2. Convert this platform specific format to a .NET format and set it to `Thread.CurrentThread.CurrentUICulture`.

For Android and iOS, It is mandatory to implement the above steps. For UWP, It is not mandatory to implement the above items, Since the resources automatically recognises the selected language on UWP. However, If you wants to set language specific to the application irrespective of the selected language in the device, Can set it using `CultureInfo.CurrentUICulture` in UWP platform specific project.

{% tabs %}
{% highlight c# %}
  
  // In PCL project of MainPage.xaml.cs file
 if (Device.RuntimePlatform == Device.iOS || Device.RuntimePlatform == Device.Android)
            {
                DependencyService.Get<ILocalize>().SetLocale(new CultureInfo("fr-FR"));
            }

  // In UWP project project of MainPage.xaml.cs file
        CultureInfo.CurrentUICulture = new CultureInfo("fr-FR");

{% endhighlight %}
{% endtabs %}

## Implement the interface

To get the localized text from added `resx` file needs to implement the interface from PCL to Android and IOS renderer project like below code example.

{% tabs %}
{% highlight c# %}

 // In PCL Application add a ILocalize interface

  public interface ILocalize
    {
        CultureInfo GetCurrentCultureInfo();
        void SetLocale(CultureInfo ci);
    }
    public class PlatformCulture
    {
        public PlatformCulture(string platformCultureString)
        {
            if (String.IsNullOrEmpty(platformCultureString))
                throw new ArgumentException("Expected culture identifier", "platformCultureString"); // in C# 6 use nameof(platformCultureString)

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


{% tabs %}
{% highlight c# %}

// Implement the interface in Andeoid renderer project.

public class Localize : ILocalize

    {

        public void SetLocale(CultureInfo ci)
        {
            Thread.CurrentThread.CurrentCulture = ci;
            Thread.CurrentThread.CurrentUICulture = ci;
        }

        public CultureInfo GetCurrentCultureInfo()
        {
            var netLanguage = "en";
            var androidLocale = Java.Util.Locale.Default;
            netLanguage = AndroidToDotnetLanguage(androidLocale.ToString().Replace("_", "-"));

            // this gets called a lot - try/catch can be expensive so consider caching or something
            CultureInfo ci = null;
            try
            {
                ci = new CultureInfo(netLanguage);
            }
            catch
            {
                // iOS locale not valid .NET culture (eg. "en-ES" : English in Spain)
                // fallback to first characters, in this case "en"
                try
                {
                    var fallback = ToDotnetFallbackLanguage(new PlatformCulture(netLanguage));
                    ci = new CultureInfo(fallback);
                }
                catch
                {
                    // iOS language not valid .NET culture, falling back to English
                    ci = new CultureInfo("en");
                }
            }

            return ci;
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

  // Implement the interface in IOS renderer prject

   public class Localize : ILocalize
    {
        public void SetLocale(CultureInfo ci)
        {
            Thread.CurrentThread.CurrentCulture = ci;
            Thread.CurrentThread.CurrentUICulture = ci;
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
            CultureInfo ci = null;
            try
            {
                ci = new CultureInfo(netLanguage);
            }
            catch
            {
                // iOS locale not valid .NET culture (eg. "en-ES" : English in Spain)
                // fallback to first characters, in this case "en"
                try
                {
                    var fallback = ToDotnetFallbackLanguage(new PlatformCulture(netLanguage));
                    ci = new CultureInfo(fallback);
                }
                catch
                {
                    // iOS language not valid .NET culture, falling back to English
                    ci = new CultureInfo("en");
                }
            }

            return ci;
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

For UWP project need not to be implement the interface, Since the resources automatically recognises the selected language on UWP.

You can download the sample from [here]().