---
layout: post
title: Getting Started for Essential Syncfusion.Xamarin.Forms Cards
description: How to create a SfCardView, SfCardLayout and add contents in SfCardView and SfCardLayout.
platform: xamarin
control: Cards
documentation: ug
---

# Getting Started

This section explains you the steps required to add content in SfCardView with indicator and adding SfCardView in SCardLayout. This section covers only the minimal features that you need to know to get started with the Cards.

## Adding Cards reference

You can add Cards reference using one of the following methods:

**Method 1: Adding Cards reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add cards to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.Cards](https://www.nuget.org/packages/Syncfusion.Xamarin.Cards/), and then install it.

![Adding Xamarin.Forms Cards reference](getting-started_images/img3.png)

N> Install the same version of the cards NuGet in all the projects.

**Method 2: Adding Cards reference from toolbox**

Syncfusion provides Xamarin Toolbox. Using this toolbox, you can drag the SfCardView and SfCardLayout to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding Cards assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location : {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>
PCL
</td>
<td>
Syncfusion.Cards.XForms.dll<br/>
Syncfusion.Core.XForms.dll<br/>
Syncfusion.Licensing.dll<br/>
</td>
</tr>
<tr>
<td>
Android
</td>
<td>
Syncfusion.Cards.XForms.Android.dll<br/>
Syncfusion.Cards.XForms.dll<br/>
Syncfusion.Core.XForms.dll<br/>
Syncfusion.Core.XForms.Android.dll<br/>
Syncfusion.Licensing.dll<br/>
</td>
</tr>
<tr>
<td>
iOS
</td>
<td>
Syncfusion.Cards.XForms.iOS.dll<br/>
Syncfusion.Cards.XForms.dll<br/>
Syncfusion.Core.XForms.dll<br/>
Syncfusion.Core.XForms.iOS.dll<br/>
Syncfusion.Licensing.dll<br/>
</td>
</tr>
<tr>
<td>
UWP
</td>
<td>
Syncfusion.Cards.XForms.UWP.dll<br/>
Syncfusion.Cards.XForms.dll<br/>
Syncfusion.Core.XForms.dll<br/>
Syncfusion.Core.XForms.UWP.dll<br/>
Syncfusion.Licensing.dll<br/>
</td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Launching the application on each platform with cards

To use the cards inside an application, each platform application requires some additional configurations. The configurations vary from platform to platform and is discussed in the following sections:

### iOS

To launch the cards in iOS, call the SfCardViewRenderer.Init() method in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms framework initialization and before the LoadApplication method is called as demonstrated in the following code sample:

N> If you are adding the references from toolbox, this step is not needed.

{% highlight C# %} 

    public override bool FinishedLaunching(UIApplication app, NSDictionary options) 
    { 
        … 
        global::Xamarin.Forms.Forms.Init();
        Syncfusion.XForms.iOS.Cards.SfCardViewRenderer.Init();
        LoadApplication(new App()); 
        …
    }

{% endhighlight %}

### Universal Windows Platform (UWP)

To deploy the cards in `Release` mode, you need to initialize the cards assemblies in App.xaml.cs in UWP project as shown in the below code snippets.

{% highlight C# %} 

    // In App.xaml.cs 
    protected override void OnLaunched(LaunchActivatedEventArgs e)
    { 
    … 
        if (rootFrame == null) 
        { 
            List<Assembly> assembliesToInclude = new List<Assembly>();
            assembliesToInclude.Add(typeof(Syncfusion.XForms.UWP.Cards.SfCardViewRenderer).GetTypeInfo().Assembly);
            Xamarin.Forms.Forms.Init(e, assembliesToInclude);
        } 
    … 
    }

{% endhighlight %}

### Android

The Android platform does not require any additional configuration to render the cards.


## Initialize Cards

Import the [`Cards`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.Cards.XForms.SfCardView.html) namespace as shown below in your respective Page,

{% tabs %} 

{% highlight xaml %} 

    xmlns:cards="clr-namespace:Syncfusion.XForms.Cards;assembly=Syncfusion.Cards.XForms" 

{% endhighlight %}

{% highlight C# %} 

    using Syncfusion.Cards.XForms;

{% endhighlight %}

{% endtabs %} 

### SfCardView

Initialize an card view with [`Content`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.Cards.XForms.Cards~Content.html) as shown below,

{% tabs %} 

{% highlight xaml %} 

    <cards:SfCardView>

         <Label  Text="SfCardView"/>

    </cards:SfCardView>

{% endhighlight %}

{% highlight C# %} 

    SfCardView cardView = new SfCardView();

     //set Content for card view
    cardView.Content = new Label(){ Text="SfCardView" };

    this.Content = cardView;

{% endhighlight %}

{% endtabs %} 

Run the project and check if you get following output to make sure you have configured your project properly to add [`Cards`.](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.Cards.XForms.SfCardLayout.html)

![Initializing Xamarin.Forms SfCardView](getting-started_images/img1.png)

## Indicator customization

Indicator can be added in any direction which can be used to denote the state based on the content of the [`SfCardView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.Cards.XForms.Cards~SfCardView.html).

{% tabs %} 

{% highlight xaml %}

    <cards:SfCardView x:Name="cardView" IndicatorColor="Cyan" IndicatorThickness="12" IndicatorPosition="Left" />

{% endhighlight %}

{% highlight C# %}

    SfCardView cardView = new SfCardView();
    cardView.IndicatorThickness = 12;
    cardView.IndicatorPosition = IndicatorPosition.Left;
    cardView.IndicatorColor = Color.Cyan;

{% endhighlight %}

{% endtabs %}

Refer this [link](https://help.syncfusion.com/xamarin/cards/indicator) to learn more about the options available in [`Cards`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.Cards.XForms.SfCardView.html) to customize indicator.

## SwipeToDismiss

[`SwipeToDismiss`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.Cards.XForms.Cards~SwipeToDismiss.html) is used to enable or disable swiping in SfCardView.

{% tabs %} 

{% highlight xaml %}

    <cards:SfCardView x:Name="cardView" SwipeToDismiss="true"/>

{% endhighlight %}

{% highlight C# %}

    SfCardView cardView = new SfCardView();
    cardView.SwipeToDismiss = true;

{% endhighlight %}

{% endtabs %}

![SwipeToDismiss in Xamarin.Forms SfCardView](getting-started_images/cardview.gif)

### SfCardLayout

Initialize an card layout with card view as shown below,

{% tabs %} 

{% highlight xaml %} 

    <cards:SfCardLayout x:Name="cardLayout" SwipeDirection="Left" HeightRequest="500" BackgroundColor="#F0F0F0">

        <cards:SfCardView>
          <Label  Text="Cyan" BackgroundColor="Cyan"/>
        </cards:SfCardView>

        <cards:SfCardView>
            <Label  Text="Yellow" BackgroundColor="Yellow"/>
        </cards:SfCardView>

        <cards:SfCardView>
            <Label  Text="Orange" BackgroundColor="Orange"/>
        </cards:SfCardView>  

    </cards:SfCardLayout>

{% endhighlight %}

{% highlight C# %} 

    SfCardLayout cardLayout = new SfCardLayout();

    //Add children for card layout 
    cardLayout.Children.Add(new SfCardView(){Content = new Label(){ Text="Cyan", BackgroundColor=Color.Cyan }});

    cardLayout.Children.Add(new SfCardView(){Content = new Label(){ Text="Yellow", BackgroundColor=Color.Yellow }});

    cardLayout.Children.Add(new SfCardView(){Content = new Label(){ Text="Orange", BackgroundColor=Color.Orange }});

    this.Content = cardLayout;

{% endhighlight %}

{% endtabs %} 

![Initializing Xamarin.Forms SfCardLayout](getting-started_images/layout.gif)

