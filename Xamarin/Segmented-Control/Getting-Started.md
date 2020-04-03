---
layout: post
title: Getting Started with Syncfusion segmented control for Xamarin.Forms 
description: A quick tour for the initial users of Xamarin.Forms SegmentedControl to find a way to create and populate a data source. 
platform: Xamarin
control: SfSegmentedControl
documentation: ug
---

# Getting Started Xamarin.Forms SegmentedControl (SfSegmentedControl)

This section provides an overview for working with the segmented control for Xamarin.Forms. Walk through the entire process of creating a real-world application with the SfSegmentedControl.

## Assembly deployment

After installing the Essential Studio for Xamarin, find all the required assemblies in installation folders, {Syncfusion Essential Studio Installed location}\Essential Studio\16.2.0.41\Xamarin\lib}.

E.g., C:\Program Files (x86)\Syncfusion\Essential Studio\16.2.0.41\Xamarin\lib

N> Assemblies can be found in an unzipped package location in Mac.

## Adding SfSegmentedControl reference

You can add SfSegmentedControl reference using one of the following methods:

**Method 1: Adding SfSegmentedControl reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfSegmentedControl to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.Buttons](https://www.nuget.org/packages/Syncfusion.Xamarin.Buttons), and then install it.

![Adding SfSegmentedControl reference from NuGet](images/getting-started/Adding SfSegmentedControl reference.png)

N> 
* Install the same version of SfSegmentedControl NuGet in all the projects.
* In addition, you need to install the [Syncfusion.Xamarin.Buttons.WPF]() package for Xamarin.Forms WPF platform only.

**Method 2: Adding SfSegmentedControl reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfSegmentedControl control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfSegmentedControl assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.Buttons.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.Buttons.XForms.dll<br/>Syncfusion.Buttons.XForms.Android.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.Buttons.XForms.dll<br/>Syncfusion.Buttons.XForms.iOS.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.Buttons.XForms.dll<br/>Syncfusion.Buttons.XForms.UWP.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>WPF</td>
<td>Syncfusion.Buttons.XForms.dll<br/>Syncfusion.Buttons.XForms.WPF.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.WPF.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To learn more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to learn about registering Syncfusion license key in your Xamarin application to use our components.

## Launching the SfSegmentedControl on each platform

To use the segmented control inside an application, each platform application must initialize the segmented control renderer. This initialization steps vary from platform to platform, and it is discussed in the following sections:

### Android and UWP

The Android and UWP launches the SfSegmentedControl without any initialization, and it is enough to only initialize the Xamarin.Forms Framework to launch the application.

N> If you are adding the references from toolbox, this step is not needed.

### iOS

To launch the segmented control in iOS, call the SfSegmentedControlRenderer.Init() in the `FinishedLaunching` overridden method of the `AppDelegate` class after the Xamarin.Forms Framework has been initialized and before the `LoadApplication` is called, as demonstrated in the following code example.

{% highlight C# %}

    public override bool FinishedLaunching(UIApplication app, NSDictionary options)
    {
         …            
         global::Xamarin.Forms.Forms.Init ();   
         Syncfusion.XForms.iOS.Buttons.SfSegmentedControlRenderer.Init();  
         LoadApplication (new App ());   
         …   
    }
	

{% endhighlight %}


### ReleaseMode issue in UWP platform

There is a known Framework issue in UWP platform. The custom controls will not render when deployed the application in `Release Mode`.

The above problem can be resolved by initializing the SfSegmentedControl assemblies in `App.xaml.cs` in UWP project as in the following code snippet.

{% highlight C# %}

// In App.xaml.cs

    protected override void OnLaunched(LaunchActivatedEventArgs e)
    {
        …
    	    rootFrame.NavigationFailed += OnNavigationFailed;
    
        // you'll need to add `using System.Reflection;
        List<Assembly> assembliesToInclude = new List<Assembly>();
    
        //Now, add all the assemblies your app uses                 
        assembliesToInclude.Add(typeof(Syncfusion.XForms.UWP.Buttons.SfSegmentedControlRenderer).GetTypeInfo().Assembly);
    
        // replaces Xamarin.Forms.Forms.Init(e);        
        Xamarin.Forms.Forms.Init(e, assembliesToInclude);	
        …     
    }

{% endhighlight %}

### Additional step for WPF

To launch the segmented control in WPF, call the SfSegmentedControlRenderer.Init() method in the MainWindow constructor of the MainWindow class after the Xamarin.Forms framework has been initialized and before the LoadApplication method is called as demonstrated in the following code sample.

{% highlight C# %} 

public partial class MainWindow : FormsApplicationPage
{
     public MainWindow()
     { 
            InitializeComponent();
            
            Forms.Init();
            
            Syncfusion.XForms.WPF.Buttons.SfSegmentedControlRenderer.Init();
            
            LoadApplication(new App());
     }
}

{% endhighlight %}


## Creating an application with segmented control.

This section explains how to create a bus ticket booking module by using syncfusion segmented control. The control can be configured entirely in C# code or by using XAML markup. The following screenshot illustrates the output of Segmented control on iOS, Android and UWP devices.

![OverView image of SegmentedControl](images/getting-started/Xamarin_forms_gettingstarted.png)

## Creating a project

Create a new BlankApp (Xamarin.Forms.Portable) application in Visual Studio for Xamarin.Forms.

### Adding SfSegmentedControl in Xamarin.Forms

Add the required assembly references to the PCL and renderer projects as discussed in the Assembly deployment  [section](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfsegmentedcontrol).

Import the control namespace as shown in the following code.

{% tabs %}

{% highlight xaml %}

    xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
	
{% endhighlight %}

{% highlight C# %}

    using Syncfusion.XForms.Buttons;

{% endhighlight %}

{% endtabs %}

Set the control to content in `ContentPage`.

{% tabs %}

{% highlight xaml %}

    <? xml version="1.0" encoding="utf-8" ?>
    <ContentPage xmlns = "http://xamarin.com/schemas/2014/forms"
    
        xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    	xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
    	x:Class="GettingStarted.MainPage">
        <ContentPage.Content>
            <buttons:SfSegmentedControl  />
        </ContentPage.Content>
    </ContentPage>  

{% endhighlight %}

{% highlight c# %}

    using Syncfusion.XForms.Buttons;
    using Xamarin.Forms;
    
    namespace GettingStarted
    {
        public partial class MainPage : ContentPage
        {
            private SfSegmentedControl segmentedControl;
            public MainPage()
            {
                InitializeComponent();
                segmentedControl = new SfSegmentedControl();
                this.Content = segmentedControl;
            }
        }
    }   

{% endhighlight %}

{% endtabs %}

### Adding supportive views to the application
 
For the completeness of the ticket booking application, few framework controls are added to the application to get the data from the user.

ViewModel class for the Entry, which we have used in our View.

{% tabs %}

{% highlight c# %}

    using Syncfusion.XForms.Buttons;
    using System;
    using System.Collections.ObjectModel;
    using System.ComponentModel;
    using System.Runtime.CompilerServices;
    using Xamarin.Forms;
    
    namespace SegmentGettingStarted
    {
        class ViewModel : INotifyPropertyChanged
        {
            private string fromText="";
            public string FromText
            {
                get { return fromText; }
                set { fromText = value; NotifyPropertyChanged("FromText"); }
            }
            private string toText = "";
            public string ToText
            {
                get { return toText; }
                set { toText = value; NotifyPropertyChanged("ToText"); }
            }
            public ViewModel()
            {
            }
            public event PropertyChangedEventHandler PropertyChanged;
    
            private void NotifyPropertyChanged([CallerMemberName] String propertyName = "")
            {
                if (PropertyChanged != null)
                {
                    PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
                }
            }
        }
    }

{% endhighlight %}

{% endtabs %}

View can be created by the following code snippet.

{% tabs %}

{% highlight xaml %}

    <? xml version="1.0" encoding="utf-8" ?>
    <ContentPage xmlns = "http://xamarin.com/schemas/2014/forms"
                xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
                xmlns:local="clr-namespace:SegmentGettingStarted"
                xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
                xmlns:segmentCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
                x:Class="SegmentGettingStarted.MainPage">
    <ContentPage.BindingContext>
        <local:ViewModel x:Name="viewModel" />
    </ContentPage.BindingContext>
    <StackLayout
        HorizontalOptions = "Center"
        VerticalOptions="Center"
        Padding="20,0,20,0">
         <Label
            Text="Bus Ticket Booking"
            FontSize="Large"
            FontAttributes="Bold"
            HeightRequest="50"
            HorizontalOptions="Center"
            VerticalOptions="Center"/>
        <Entry
            Placeholder="From"
            Text="{Binding FromText,Mode=TwoWay}"
            HeightRequest="50"
            Margin="0,10,0,10"/>
        <Entry
            Placeholder="To"
            Text="{Binding ToText}"
            HeightRequest="50"
            Margin="0,10,0,10"/>
    </StackLayout>
    </ContentPage>

{% endhighlight %}

{% highlight C# %}

    using Syncfusion.XForms.Buttons;
    using System.Collections.Generic;
    using Xamarin.Forms;
    namespace SegmentGettingStarted
    {
        public partial class MainPage : ContentPage
        {
            StackLayout stack;
            ViewModel viewModel;
            Label headerLabel;
            Entry fromEntry, toEntry;
            public MainPage()
            {
                InitializeComponent();
                stack = new StackLayout();
                viewModel = new ViewModel();
                stack.HorizontalOptions = LayoutOptions.Center;
                stack.VerticalOptions = LayoutOptions.Center;
                stack.Padding = new Thickness(20, 0, 20, 0);
    
                //Label to denote the header part of application
                headerLabel = new Label();
                headerLabel.Text = "Bus Ticket Booking";
                headerLabel.FontAttributes = FontAttributes.Bold;
                headerLabel.HeightRequest = 50;
                headerLabel.FontSize = Device.GetNamedSize(NamedSize.Large, typeof(Label));
                headerLabel.HorizontalOptions = LayoutOptions.Center;
                headerLabel.VerticalOptions = LayoutOptions.Center;

                //Entry to enter the origin location
                fromEntry = new Entry();
                fromEntry.Placeholder = "From";
                fromEntry.Text = viewModel.FromText;
                fromEntry.HeightRequest = 50;
                fromEntry.Margin = new Thickness(0, 10, 0, 10);

                //Entry to enter the destination location
                toEntry = new Entry();
                toEntry.Placeholder = "To";
                toEntry.Text = viewModel.ToText;
                toEntry.HeightRequest = 50;
                toEntry.Margin = new Thickness(0, 10, 0, 10);
    
                stack.Children.Add(headerLabel);
                stack.Children.Add(fromEntry);
                stack.Children.Add(toEntry);
                this.Content = stack;
            }
        }
    }

{% endhighlight %}

{% endtabs %}


![Image for adding supportive Views](images/getting-started/Xamarin_Forms_InitialView.png)


## Adding data/Items to SfSegmentedControl

You can add the data inside the segmented control in three different ways: 

1. String data
2. SfSegmentItem
3. Custom View

Items inside the segmented control can be added using the `ItemsSource` property of `SfSegmentedControl`, which holds the collection/list of items.

### Adding data as a String

With the help of  Xamarin.Forms `System.Collections.Generic` you can add string data as `ItemsSource` to SfSegmentedControl.

{% highlight c# %}

    using Syncfusion.XForms.Buttons;
    using System;
    using System.Collections.ObjectModel;
    using System.ComponentModel;
    using System.Runtime.CompilerServices;
    using Xamarin.Forms;
    
    namespace SegmentGettingStarted
    {
        class ViewModel : INotifyPropertyChanged
        {
            private string fromText="";
            public string FromText
            {
                get { return fromText; }
                set { fromText = value; NotifyPropertyChanged("FromText"); }
            }
            private string toText = "";
            public string ToText
            {
                get { return toText; }
                set { toText = value; NotifyPropertyChanged("ToText"); }
            }
            public ViewModel()
            {
            }
            public event PropertyChangedEventHandler PropertyChanged;
    
            private void NotifyPropertyChanged([CallerMemberName] String propertyName = "")
            {
                if (PropertyChanged != null)
                {
                    PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
                }
            }
        }
    }

{% endhighlight %}

{% tabs %}

{% highlight xaml %}

    <? xml version="1.0" encoding="utf-8" ?>
    <ContentPage xmlns = "http://xamarin.com/schemas/2014/forms"
                xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
                xmlns:local="clr-namespace:SegmentGettingStarted"
                xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
                xmlns:segmentCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
                x:Class="SegmentGettingStarted.MainPage">
    <ContentPage.BindingContext>
        <local:ViewModel x:Name="viewModel" />
    </ContentPage.BindingContext>
    <StackLayout
        HorizontalOptions = "Center"
        VerticalOptions="Center"
        Padding="20,0,20,0">
         <Label
            Text="Bus Ticket Booking"
            FontSize="Large"
            FontAttributes="Bold"
            HeightRequest="50"
            HorizontalOptions="Center"
            VerticalOptions="Center"/>
        <Entry
            Placeholder="From"
            Text="{Binding FromText,Mode=TwoWay}"
            HeightRequest="50"
            Margin="0,10,0,10"/>
        <Entry
            Placeholder="To"
            Text="{Binding ToText}"
            HeightRequest="50"
            Margin="0,10,0,10"/>
        <buttons:SfSegmentedControl
            SelectionTextColor = "White"
            HeightRequest="80"
            VisibleSegmentsCount="6"
            Color="Transparent" 
            BorderColor="#929292"
            SelectedIndex="1"
            FontColor="#929292"
            BackgroundColor="Transparent" >
            <segmentCollection:List x:TypeArguments="x:String">
                <x:String>1</x:String>
                <x:String>2</x:String>
                <x:String>3</x:String>
                <x:String>4</x:String>
                <x:String>5</x:String>
                <x:String>6</x:String>
            </segmentCollection:List>
        </buttons:SfSegmentedControl>
    </StackLayout>
    </ContentPage>

{% endhighlight %}

{% highlight C# %}

    using Syncfusion.XForms.Buttons;
    using System.Collections.Generic;
    using Xamarin.Forms;
    namespace SegmentGettingStarted
    {
        public partial class MainPage : ContentPage
        {
            SfSegmentedControl segmentedControl;
            StackLayout stack;
            ViewModel viewModel;
            Label headerLabel;
            Entry fromEntry, toEntry;
            public MainPage()
            {
                InitializeComponent();
                stack = new StackLayout();
                viewModel = new ViewModel();
                stack.HorizontalOptions = LayoutOptions.Center;
                stack.VerticalOptions = LayoutOptions.Center;
                stack.Padding = new Thickness(20, 0, 20, 0);
    
                //Label to denote the header part of application
                headerLabel = new Label();
                headerLabel.Text = "Bus Ticket Booking";
                headerLabel.FontAttributes = FontAttributes.Bold;
                headerLabel.HeightRequest = 50;
                headerLabel.FontSize = Device.GetNamedSize(NamedSize.Large, typeof(Label));
                headerLabel.HorizontalOptions = LayoutOptions.Center;
                headerLabel.VerticalOptions = LayoutOptions.Center;

                //Entry to enter the origin location
                fromEntry = new Entry();
                fromEntry.Placeholder = "From";
                fromEntry.Text = viewModel.FromText;
                fromEntry.HeightRequest = 50;
                fromEntry.Margin = new Thickness(0, 10, 0, 10);

                //Entry to enter the destination location
                toEntry = new Entry();
                toEntry.Placeholder = "To";
                toEntry.Text = viewModel.ToText;
                toEntry.HeightRequest = 50;
                toEntry.Margin = new Thickness(0, 10, 0, 10);
    
                //Adding item to the SegmentedControl as String
                segmentedControl = new SfSegmentedControl();
                segmentedControl.SelectionTextColor = Color.White;
                segmentedControl.HeightRequest = 80;
                segmentedControl.Color = Color.Transparent;
                segmentedControl.BorderColor = Color.FromHex("#929292");
                segmentedControl.FontColor = Color.FromHex("#929292");
                segmentedControl.SelectedIndex = 1;
                segmentedControl.BackgroundColor = Color.Transparent;
                segmentedControl.VisibleSegmentsCount = 6;
                segmentedControl.DisplayMode = SegmentDisplayMode.Text;
                List<string> list = new List<string>
                {
                    "1","2","3","4","5","6"
                };
                segmentedControl.ItemsSource = list;
    
                stack.Children.Add(headerLabel);
                stack.Children.Add(fromEntry);
                stack.Children.Add(toEntry);
                stack.Children.Add(segmentedControl);
                this.Content = stack;
            }
        }
    }

{% endhighlight %}

{% endtabs %}


![Image for adding data as string](images/getting-started/Xamarin_Forms_String.png)

### Adding data as a SfSegmentItem

By using `SfSegmentItem` class, you can add data inside the segmented control.

In ViewModel, add the following code to get the respective items in SfSegmentedControl.

{% highlight C# %}

    using Syncfusion.XForms.Buttons;
    using System;
    using System.Collections.ObjectModel;
    using System.ComponentModel;
    using System.Runtime.CompilerServices;
    using Xamarin.Forms;
    
    namespace SegmentGettingStarted
    {
        class ViewModel : INotifyPropertyChanged
        {
            private string fromText="";
            public string FromText
            {
                get { return fromText; }
                set { fromText = value; NotifyPropertyChanged("FromText"); }
            }
            private string toText = "";
            public string ToText
            {
                get { return toText; }
                set { toText = value; NotifyPropertyChanged("ToText"); }
            }
            public ViewModel()
            {
                itemCollection = new ObservableCollection<SfSegmentItem>
                    {
                        new SfSegmentItem() {  Text = "Seater"},
                        new SfSegmentItem() {  Text = "Sleeper"},
                    };
            }
            public event PropertyChangedEventHandler PropertyChanged;
    
            private void NotifyPropertyChanged([CallerMemberName] String propertyName = "")
            {
                if (PropertyChanged != null)
                {
                    PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
                }
            }
    
            private ObservableCollection<SfSegmentItem> itemCollection;

            public ObservableCollection<SfSegmentItem> ItemCollection
            {
                get { return itemCollection; }
                set { itemCollection = value; }
            }
        }
    }

{% endhighlight %}

{% tabs %}

{% highlight xaml %}

        <?xml version="1.0" encoding="utf-8" ?>
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
                 xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
                 xmlns:local="clr-namespace:SegmentGettingStarted"
                  xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
                 xmlns:segmentCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
                 x:Class="SegmentGettingStarted.MainPage">
        <ContentPage.BindingContext>
            <local:ViewModel x:Name="viewModel" />
        </ContentPage.BindingContext>
        <StackLayout 
            HorizontalOptions="Center"
            VerticalOptions="Center"
            Padding="20,0,20,0">
             <Label
            Text="Bus Ticket Booking"
            FontSize="Large"
            FontAttributes="Bold"
            HeightRequest="50"
            HorizontalOptions="Center"
            VerticalOptions="Center"/>
        <Entry
            Placeholder="From"
            Text="{Binding FromText,Mode=TwoWay}"
            HeightRequest="50"
            Margin="0,10,0,10"/>
        <Entry
            Placeholder="To"
            Text="{Binding ToText}"
            HeightRequest="50"
            Margin="0,10,0,10"/>
            <buttons:SfSegmentedControl 
                x:Name="segment" 
                HeightRequest="80"
                VisibleSegmentsCount="2"
                Color="White"
                SelectionTextColor="#007CEE"
                FontColor="#929292"
                BorderColor="#929292"
                SelectedIndex="1"
                ItemsSource="{Binding ItemCollection,Mode=TwoWay}"
                BackgroundColor="Transparent">
            </buttons:SfSegmentedControl>
            <buttons:SfSegmentedControl
                SelectionTextColor="White"
                HeightRequest="80"
                VisibleSegmentsCount="6"
                Color="Transparent" 
                BorderColor="#929292"
                SelectedIndex="1"
                FontColor="#929292"
                BackgroundColor="Transparent" >
                <segmentCollection:List x:TypeArguments="x:String">
                    <x:String>1</x:String>
                    <x:String>2</x:String>
                    <x:String>3</x:String>
                    <x:String>4</x:String>
                    <x:String>5</x:String>
                    <x:String>6</x:String>
                </segmentCollection:List>
            </buttons:SfSegmentedControl>
        </StackLayout>
    </ContentPage>

{% endhighlight %}

{% highlight C# %}


    using Syncfusion.XForms.Buttons;
    using System.Collections.Generic;
    using Xamarin.Forms;
    namespace SegmentGettingStarted
    {
        public partial class MainPage : ContentPage
        {
            SfSegmentedControl segmentedControl, segment;
            StackLayout stack;
            ViewModel viewModel;
            Label headerLabel;
            Entry fromEntry, toEntry;
            public MainPage()
            {
                InitializeComponent();
                stack = new StackLayout();
                viewModel = new ViewModel();
                stack.HorizontalOptions = LayoutOptions.Center;
                stack.VerticalOptions = LayoutOptions.Center;
                stack.Padding = new Thickness(20, 0, 20, 0);
    
                //Label to denote the header part of application
                headerLabel = new Label();
                headerLabel.Text = "Bus Ticket Booking";
                headerLabel.FontAttributes = FontAttributes.Bold;
                headerLabel.HeightRequest = 50;
                headerLabel.FontSize = Device.GetNamedSize(NamedSize.Large, typeof(Label));
                headerLabel.HorizontalOptions = LayoutOptions.Center;
                headerLabel.VerticalOptions = LayoutOptions.Center;

                //Entry to enter the origin location
                fromEntry = new Entry();
                fromEntry.Placeholder = "From";
                fromEntry.Text = viewModel.FromText;
                fromEntry.HeightRequest = 50;
                fromEntry.Margin = new Thickness(0, 10, 0, 10);

                //Entry to enter the destination location
                toEntry = new Entry();
                toEntry.Placeholder = "To";
                toEntry.Text = viewModel.ToText;
                toEntry.HeightRequest = 50;
                toEntry.Margin = new Thickness(0, 10, 0, 10);
    
                //Adding item to the SegmentedControl as String
                segmentedControl = new SfSegmentedControl();
                segmentedControl.SelectionTextColor = Color.White;
                segmentedControl.HeightRequest = 80;
                segmentedControl.Color = Color.Transparent;
                segmentedControl.BorderColor = Color.FromHex("#929292");
                segmentedControl.FontColor = Color.FromHex("#929292");
                segmentedControl.SelectedIndex = 1;
                segmentedControl.BackgroundColor = Color.Transparent;
                segmentedControl.VisibleSegmentsCount = 6;
                segmentedControl.DisplayMode = SegmentDisplayMode.Text;
                List<string> list = new List<string>
                {
                    "1","2","3","4","5","6"
                };
                segmentedControl.ItemsSource = list;

                //Adding item to SegmentedControl as SegmentItem
                segment = new SfSegmentedControl();
                segment.SelectionTextColor = Color.FromHex("#007CEE");
                segment.VisibleSegmentsCount = 2;
                segment.Color = Color.White;
                segment.BorderColor = Color.FromHex("#929292");
                segment.SelectedIndex = 1;
                segment.FontColor = Color.FromHex("#929292");
                segment.BackgroundColor = Color.Transparent;

                segment.BindingContext = viewModel;
                segment.ItemsSource = viewModel.ItemCollection;
    
                SelectionIndicatorSettings select = new SelectionIndicatorSettings();
                select.Color = Color.White;

                segment.SelectionIndicatorSettings = select;
    
                stack.Children.Add(headerLabel);
                stack.Children.Add(fromEntry);
                stack.Children.Add(toEntry);
                stack.Children.Add(segment);
                stack.Children.Add(segmentedControl);
                this.Content = stack;
            }
        }
    }

{% endhighlight %}

{% endtabs %}

![Image for adding data as SfSegmentedItem](images/getting-started/Xamarin_Forms_String_SegmentItem.png)



### Adding data as Custom View

You can add any custom view to the segmented control.

In ViewModel add the below given code to get the respective items/collection in SfSegmentedControl.

{% highlight C# %}

    using Syncfusion.XForms.Buttons;
    using System;
    using System.Collections.ObjectModel;
    using System.ComponentModel;
    using System.Runtime.CompilerServices;
    using Xamarin.Forms;
    
    namespace SegmentGettingStarted
    {
        class ViewModel : INotifyPropertyChanged
        {
            private string fromText="";
            public string FromText
            {
                get { return fromText; }
                set { fromText = value; NotifyPropertyChanged("FromText"); }
            }
            private string toText = "";
            public string ToText
            {
                get { return toText; }
                set { toText = value; NotifyPropertyChanged("ToText"); }
            }
            public ViewModel()
            {
                itemCollection = new ObservableCollection<SfSegmentItem>
                    {
                        new SfSegmentItem() {  Text = "Seater"},
                        new SfSegmentItem() {  Text = "Sleeper"},
                    };
                ViewCollection = new ObservableCollection<View>
                    {
                       ResetViewButton,
                       GoViewButton
                    };
            }
            public event PropertyChangedEventHandler PropertyChanged;
    
            private void NotifyPropertyChanged([CallerMemberName] String propertyName = "")
            {
                if (PropertyChanged != null)
                {
                    PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
                }
            }
    
            private ObservableCollection<SfSegmentItem> itemCollection = new ObservableCollection<SfSegmentItem>();
            private ObservableCollection<View> viewCollection = new ObservableCollection<View>();
            public ObservableCollection<SfSegmentItem> ItemCollection
            {
                get { return itemCollection; }
                set { itemCollection = value; }
            }
            public ObservableCollection<View> ViewCollection
            {
                get { return viewCollection; }
                set { viewCollection = value; }
            }
            private Button ResetViewButton = new Button
            {
                Text = "Reset",
                TextColor = Color.FromHex("#979797"),
                BackgroundColor = Color.White,
                BorderColor = Color.FromHex("#979797"),
                BorderWidth = 1,
                CornerRadius = 4,
                HeightRequest = 50,
                VerticalOptions = LayoutOptions.Center
            };
            private Button GoViewButton = new Button
            {
                Text = "Go",
                TextColor = Color.FromHex("#979797"),
                BackgroundColor = Color.White,
                BorderColor = Color.FromHex("#979797"),
                BorderWidth = 1,
                CornerRadius = 4,
                HeightRequest = 50,
                VerticalOptions = LayoutOptions.Center
            };
        }
    }

{% endhighlight %}


{% tabs %}

{% highlight xaml %}

   
    <?xml version="1.0" encoding="utf-8" ?>
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
                 xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
                 xmlns:local="clr-namespace:SegmentGettingStarted"
                  xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
                 xmlns:segmentCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
                 x:Class="SegmentGettingStarted.MainPage">
    
        <ContentPage.BindingContext>
            <local:ViewModel x:Name="viewModel" />
        </ContentPage.BindingContext>
        <StackLayout 
            HorizontalOptions="Center"
            VerticalOptions="Center"
            Padding="20,0,20,0">
        <Label
            Text="Bus Ticket Booking"
            FontSize="Large"
            FontAttributes="Bold"
            HeightRequest="50"
            HorizontalOptions="Center"
            VerticalOptions="Center"/>
        <Entry
            Placeholder="From"
            Text="{Binding FromText,Mode=TwoWay}"
            HeightRequest="50"
            Margin="0,10,0,10"/>
        <Entry
            Placeholder="To"
            Text="{Binding ToText}"
            HeightRequest="50"
            Margin="0,10,0,10"/>
        <buttons:SfSegmentedControl 
                x:Name="segment" 
                HeightRequest="80"
                VisibleSegmentsCount="2"
                Color="White"
                SelectionTextColor="#007CEE"
                FontColor="#929292"
                BorderColor="#929292"
                SelectedIndex="1"
                ItemsSource="{Binding ItemCollection,Mode=TwoWay}"
                BackgroundColor="Transparent">
        </buttons:SfSegmentedControl>
        <buttons:SfSegmentedControl
                SelectionTextColor="White"
                HeightRequest="80"
                VisibleSegmentsCount="6"
                Color="Transparent" 
                BorderColor="#929292"
                SelectedIndex="1"
                FontColor="#929292"
                BackgroundColor="Transparent" >
                <segmentCollection:List x:TypeArguments="x:String">
                    <x:String>1</x:String>
                    <x:String>2</x:String>
                    <x:String>3</x:String>
                    <x:String>4</x:String>
                    <x:String>5</x:String>
                    <x:String>6</x:String>
                </segmentCollection:List>
        </buttons:SfSegmentedControl>
        <buttons:SfSegmentedControl
                BorderColor="Transparent" 
                HeightRequest="80"
                HorizontalOptions="Center"
                x:Name="segmentView"
                VisibleSegmentsCount="2"
                Color="Transparent"
                ItemsSource="{Binding ViewCollection}"
                SegmentPadding="30">
            </buttons:SfSegmentedControl>
        </StackLayout>
    </ContentPage>
    

{% endhighlight %}

{% highlight C# %}

    using Syncfusion.XForms.Buttons;
    using System.Collections.Generic;
    using Xamarin.Forms;
    
    namespace SegmentGettingStarted
    {
        public partial class MainPage : ContentPage
        {
            SfSegmentedControl segmentedControl, segment, segmentView;
            StackLayout stack;
            ViewModel viewModel;
            Label headerLabel;
            Entry fromEntry, toEntry;
            public MainPage()
            {
                InitializeComponent();
                stack = new StackLayout();
                viewModel = new ViewModel();
                stack.HorizontalOptions = LayoutOptions.Center;
                stack.VerticalOptions = LayoutOptions.Center;
                stack.Padding = new Thickness(20, 0, 20, 0);

                //Label to denote the header part of application
                headerLabel = new Label();
                headerLabel.Text = "Bus Ticket Booking";
                headerLabel.FontAttributes = FontAttributes.Bold;
                headerLabel.HeightRequest = 50;
                headerLabel.FontSize = Device.GetNamedSize(NamedSize.Large, typeof(Label));
                headerLabel.HorizontalOptions = LayoutOptions.Center;
                headerLabel.VerticalOptions = LayoutOptions.Center;

                //Entry to enter the origin location
                fromEntry = new Entry();
                fromEntry.Placeholder = "From";
                fromEntry.Text = viewModel.FromText;
                fromEntry.HeightRequest = 50;
                fromEntry.Margin = new Thickness(0, 10, 0, 10);

                //Entry to enter the destination location
                toEntry = new Entry();
                toEntry.Placeholder = "To";
                toEntry.Text = viewModel.ToText;
                toEntry.HeightRequest = 50;
                toEntry.Margin = new Thickness(0, 10, 0, 10);
    
                //Adding item to the segmented control as String
                segmentedControl = new SfSegmentedControl();
                segmentedControl.SelectionTextColor = Color.White;
                segmentedControl.HeightRequest = 80;
                segmentedControl.Color = Color.Transparent;
                segmentedControl.BorderColor = Color.FromHex("#929292");
                segmentedControl.FontColor = Color.FromHex("#929292");
                segmentedControl.SelectedIndex = 1;
                segmentedControl.BackgroundColor = Color.Transparent;
                segmentedControl.VisibleSegmentsCount = 6;
                segmentedControl.DisplayMode = SegmentDisplayMode.Text;
                List<string> list = new List<string>
                {
                    "1","2","3","4","5","6"
                };
                segmentedControl.ItemsSource = list;

                //Adding item to segmented control as SegmentItem
                segment = new SfSegmentedControl();
                segment.SelectionTextColor = Color.FromHex("#007CEE");
                segment.VisibleSegmentsCount = 2;
                segment.Color = Color.White;
                segment.BorderColor = Color.FromHex("#929292");
                segment.SelectedIndex = 1;
                segment.FontColor = Color.FromHex("#929292");
                segment.BackgroundColor = Color.Transparent;

                segment.BindingContext = viewModel;
                segment.ItemsSource = viewModel.ItemCollection;
    
                SelectionIndicatorSettings select = new SelectionIndicatorSettings();
                select.Color = Color.White;

                segment.SelectionIndicatorSettings = select;
    
                //Adding item to the segmented control as View
                segmentView = new SfSegmentedControl();
                segmentView.BindingContext = viewModel;
                segmentView.ItemsSource = viewModel.ViewCollection;
                segmentView.BorderColor = Color.Transparent;
                segmentView.HeightRequest = 80;
                segmentView.HorizontalOptions = LayoutOptions.Center;
                segmentView.VisibleSegmentsCount = 2;
                segmentView.Color = Color.Transparent;
                segmentView.SegmentPadding = 30;
    
                SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings();
                selectionIndicator.Color = Color.Transparent;
                selectionIndicator.Position = SelectionIndicatorPosition.Fill;
                selectionIndicator.StrokeThickness = 10;
    
                segmentView.SelectionIndicatorSettings = selectionIndicator;
    
                stack.Children.Add(headerLabel);
                stack.Children.Add(fromEntry);
                stack.Children.Add(toEntry);
                stack.Children.Add(segment);
                stack.Children.Add(segmentedControl);
                stack.Children.Add(segmentView);
                this.Content = stack;
            }
        }
    }


{% endhighlight %}

{% endtabs %}

![CustomView Image](images/getting-started/Xamarin_forms_gettingstarted.png)

## Customizing segmented control appearance

### Share space equally to all the items

To share the item space equally to the segmented control, set the number of segment item that has to be visible on the available screen width and that can be distributed in the available space using the `VisibleSegmentsCount` property of `SfSegmentedControl`.

{% tabs %}

{% highlight xaml %}

    <buttons:SfSegmentedControl VisibleSegmentsCount="5">
	
{% endhighlight %}

{% highlight C# %}

    SegmentedControl.VisibleSegmentsCount = 5;

{% endhighlight %}

{% endtabs %}


### Display mode

You can change the appearance of the segmented control by using the `DisplayMode` property of SfSegmentedControl. You can set the `DisplayMode` to either Image or Text or ImageWithText.

{% tabs %}

{% highlight xaml %}

    <buttons:SfSegmentedControl DisplayMode="Text"/>
	
{% endhighlight %}

{% highlight c# %}

    SegmentedControl.DisplayMode = SegmentDisplayMode.Text;

{% endhighlight %}
{% endtabs %}


## Customizing selection indicator appearance

The Selection indicator can be used to indicate the selected index of the segmented control. It can be customized with the built-in APIs that are available in the `SelectionIndicatorSettings` property of SfSegmentedControl.

To learn more about customizing selection indicator, refer to this [feature link](https://help.syncfusion.com/xamarin/sfsegmentedcontrol/indicating-the-selected-item)

## Handle click events

SfSegmentedControl has SelectionChanged event, using this, you can perform operation based on your needs.

{% tabs %}

{% highlight xaml %}

     <buttons:SfSegmentedControl 
     x:Name="SegmentedControl" 
     SelectionChanged="SegmentedControl_SelectionChanged" />

{% endhighlight %}

{% highlight C# %}

    SegmentedControl.SelectionChanged += SegmentedControl_SelectionChanged;

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

        private void SegmentedControl_SelectionChanged(object sender, Syncfusion.XForms.Buttons.SelectionChangedEventArgs e)
        {
                var currentValue = e.Index; //To get the value of current selected index.
        }

{% endhighlight %}

{% endtabs %}

N> For custom view user, need to handle the click event manually for the view which have been used.
eg. For Button we have to use its "Click" event.


The below given code can be included on the Custom view viewModel to get the click event output.

{% tabs %}

{% highlight C# %}

        public ViewModel()
        {
            ResetViewButton.Clicked += ResetViewButton_Clicked;
            GoViewButton.Clicked += GoViewButton_Clicked;
        }

         private void GoViewButton_Clicked(object sender, EventArgs e)
        {
                if (FromText == "")
                {
                    SendMessage("Please enter your origin city.");
                }
                else if (ToText == "")
                {
                    SendMessage("Please enter your destination city.");
                }
                else
                    SendMessage("Your ticket has been booked.");
        }

        private void ResetViewButton_Clicked(object sender, EventArgs e)
        {
            FromText = "";
            ToText = "";
            Application.Current.MainPage.DisplayAlert("Status", "Fields has been refreshed", null, "Ok");
        }

         internal void SendMessage(string message)
        {
            Application.Current.MainPage.DisplayAlert(message, null, "Ok");
        }


{% endhighlight %}

{% endtabs %}


Note: Getting started sample can be downloaded from this [link](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted1466563199.zip)
