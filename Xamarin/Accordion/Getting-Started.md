---
layout: post
title: Getting started | SfAccordion | Xamarin | Syncfusion
description: This section described about getting started with Xamarin Forms Accordion (SfAccordion) control and more details.
platform: xamarin
control: SfAccordion
documentation: ug
---

# Getting Started with Xamarin Accordion (SfAccordion)

The Accordion control allows content to be organized in a vertically stacked list of items that is collapsible. Each item can also be expanded to reveal the content associated with that item. This section provides a quick overview for working with the `SfAccordion` for Xamarin.Forms.

## Assembly deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, {Syncfusion Essential Studio Installed location} \Essential Studio\16.x.x.x\Xamarin\lib

Eg: C:\Program Files (x86) \Syncfusion\Essential Studio\16.1.0.24\Xamarin\lib

N> Assemblies can be found in unzipped package location in Mac. 

## Adding SfAccordion reference 

You can add SfAccordion reference using one of the following methods: 

**Method 1: Adding SfAccordion reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfAccordion to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.Expander](https://www.nuget.org/packages/Syncfusion.Xamarin.Expander), and then install it. 

![Adding SfAccordion reference from NuGet](accordion_images/adding-sfaccordion-reference.png)

N> Install the same version of Expander NuGet in all the projects. 

**Method 2: Adding SfAccordion reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfAccordion control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox). 

**Method 3: Adding SfAccordion assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects. 

Location: {Installed location}/{version}/Xamarin/lib 

<table>
<tr>
<td>PCL</td>
<td>
Syncfusion.Expander.XForms.dll<br/>
Syncfusion.Core.XForms.dll<br/>
Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>
Syncfusion.Expander.XForms.dll<br/>
Syncfusion.Expander.XForms.Android.dll<br/>
Syncfusion.Core.XForms.dll<br/>
Syncfusion.Core.XForms.Android.dll<br/>
Syncfusion.Licensing.dll<br/>
</td>
</tr>
<tr>
<td>iOS</td>
<td>
Syncfusion.Expander.XForms.dll<br/>
Syncfusion.Expander.XForms.iOS.dll<br/>
Syncfusion.Core.XForms.dll<br/>
Syncfusion.Core.XForms.iOS.dll<br/>
Syncfusion.Licensing.dll<br/>
</td>
</tr>
<tr>
<td>UWP</td>
<td>
Syncfusion.Expander.XForms.dll<br/>
Syncfusion.Expander.XForms.UWP.dll<br/>
Syncfusion.Core.XForms.dll<br/>
Syncfusion.Core.XForms.UWP.dll<br/>
Syncfusion.Licensing.dll<br/>
</td>
</tr>
</table>

N> To learn more about obtaining Syncfusion components, refer to these links:  [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to learn about registering Syncfusion license key in your Xamarin application to use Syncfusion components.

## Launching the accordion on each platform

To use the accordion in an application, each platform application must initialize the accordion renderer. This initialization step varies from platform to platform and is discussed in the following sections:

### Android

The Android launches the accordion without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application.

N> If you are adding the references from toolbox, this step is not needed.

### iOS

To launch the accordion in iOS, call the `SfAccordionRenderer.Init()` in the `FinishedLaunching` overridden method of the AppDelegate class after the Xamarin.Forms Framework initialization and before the LoadApplication is called as explained in the following code example. 

{% tabs %}
{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    …
    global::Xamarin.Forms.Forms.Init ();
    Syncfusion.XForms.iOS.Accordion.SfAccordionRenderer.Init(); 
    LoadApplication (new App ());
    …
}
{% endhighlight %} 
{% endtabs %}

### Universal Windows Platform (UWP)

The UWP launches the accordion without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application. 

### ReleaseMode issue in UWP platform

The known Framework issue in UWP platform is that the custom controls will not render when deployed the application in `Release Mode`. 

The previous problem can be resolved by initializing the accordion assemblies in `App.xaml.cs` file in UWP project as in the following code snippet. 

{% tabs %}
{% highlight c# %}
// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
{
    …
    
    rootFrame.NavigationFailed += OnNavigationFailed;
        
    // you'll need to add `using System.Reflection;`
    List<Assembly> assembliesToInclude = new List<Assembly>();

    //Now, add all the assemblies your app uses 
	assembliesToInclude.Add(typeof(Syncfusion.XForms.UWP.Accordion.SfAccordionRenderer).GetTypeInfo().Assembly); 

    // replaces Xamarin.Forms.Forms.Init(e);        
    Xamarin.Forms.Forms.Init(e, assembliesToInclude);
        
    …     
}
{% endhighlight %}
{% endtabs %}

## Creating the accordion 

This section explains how to create a simple Xamarin.Forms application with [SfAccordion](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html). The control should be configured entirely in C# code or by using XAML markup. 

* Creating the project.
* Adding accordion to Xamarin.Forms. 
* Defining accordion items.

### Creating the project

Create a new blank (.NET Standard) application in Xamarin Studio or Visual Studio for Xamarin.Forms. 

### Adding accordion in Xamarin.Forms: 

To add the accordion to your application, follow these steps: 

1. Add required assemblies as discussed in assembly deployment section. 
2. Import the control namespace as `xmlns:accordion="clr-namespace:Syncfusion.XForms. Accordion;assembly=Syncfusion.Expander.XForms` in XAML Page. 
3. Create an instance of accordion control and add as content. 

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Accordion;assembly=Syncfusion.Expander.XForms">
             <ContentPage.Content> 
                <syncfusion:SfAccordion x:Name="accordion"/> 
             </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}

using Syncfusion.XForms.Accordion;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfAccordion accordion;
        public MainPage()
        {            
            InitializeComponent();
            accordion = new SfAccordion();
        }
    }
}

