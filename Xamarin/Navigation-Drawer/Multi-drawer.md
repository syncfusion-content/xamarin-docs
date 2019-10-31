---
layout: post
title: Multi drawer support of Syncfusion NavigationDrawer control for Forms
description: Learn how to set multi drawer view in NavigationDrawer.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---


# Multi Drawer

The navigation drawer allows users to open the drawer on multiple sides with different toggle methods. The DrawerSettings class and its properties need to be used when users need to provide multiple drawer. The multiple drawers can be implemented using the following drawer settings.

* Default drawer settings
* Secondary drawer settings

N> The header and footer content are optional, but the drawer content is mandatory to allocate space for the drawer.
		
## Default drawer settings

Implement the default drawer using the default drawer settings class. The following code sample demonstrates how to set the default drawer settings's properties inside the DrawerSettings class.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
    <navigationdrawer:SfNavigationDrawer.DefaultDrawerSettings >
    <navigationdrawer:DrawerSettings
        DrawerWidth="150"
        DrawerHeight="150"
        Transition ="SlideOnTop"
        DrawerHeaderHeight="150"
        DrawerFooterHeight="150"
        ContentBackgroundColor ="Red"
        Position="Left">
    </navigationdrawer:DrawerSettings>
    </navigationdrawer:SfNavigationDrawer.DefaultDrawerSettings>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.SfNavigationDrawer.XForms;
using Xamarin.Forms;

namespace NaviSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            DrawerSettings defaultDrawerSettings = new DrawerSettings();
            defaultDrawerSettings.DrawerHeight = 150;
            defaultDrawerSettings.Position = Position.Left;
            defaultDrawerSettings.Transition = Transition.SlideOnTop;
            defaultDrawerSettings.ContentBackgroundColor = Color.Red;
            defaultDrawerSettings.DrawerWidth = 150;
            navigationDrawer.DrawerHeaderHeight = 150;
            navigationDrawer.DrawerFooterHeight = 150;
            navigationDrawer.DefaultDrawerSettings = defaultDrawerSettings;
            this.Content = navigationDrawer;
        }
    }
}
  
{% endhighlight %}

{% endtabs %}

N> The navigation drawer works with the value given for the properties inside the DrawerSettings class when using the default drawer settings.

### Default drawer header view

The header content can be provided to the default drawer using the `DrawerHeaderView` property inside the DrawerSettings class of DefaultDrawerSettings. The following code demonstrates how to set header content for the default drawer.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
    <navigationdrawer:SfNavigationDrawer.DefaultDrawerSettings>
    <Grid BackgroundColor="#1aa1d6">
    <Grid.RowDefinitions>
    <RowDefinition Height="120"/>
    </Grid.RowDefinitions>
    <navigationdrawer:DrawerSettings.DrawerHeaderView>
    <Label Text="Syncfusion Xamarin Products"  HorizontalTextAlignment="Center" HorizontalOptions="Center" FontSize="20" TextColor="White"/>
    </navigationdrawer:DrawerSettings.DrawerHeaderView>
     </Grid>
    </navigationdrawer:SfNavigationDrawer.DefaultDrawerSettings>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

   using System;
using Syncfusion.SfNavigationDrawer.XForms;
using Xamarin.Forms;

namespace NaviSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            DrawerSettings defaultDrawerSettings = new DrawerSettings();
            Grid headerLayout = new Grid();
            headerLayout.BackgroundColor = Color.FromHex("#1aa1d6");
            Label header = new Label();
            header.Text = "Syncfusion Xamarin Products";
            header.FontSize = 20;
            header.TextColor = Color.White;
            header.HorizontalTextAlignment = TextAlignment.Center;
            headerLayout.Children.Add(header);
            defaultDrawerSettings.DrawerHeaderView = headerLayout;
            this.Content = navigationDrawer;
        }
    }
}

{% endhighlight %}

{% endtabs %}      

### Default drawer content view

The drawer content can be provided to the default drawer using the `DrawerContentView` property inside the DrawerSettings class. The following code demonstrates how to set drawer content to the default drawer.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
<navigationdrawer:SfNavigationDrawer.DefaultDrawerSettings>
<navigationdrawer:DrawerSettings>
<navigationdrawer:DrawerSettings.DrawerContentView>
    <Label Text="DrawerContent "  
           HorizontalTextAlignment="Center" 
           HorizontalOptions="Center"
           FontSize="20" 
           TextColor="White"/>
</navigationdrawer:DrawerSettings.DrawerContentView>
</navigationdrawer:DrawerSettings>   
</navigationdrawer:SfNavigationDrawer.DefaultDrawerSettings>
</ContentPage>
      
