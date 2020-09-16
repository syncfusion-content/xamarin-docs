---
layout : post
title : Events in Syncfusion RadialMenu control for Xamarin.Forms
description : Learn how to perform events in RadialMenu
platform : xamarin
control : SfRadialMenu
documentation : ug
---

# Events

## Perform an action while navigating to next level

In radial menu, you can perform an action while navigating from one level to another level. The [`Navigating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html) event occurs when navigating from one level to another level and the [`Navigated`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html) event occurs after navigating to another level.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu Navigating="SfRadialMenu_Navigating" 
                             Navigated="SfRadialMenu_Navigated">
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Bold" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Copy" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Undo" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Paste" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Color" FontSize="12"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();

            ObservableCollection<SfRadialMenuItem> itemCollection = new ObservableCollection<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem() { Text = "Bold", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Copy", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Paste", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Undo", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Color", FontSize = 12 });
            radialMenu.Items = itemCollection;

            radialMenu.Navigating += SfRadialMenu_Navigating;
            radialMenu.Navigated += SfRadialMenu_Navigated;

            this.Content = radialMenu;
        }

        private void SfRadialMenu_Navigating(object sender, NavigatingEventArgs e)
        {
            DisplayAlert("Alert", "ItemNavigating", "Ok");
        }

        private void SfRadialMenu_Navigated(object sender, NavigatedEventArgs e)
        {
            DisplayAlert("Alert", "ItemNavigated", "Ok");
        }
    }
}

{% endhighlight %}

{% endtabs %}

N> You can cancel navigation using the `Cancel` event argument.

## Perform an action while opening the radial menu

You can perform an action while opening the radial menu. The [`Opening`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html) event occurs when opening the radial menu and the [`Opened`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html) event occurs after opening the radial menu.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu Opening ="SfRadialMenu_Opening" 
                             Opened="SfRadialMenu_Opened">
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Bold" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Copy" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Undo" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Paste" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Color" FontSize="12"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();

            ObservableCollection<SfRadialMenuItem> itemCollection = new ObservableCollection<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem() { Text = "Bold", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Copy", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Paste", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Undo", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Color", FontSize = 12 });
            radialMenu.Items = itemCollection;
            
            radialMenu.Opening += SfRadialMenu_Opening;
            radialMenu.Opened += SfRadialMenu_Opened;

            this.Content = radialMenu;
        }

        private void SfRadialMenu_Opening(object sender, OpeningEventArgs e)
        {
            DisplayAlert("Alert", "ItemOpening", "Ok");
        }

        private void SfRadialMenu_Opened(object sender, OpenedEventArgs e)
        {
            DisplayAlert("Alert", "ItemOpened", "Ok");
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Perform an action while closing the radial menu

You can perform an action when closing the radial menu. The [`Closing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html) event occurs when closing the radial menu and the [`Closed`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html) event occurs after closing the radial menu.


{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu  Closing ="SfRadialMenu_Closing" 
                              Closed="SfRadialMenu_Closed">
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Bold" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Copy" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Undo" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Paste" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Color" FontSize="12"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();

            ObservableCollection<SfRadialMenuItem> itemCollection = new ObservableCollection<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem() { Text = "Bold", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Copy", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Paste", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Undo", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Color", FontSize = 12 });
            radialMenu.Items = itemCollection;

            radialMenu.Closing += SfRadialMenu_Closing;
            radialMenu.Closed += SfRadialMenu_Closed;

            this.Content = radialMenu;
        }

        private void SfRadialMenu_Closing(object sender, ClosingEventArgs e)
        {
            DisplayAlert("Alert", "ItemClosing", "Ok");
        }

        private void SfRadialMenu_Closed(object sender, ClosedEventArgs e)
        {
            DisplayAlert("Alert", "ItemClosed", "Ok");
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Perform an action while tapping the center back button

You can perform an action when tapping the center back button of the radial menu. The [`CenterButtonBackTapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html) event occurs when tapping the center button of the radial menu.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu CenterButtonBackTapped="SfRadialMenu_CenterButtonBackTapped">
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Bold" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Copy" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Undo" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Paste" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Color" FontSize="12"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();

            ObservableCollection<SfRadialMenuItem> itemCollection = new ObservableCollection<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem() { Text = "Bold", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Copy", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Paste", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Undo", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Color", FontSize = 12 });
            radialMenu.Items = itemCollection;

            radialMenu.CenterButtonBackTapped += SfRadialMenu_CenterButtonBackTapped;
            this.Content = radialMenu;
        }

        private void SfRadialMenu_CenterButtonBackTapped(object sender, CenterButtonBackTappedEventArgs e)
        {
            DisplayAlert("Alert", "CenterButtonTapped", "Ok");
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Perform an action while tapping the radial menu item

You can perform an action when tapping the radial menu item of the radial menu. The [`ItemTapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem.html) event occurs when tapping the items of the radial menu.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Bold" FontSize="12" ItemTapped="SfRadialMenuItem_ItemTapped"/>
            <radialMenu:SfRadialMenuItem Text="Copy" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Undo" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Paste" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Color" FontSize="12"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
 
 {% endhighlight %}

 {% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();

            ObservableCollection<SfRadialMenuItem> itemCollection = new ObservableCollection<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem() { Text = "Bold", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Copy", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Paste", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Undo", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Color", FontSize = 12 });
            radialMenu.Items = itemCollection;

            radialMenu.Items[0].ItemTapped += SfRadialMenuItem_ItemTapped;
            this.Content = radialMenu;
        }

        private void SfRadialMenuItem_ItemTapped(object sender, Syncfusion.SfRadialMenu.XForms.ItemTappedEventArgs e)
        {
            DisplayAlert("Alert", "ItemTapped", "Ok");
        }
    }
}

{% endhighlight %}

{% endtabs %}