{% endhighlight %}
{% endtabs %}

### Defining accordion items 

`SfAccordion` is a layout control with vertically stacked list of accordion [Items](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html#Syncfusion_XForms_Accordion_SfAccordion_Items) that comprise of [Header](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.AccordionItem.html#Syncfusion_XForms_Accordion_AccordionItem_Header) and [Content](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.AccordionItem.html#Syncfusion_XForms_Accordion_AccordionItem_Content). You can load any View in Header and Content. Users can expand or collapse the Content view by tapping Header. 

Here, Grid is loaded in Header and Content of accordion items.

N> When loading Label as direct children of Header or Content of AccordionItem, then it will lead to exception in Forms 4.0 and above version. So, load Label inside Grid to overcome the crash.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Accordion;assembly=Syncfusion.Expander.XForms">
           <ContentPage.Content> 
                <syncfusion:SfAccordion Grid.Row="1"> 
                    <syncfusion:SfAccordion.Items> 
                        <syncfusion:AccordionItem> 
                            <syncfusion:AccordionItem.Header> 
                                <Grid>
                                    <Label TextColor="#495F6E" Text="Cheese burger" HeightRequest="50" VerticalTextAlignment="Center"/>
                                </Grid>
                            </syncfusion:AccordionItem.Header> 
                            <syncfusion:AccordionItem.Content> 
                                <Grid Padding="10,10,10,10" BackgroundColor="#FFFFFF"> 
                                    <Label TextColor="#303030" Text="Hamburger accompanied with melted cheese. The term itself is a portmanteau of the words cheese and hamburger. The cheese is usually sliced, then added a short time before the hamburger finishes cooking to allow it to melt." HeightRequest="50" VerticalTextAlignment="Center"/> 
                                </Grid> 
                            </syncfusion:AccordionItem.Content>     
                        </syncfusion:AccordionItem> 
                        <syncfusion:AccordionItem> 
                            <syncfusion:AccordionItem.Header> 
                                <Grid>
                                    <Label TextColor="#495F6E" Text="Veggie burger" HeightRequest="50" VerticalTextAlignment="Center"/>
                                </Grid> 
                            </syncfusion:AccordionItem.Header> 
                            <syncfusion:AccordionItem.Content> 
                                <Grid Padding="10,10,10,10" BackgroundColor="#FFFFFF"> 
                                    <Label TextColor="#303030" Text="Veggie burger, garden burger, or tofu burger uses a meat analogue, a meat substitute such as tofu, textured vegetable protein, seitan (wheat gluten), Quorn, beans, grains or an assortment of vegetables, which are ground up and formed into patties." HeightRequest="50" VerticalTextAlignment="Center"/> 
                                </Grid> 
                            </syncfusion:AccordionItem.Content> 
                        </syncfusion:AccordionItem> 
                        <syncfusion:AccordionItem> 
                            <syncfusion:AccordionItem.Header> 
                                <Grid>
                                    <Label TextColor="#495F6E" Text="Barbecue burger" HeightRequest="50" VerticalTextAlignment="Center"/> 
                                </Grid>
                            </syncfusion:AccordionItem.Header> 
                            <syncfusion:AccordionItem.Content> 
                                <Grid Padding="10,10,10,10" BackgroundColor="#FFFFFF"> 
                                    <Label TextColor="#303030" Text="Prepared with ground beef, mixed with onions and barbecue sauce, and then grilled. Once the meat has been turned once, barbecue sauce is spread on top and grilled until the sauce caramelizes." HeightRequest="50" VerticalTextAlignment="Center"/> 
                                </Grid> 
                            </syncfusion:AccordionItem.Content> 
                        </syncfusion:AccordionItem> 
                        <syncfusion:AccordionItem> 
                            <syncfusion:AccordionItem.Header> 
                                <Grid>
                                    <Label TextColor="#495F6E" Text="Chili burger" HeightRequest="50" VerticalTextAlignment="Center"/> 
                                </Grid>
                            </syncfusion:AccordionItem.Header> 
                            <syncfusion:AccordionItem.Content> 
                                <Grid Padding="10,10,10,10" BackgroundColor="#FFFFFF"> 
                                    <Label TextColor="#303030" Text="Consists of a hamburger, with the patty topped with chili con carne." HeightRequest="50" VerticalTextAlignment="Center"/> 
                                </Grid> 
                            </syncfusion:AccordionItem.Content> 
                        </syncfusion:AccordionItem> 
                    </syncfusion:SfAccordion.Items> 
                </syncfusion:SfAccordion> 
            </ContentPage.Content>    
</ContentPage>

{% endhighlight %}
{% highlight c# %}
public MainPageCS()
{
    InitializeAccordionItems();
    this.Content = Accordion;
}

private void InitializeAccordionItems()
{
	Accordion = new SfAccordion();
    Accordion.Items.Add(GenerateInvoiceHeaderAccordion());
    Accordion.Items.Add(GenerateInvoiceItemsAccordion());
    Accordion.Items.Add(GeneratePaymentDetailsAccordion());
}

private AccordionItem GenerateInvoiceHeaderAccordion()
{
	var item = new AccordionItem();
    var headerGrid = new Grid() { Padding = new Thickness(10, 0, 0, 10) };
    var headerLabel = new Label() { TextColor = Color.FromHex("#495F6E"), Text = "Invoice Date", HeightRequest = 50, VerticalTextAlignment = TextAlignment.Center };
    headerGrid.Children.Add(headerLabel);

    var contentGrid = new Grid() { Padding = new Thickness(10, 0, 0, 10), BackgroundColor = Color.FromHex("#FFFFFF") };
    var contentLabel = new Label() { TextColor = Color.FromHex("#303030"), Text = "11.03 AM, 15 January 2019", HeightRequest = 50, VerticalTextAlignment = TextAlignment.Center };
    contentGrid.Children.Add(contentLabel);

    item.Header = headerGrid;
    item.Content = contentGrid;
    return item;
}

private AccordionItem GenerateInvoiceItemsAccordion()
{
	var item = new AccordionItem();
    var headerGrid = new Grid() { Padding = new Thickness(10, 0, 10, 10) };
    var headerLabel = new Label() { TextColor = Color.FromHex("#495F6E"), Text = "Item (s)", HeightRequest = 50, VerticalTextAlignment = TextAlignment.Center };
    headerGrid.Children.Add(headerLabel);

    var contentGrid = new Grid() { Padding = new Thickness(10, 0, 10, 10), BackgroundColor = Color.FromHex("#FFFFFF") };
    contentGrid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Auto) });
    contentGrid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Auto) });
    contentGrid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Auto) });
    contentGrid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Auto) });
    contentGrid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Auto) });

    contentGrid.ColumnDefinitions.Add(new ColumnDefinition() { Width = new GridLength(1, GridUnitType.Star) });
    contentGrid.ColumnDefinitions.Add(new ColumnDefinition() { Width = new GridLength(1, GridUnitType.Star) });

    var contentLabel0 = new Label() { TextColor = Color.FromHex("#303030"), Text = "2018 Subaru Outback" };
	var contentLabel2 = new Label() { TextColor = Color.FromHex("#303030"), Text = "Door Edge Guard Kit" };
    var contentLabel1 = new Label() { TextColor = Color.FromHex("#303030"), Text = "All-Weather Mats" };
    var contentLabel3 = new Label() { TextColor = Color.FromHex("#303030"), Text = "Rear Bumper Cover" };
    var contentLabel4 = new Label() { TextColor = Color.FromHex("#303030"), Text = "Total Amount Paid", FontAttributes = FontAttributes.Bold };
    var contentLabel5 = new Label() { TextColor = Color.FromHex("#303030"), Text = "$35,705.00", HorizontalTextAlignment = TextAlignment.End };
    var contentLabel6 = new Label() { TextColor = Color.FromHex("#303030"), Text = "$105.00", HorizontalTextAlignment = TextAlignment.End };
    var contentLabel7 = new Label() { TextColor = Color.FromHex("#303030"), Text = "$100.00", HorizontalTextAlignment = TextAlignment.End };
    var contentLabel8 = new Label() { TextColor = Color.FromHex("#303030"), Text = "$95.00", HorizontalTextAlignment = TextAlignment.End };
    var contentLabel9 = new Label() { TextColor = Color.FromHex("#303030"), Text = "$36,000.00", HorizontalTextAlignment = TextAlignment.End, FontAttributes = FontAttributes.Bold };

    contentGrid.Children.Add(contentLabel0, 0, 0);
    contentGrid.Children.Add(contentLabel1, 0, 1);
    contentGrid.Children.Add(contentLabel2, 0, 2);
    contentGrid.Children.Add(contentLabel3, 0, 3);
    contentGrid.Children.Add(contentLabel4, 0, 4);
    contentGrid.Children.Add(contentLabel5, 1, 0);
    contentGrid.Children.Add(contentLabel6, 1, 1);
    contentGrid.Children.Add(contentLabel7, 2, 1);
    contentGrid.Children.Add(contentLabel8, 3, 1);
    contentGrid.Children.Add(contentLabel9, 4, 1);

    item.Header = headerGrid;
    item.Content = contentGrid;
    return item;
}