{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.SfNavigationDrawer.XForms;
using Xamarin.Forms;

namespace NaviSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            DrawerSettings defaultDrawerSettings = new DrawerSettings();
            Grid contentLayout = new Grid();
            contentLayout.BackgroundColor = Color.FromHex("#1aa1d6");
            Label content = new Label();
            content.Text = "DrawerContent";
            content.FontSize = 20;
            content.TextColor = Color.White;
            content.HorizontalTextAlignment = TextAlignment.Center;
            contentLayout.Children.Add(content);
            defaultDrawerSettings.DrawerContentView = contentLayout;
            this.Content = navigationDrawer;
        }
    }
}

{% endhighlight %}

{% endtabs %}   

### Default drawer footer view

The footer content can be provided to the default drawer using the `DrawerFooterView` property inside the DrawerSettings class of DefaultDrawerSettings. The following code demonstrates how to set footer content to the default drawer.

{% tabs %}

{% highlight xaml %}
    
<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
<navigationdrawer:SfNavigationDrawer.DefaultDrawerSettings>   
    <navigationdrawer:DrawerSettings.DrawerFooterView>
    <Grid BackgroundColor="#1aa1d6">
    <Grid.RowDefinitions>
    <RowDefinition Height="120"/>
    </Grid.RowDefinitions>
        <Label Text="Close" 
               Grid.Row="0" 
               HorizontalTextAlignment="Center" 
               HorizontalOptions="Center" 
               FontSize="20" 
               TextColor="White"/>
    </Grid>
    </navigationdrawer:DrawerSettings.DrawerFooterView>
    </navigationdrawer:SfNavigationDrawer.DefaultDrawerSettings>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.SfNavigationDrawer.XForms;
using Xamarin.Forms;

namespace NaviSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            DrawerSettings defaultDrawerSettings = new DrawerSettings();
            Grid footerLayout = new Grid();
            footerLayout.BackgroundColor = Color.FromHex("#1aa1d6");
            Label footer = new Label();
            footer.Text = "Close";
            footer.FontSize = 20;
            footer.TextColor = Color.White;
            footer.HorizontalTextAlignment = TextAlignment.Center;
            footerLayout.Children.Add(footer);
            defaultDrawerSettings.DrawerFooterView = footerLayout;
            this.Content = navigationDrawer;
        }
    }
}

{% endhighlight %}

{% endtabs %}   

## Secondary drawer settings   

Implement the secondary drawer using the secondary drawer settings class. Its properties and functionalities are same as the default drawer. The secondary drawer can be set to different positions similar to the default drawer. The following code demonstrates how to set the secondary drawer settings's properties inside the DrawerSettings class.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
    <navigationdrawer:SfNavigationDrawer.SecondaryDrawerSettings >
        <navigationdrawer:DrawerSettings x:Name="secondaryDrawer"
                                 DrawerHeaderHeight="40"
                                 DrawerFooterHeight="40"
                                 ContentBackgroundColor="Blue"
                                 DrawerHeight="300"
                                 DrawerWidth= "150"
                                 Duration="400" 
                                 Position="Right"
                                 Transition="SlideOnTop">
        </navigationdrawer:DrawerSettings>
    </navigationdrawer:SfNavigationDrawer.SecondaryDrawerSettings>
</ContentPage>
               
{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.SfNavigationDrawer.XForms;
using Xamarin.Forms;

namespace NaviSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            DrawerSettings secondaryDrawer = new DrawerSettings();
            secondaryDrawer.DrawerHeight = 300;
            secondaryDrawer.Position = Position.Right;
            secondaryDrawer.Transition = Transition.SlideOnTop;
            secondaryDrawer.ContentBackgroundColor = Color.Blue;
            secondaryDrawer.DrawerWidth = 150;
            secondaryDrawer.DrawerHeaderHeight = 40;
            secondaryDrawer.DrawerFooterHeight = 40;
            navigationDrawer.SecondaryDrawerSettings = secondaryDrawer;
            this.Content = navigationDrawer;
        }
    }
}
  
{% endhighlight %}

{% endtabs %}

N> When the default drawer and the secondary drawer are set to the same position, the default drawer will open on swiping.

### Secondary drawer header view

The header content can be provided to the secondary drawer using the `DrawerHeaderView` property inside the DrawerSettings class of SecondaryDrawerSettings. The following code demonstrates how to set the header content to the secondary drawer.

{% tabs %}

{% highlight xaml %}
    
<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
    <navigationdrawer:SfNavigationDrawer.SecondaryDrawerSettings>
        <navigationdrawer:DrawerSettings.DrawerHeaderView>
            <Grid BackgroundColor="#1aa1d6">
                <Grid.RowDefinitions>
                    <RowDefinition Height="120"/>
                </Grid.RowDefinitions>
                <Label Text="Syncfusion Enterprise solution" 
                       Grid.Row="0" 
                       HorizontalTextAlignment="Center" 
                       HorizontalOptions="Center" 
                       FontSize="20" 
                       TextColor="White"/>
            </Grid>
        </navigationdrawer:DrawerSettings.DrawerHeaderView>
    </navigationdrawer:SfNavigationDrawer.SecondaryDrawerSettings>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.SfNavigationDrawer.XForms;
