# Download and Installation

## Install from Xamarin Component Store

Refer [this](https://developer.xamarin.com/guides/cross-platform/application_fundamentals/components_walkthrough/# "") article to know about how to add a Xamarin Component Store component to Xamarin.Forms application.

## Install from nuget

Refer [this](http://help.syncfusion.com/extension/syncfusion-nuget-packages/overview# "") document to know about how to add Syncfusion assemblies through nuget package.

## Download directly from Website

You can also download the complete Xamarin.Forms component from [here](http://www.syncfusion.com/products/xamarin# ""). You will be asked to choose the file to download whether windows installer or zip file.

**Windows** **Installer** **(****exe****)**

The following procedure illustrates how to install the installer of Syncfusion Xamarin components in Windows.

1. Double-click the Syncfusion Essential Studio for Xamarin Setup file. The Self-Extractor wizard opens and extracts the package automatically.
2. Enter User Name, Organization and Unlock Key in the corresponding text boxes provided.
3. Click Next.
4. After reading the terms, click the “I accept the terms and conditions” check box.
5. Click Next and choose the installation location and samples installation.
6. To install it in the displayed default location, click Install.
7. Click Finish. The library and samples locations will be launched automatically.
## Exploring the package


You will find the following folders when extract the downloaded zip package or from the installed location in Windows

* **Lib** – Contains Syncfusion assemblies for Xamarin.Forms, Xamarin.Android and Xamarin.iOS.
* **Samples** - Contains demo samples for Xamarin.Forms, Xamarin.Android and Xamarin.iOS.
## Add reference to the project


You can then add the assembly references to the respective projects; following is the location where you can locate dll for Chart control, you can find assemblies for the other controls also from the same location.

**PCL** **project**

pcl\Syncfusion.SfChart.XForm.dll

**Android** **project**

android\Syncfusion.SfChart.Andriod.dll

android\Syncfusion.SfChart.XForms.Andriod.dll

android\Syncfusion.SfChart.XForm.dll

**iOS****(****Classic****)** **project**

ios\Syncfusion.SfChart.iOS.dll

ios\Syncfusion.SfChart.XForms.iOS.dll

ios\Syncfusion.SfChart.XForm.dll

**iOS****(****Unified****)** **project**

ios-unified\Syncfusion.SfChart.iOS.dll

ios-unified\Syncfusion.SfChart.XForms.iOS.dll

ios-unified\Syncfusion.SfChart.XForm.dll

**Windows** **Phone** **project**

wp8\Syncfusion.SfChart.WP8.dll

wp8\Syncfusion.SfChart.XForms.WinPhone.dll

wp8\Syncfusion.SfChart.XForm.dll

**Windows** **Phone** **8****.****1** **project**

wp81\Syncfusion.SfChart.WP.dll

wp81\Syncfusion.SfChart.XForms.WinPhone.dll

wp81\Syncfusion.SfChart.XForm.dll

**WinRT** **project**

winrt\Syncfusion.SfChart.WinRT.dll

winrt\Syncfusion.SfChart.XForms.WinRT.dll

winrt\Syncfusion.SfChart.XForm.dll

After you have added assemblies to the respective projects, you have to follow an additional step for loading our components in Windows Phone, WinRT and iOS projects. 

Following is an example for Chart component; create an instance of SfChartRenderer in MainPage constructor of the Windows Phone and WinRT project as shown below.

{% highlight C# %}

public MainPage() 
{
     new SfChartRenderer();
     ...
}

{% endhighlight %}

Create an instance of SfChartRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% highlight C# %} 

public override bool FinishedLaunching(UIApplication app, NSDictionary options) 
{
   ... 
   new SfChartRenderer (); 
   ... 
}

{% endhighlight %}

N> If you don’t add the above line, our controls will not be loaded in WP, WinRT and iOS platforms, and it will be looking blank.