private AccordionItem GeneratePaymentDetailsAccordion()
{
	var item = new AccordionItem();
    var headerGrid = new Grid() { Padding = new Thickness(10, 0, 10, 10) };
    var headerLabel = new Label() { TextColor = Color.FromHex("#495F6E"), Text = "Payment Details", HeightRequest = 50, VerticalTextAlignment = TextAlignment.Center };
    headerGrid.Children.Add(headerLabel);

    var contentGrid = new Grid() { Padding = new Thickness(10, 0, 10, 10), BackgroundColor = Color.FromHex("#FFFFFF") };
    contentGrid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Auto) });
    contentGrid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Auto) });
    contentGrid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Auto) });

    contentGrid.ColumnDefinitions.Add(new ColumnDefinition() { Width = new GridLength(1, GridUnitType.Star) });
    contentGrid.ColumnDefinitions.Add(new ColumnDefinition() { Width = new GridLength(1, GridUnitType.Star) });

    var contentLabel0 = new Label() { TextColor = Color.FromHex("#303030"), Text = "Card Payment" };
    var contentLabel1 = new Label() { TextColor = Color.FromHex("#303030"), Text = "Third-Party coupons" };
    var contentLabel2 = new Label() { TextColor = Color.FromHex("#303030"), Text = "Total Amount Paid", FontAttributes = FontAttributes.Bold };
    var contentLabel3 = new Label() { TextColor = Color.FromHex("#303030"), Text = "$31,000.00", HorizontalTextAlignment = TextAlignment.End };
    var contentLabel4 = new Label() { TextColor = Color.FromHex("#303030"), Text = "$5,000.00", HorizontalTextAlignment = TextAlignment.End };
    var contentLabel5 = new Label() { TextColor = Color.FromHex("#303030"), Text = "$36,000.00", HorizontalTextAlignment = TextAlignment.End, FontAttributes = FontAttributes.Bold };


    contentGrid.Children.Add(contentLabel0, 0, 0);
    contentGrid.Children.Add(contentLabel1, 0, 1);
    contentGrid.Children.Add(contentLabel2, 0, 2);
    contentGrid.Children.Add(contentLabel3, 1, 0);
    contentGrid.Children.Add(contentLabel4, 1, 1);
    contentGrid.Children.Add(contentLabel5, 1, 2);

    item.Header = headerGrid;
    item.Content = contentGrid;
    return item;
}
{% endhighlight %}
{% endtabs %}