using Xamarin.Forms;

namespace NaviSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            DrawerSettings secondaryDrawer = new DrawerSettings();
            Grid secondary = new Grid();
            secondary.BackgroundColor = Color.FromHex("#1aa1d6");
            Label header = new Label();
            header.Text = "Syncfusion Enterprise solution";
            header.FontSize = 20;
            header.TextColor = Color.White;
            header.HorizontalTextAlignment = TextAlignment.Center;
            secondary.Children.Add(header);
            secondaryDrawer.DrawerHeaderView = secondary;
            this.Content = navigationDrawer;
        }
    }
}

{% endhighlight %}

{% endtabs %}      

### Secondary drawer content view

The drawer content can be provided to the default drawer using the `DrawerContentView` property inside the DrawerSettings class of SecondaryDrawerSettings. The following code demonstrates how to set the drawer content to the secondary drawer.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
    <navigationdrawer:SfNavigationDrawer.SecondaryDrawerSettings>
        <navigationdrawer:DrawerSettings>
            <navigationdrawer:DrawerSettings.DrawerContentView>
                <Label Text="DrawerContent "  
                       HorizontalTextAlignment="Center" 
                       HorizontalOptions="Center" 
                       FontSize="20" 
                       TextColor="White"/>
            </navigationdrawer:DrawerSettings.DrawerContentView>
        </navigationdrawer:DrawerSettings>   
    </navigationdrawer:SfNavigationDrawer.SecondaryDrawerSettings>
</ContentPage>
      
{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.SfNavigationDrawer.XForms;
using Xamarin.Forms;

namespace NaviSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            DrawerSettings secondaryDrawer = new DrawerSettings();
            Grid Layout = new Grid();
            Layout.BackgroundColor = Color.FromHex("#1aa1d6");
            Label content = new Label();
            content.Text = "DrawerContent";
            content.FontSize = 20;
            content.TextColor = Color.White;
            content.HorizontalTextAlignment = TextAlignment.Center;
            Layout.Children.Add(content);
            secondaryDrawer.DrawerContentView = Layout;
            this.Content = navigationDrawer;
        }
    }
}

{% endhighlight %}

{% endtabs %}   

### Secondary drawer footer view

The footer content can be provided to the secondary drawer using the `DrawerFooterView` property inside the DrawerSettings class of SecondaryDrawerSettings. The following code demonstrates how to set footer content to the secondary drawer.

{% tabs %}

{% highlight xaml %}
    
<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
    <navigationdrawer:SfNavigationDrawer.SecondaryDrawerSettings>
        <navigationdrawer:DrawerSettings.DrawerFooterView>
            <Grid BackgroundColor="#1aa1d6">
                <Grid.RowDefinitions>
                    <RowDefinition Height="120"/>
                </Grid.RowDefinitions>
                <Label Text="Close" 
                       Grid.Row="0" 
                       HorizontalTextAlignment="Center" 
                       HorizontalOptions="Center" 
                       FontSize="20" 
                       TextColor="White"/>
            </Grid>
        </navigationdrawer:DrawerSettings.DrawerFooterView>
    </navigationdrawer:SfNavigationDrawer.SecondaryDrawerSettings>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using Syncfusion.SfNavigationDrawer.XForms;
using Xamarin.Forms;

namespace NaviSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
            DrawerSettings secondaryDrawer = new DrawerSettings();
            Grid Layout = new Grid();
            Layout.BackgroundColor = Color.FromHex("#1aa1d6");
            Label footer = new Label();
            footer.Text = "Close";
            footer.FontSize = 20;
            footer.TextColor = Color.White;
            footer.HorizontalTextAlignment = TextAlignment.Center;
            Layout.Children.Add(footer);
            secondaryDrawer.DrawerFooterView = Layout;
            this.Content = navigationDrawer;
        }
    }
}

{% endhighlight %}

{% endtabs %}   

## Toggling method

Users can toggle the secondary drawer using the `ToggleSecondaryDrawer` method. 

{% highlight c# %} 

navigationDrawer.ToggleSecondaryDrawer();

{% endhighlight %}

### Opening the drawer programmatically

The `IsOpen` property in the DrawerSettings of SecondaryDrawerSettings is used to open or close the drawer programmatically.

N> Users can open only one drawer at a time.

Note: The sample for implementing multiple drawers can be downloaded from this [link](http://www.syncfusion.com/downloads/support/directtrac/general/ze/NavigationDrawerSample_2-228312513).