Now, run the application to render the following output.

![Xamarin Forms Accordion](accordion_images/xamarin-forms-accordion.png)

You can download accordion sample for Xamarin.Forms here [AccordionGettingStarted](https://github.com/SyncfusionExamples/xamarin_accordion_getting_started).

N> When adding the template control inside the `StackLayout` or `Grid` with the height as `Auto`, the child element will not get the height at run time changes. Since the `SfAccordion` is entirely a template based control, we cannot determine the default height value to the control. So it is recommended to provide the `HorizontalOptions` and `VerticalOptions` as `FillAndExpand` options for the control.

## Animation duration

`SfAccordion` allows you to customize the expanding and collapsing of accordion item by using the [AnimationDuration](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html#Syncfusion_XForms_Accordion_SfAccordion_AnimationDuration) property. By default, the animation duration is 250 milliseconds. 

{% tabs %}
{% highlight xaml %}
    <syncfusion:SfAccordion x:Name="accordion" AnimationDuration="150" /> 
{% endhighlight %}
{% highlight c# %}
    accordion.AnimationDuration = 150;
{% endhighlight %}
{% endtabs %}

## Animation easing

`SfAccordion` allows you to customize the rate of change of parameter over time or animation style of accordion item by using the [AnimationEasing](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html#Syncfusion_XForms_Accordion_SfAccordion_AnimationEasing) property. By default, the animation easing is `Linear`.  

{% tabs %}
{% highlight xaml %}
         <syncfusion:SfAccordion x:Name="accordion" AnimationEasing="SinOut" />        
{% endhighlight %}
{% highlight c# %}
    accordion.AnimationEasing = Syncfusion.XForms.Expander.AnimationEasing.SinOut;
{% endhighlight %}
{% endtabs %}

## Auto scroll position

`SfAccordion` allows you to customize the scroll position of the expanded accordion item by using the [AutoScrollPosition](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html#Syncfusion_XForms_Accordion_SfAccordion_AutoScrollPosition) property. By default, the auto scroll position is `MakeVisible`.  

{% tabs %}
{% highlight xaml %}
    <syncfusion:SfAccordion x:Name="accordion" AutoScrollPosition="Top"/>    
{% endhighlight %}
{% highlight c# %}
    accordion.AutoScrollPosition = Syncfusion.XForms.Accordion.AutoScrollPosition.Top;
{% endhighlight %}
{% endtabs %}

## Expand mode

`SfAccordion` allows you to expand single or multiple items by using the [ExpandMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html#Syncfusion_XForms_Accordion_SfAccordion_ExpandMode) property. By default, the expand mode is `Single`.  

{% tabs %}
{% highlight xaml %}
    <syncfusion:SfAccordion x:Name="accordion" ExpandMode="Multiple" />         
{% endhighlight %}
{% highlight c# %}
    accordion.ExpandMode = Syncfusion.XForms.Accordion.ExpandMode.Multiple;
{% endhighlight %}
{% endtabs %}

## Item spacing

`SfAccordion` allows you to customize the vertical spacing between the accordion items by using the [ItemSpacing](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Accordion.SfAccordion.html#Syncfusion_XForms_Accordion_SfAccordion_ItemSpacing) property. The default value is `6.0d`. 

{% tabs %}
{% highlight xaml %}
    <syncfusion:SfAccordion x:Name="accordion" ItemSpacing="8.0d" />        
{% endhighlight %}
{% highlight c# %}
    accordion.ItemSpacing = 8.0d;
{% endhighlight %}
{% endtabs %}

## See also

[How to resolve SfAccordion not rendering issue in iOS and UWP](https://www.syncfusion.com/kb/11294)                                                                                                                                                                            
[How to show WebView in Xamarin.Forms Accordion (SfAccordion)](https://www.syncfusion.com/kb/11373)                                                                                                                                                         
[How to bind command in Xamarin.Forms Accordion (SfAccordion)](https://www.syncfusion.com/kb/11359/)                                                                                                                                    
[How to show or hide AccordionItem in Xamarin.Forms (SfAccordion)](https://www.syncfusion.com/kb/11383/)                                                                                                                                                                                                            
[How to retrieve the expanding Accordion item index in Xamarin.Forms (SfAccordion)](https://www.syncfusion.com/kb/11358/)
[How to expand or collapse Accordion programmatically in Xamarin.Forms (SfAccordion)](https://www.syncfusion.com/kb/11314/)                                                                                                                                                                                                                                                                 
[How to access a named Accordion inside a XAML DataTemplate in Xamarin.Forms (SfAccordion)](https://www.syncfusion.com/kb/11375/)                                                                                                                                                               
[How to overcome the crash Java.Lang.NullPointerException in Xamarin.Forms Accordion (SfAccordion)](https://www.syncfusion.com/kb/11432/)                                                                                                                                                                                           
[How to work with Accordion using C# in Xamarin.Forms (SfAccordion)](https://www.syncfusion.com/kb/11437/)                                                                                                                                                                                                                  
