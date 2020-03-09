---
layout: post
title: Customizations of Syncfusion Xamarin.Forms SfTimePicker
description: How to customize the header, footer, selected item and unselected item of the Syncfusion Xamarin.Forms SfTimePicker
platform: Xamarin
control: TimePicker
documentation: ug
---

# Customization support in SfTimePicker

You can customize the header, column header, footer, selected item, and unselected item of the SfTimePicker.

## Header customization

SfTimePicker allows customizing the header's background, text color, and fonts.

### Enable or disable header 

SfTimePicker allows enabling or disabling the header section by setting the `SfTimePicker.ShowHeader` property to true or false. The default value of the `SfTimePicker.ShowHeader` property is "true".

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 ShowHeader="False"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                ShowHeader = false
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Set header text

SfTimePicker allows providing custom text to its header by setting the `SfTimePicker.HeaderText` property. The default value of the `SfTimePicker.HeaderText` property is "Time Picker".

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 HeaderText="Select a time"/>
    </ContentPage.Content>
</ContentPage>
 
{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                HeaderText = "Select a time"
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Background

Background color of the header can be customized by setting the `SfTimePicker.HeaderBackgroundColor` property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 HeaderBackgroundColor="SkyBlue"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                HeaderBackgroundColor = Color.SkyBlue
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Text color 

Text color of the header can be customized by setting the `SfTimePicker.HeaderTextColor` property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 HeaderTextColor="Red"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
               HeaderTextColor = Color.Red; 
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}
{% endtabs %}

### Font 

This section explains the Font customization of header text.

#### FontFamily

FontFamily of the header text can be customized by setting the `SfTimePicker.HeaderFontFamily` property.

{% tabs %}

{% highlight xaml %}

<<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 HeaderFontFamily="Times New Roman"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                HeaderFontFamily = "Times New Roman"
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

#### FontSize

FontSize of the header text can be customized by setting the `SfTimePicker.HeaderFontSize` property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 HeaderFontSize="18"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                HeaderFontSize = 18
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}   

#### FontAttribute

FontAttribute of the header text can be customized by setting the `SfTimePicker.HeaderFontAttribute` property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 HeaderFontAttribute="Italic"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                HeaderFontAttribute = FontAttributes.Italic
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Customization of header

This feature allows the users to have a custom view in the header part of the control in Date Picker.

{% tabs %}

{% highlight xaml %}

<ContentPage.Content>
        <StackLayout>
            <datePicker:SfDatePicker
                ShowHeader="True"
                WidthRequest="350"
                HeightRequest="350">
                <datePicker:SfDatePicker.HeaderView>
                    <StackLayout>
                        <Label Text="Select Date" HorizontalTextAlignment="Center" FontSize="Medium" FontAttributes="Italic"/>
                    </StackLayout>
                </datePicker:SfDatePicker.HeaderView>
            </datePicker:SfDatePicker>
        </StackLayout>
</ContentPage.Content>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
namespace Sample
{
    [XamlCompilation(XamlCompilationOptions.Compile)]
    public partial class DatePicker : ContentPage
    {
        SfDatePicker datePicker;
        public DatePicker()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            datePicker = new SfDatePicker();
            datePicker.ShowHeader = true;
            datePicker.HeaderView = new Label() { Text = "Select Date", HorizontalTextAlignment = TextAlignment.Center  };
            stackLayout.Children.Add(datePicker);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Column header customization

SfTimePicker allows customizing the column header's background, text color, and fonts.

### Enable or disable column header 

SfTimePicker allows enabling or disabling the column header section by setting the `SfTimePicker.ShowColumnHeader` property to true or false. The default value of the `SfTimePicker.ShowColumnHeader` property is "true".

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 ShowColumnHeader="False"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                ShowColumnHeader = false
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Set custom column header 

SfTimePicker allows providing custom text to its column header by setting the `SfTimePicker.HourHeaderText`, `SfTimePicker.MinutesHeaderText`, and `SfTimePicker.SecondsHeaderText` properties. The default value of the `SfTimePicker.HourHeaderText` property is "Hour", `SfTimePicker.MinutesHeaderText` is "Minutes", and `SfTimePicker.SecondsHeaderText` is "Seconds".

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 HourHeaderText="Hour Column"
                                 MinutesHeaderText="Minutes Column"
                                 SecondsHeaderText="Seconds Column"/>
    </ContentPage.Content>
</ContentPage>
 
{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                HourHeaderText = "Hour Column",
                MinutesHeaderText = "Minutes Column",
                SecondsHeaderText = "Seconds Column"
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Background

Background color of the column header can be customized by setting the `SfTimePicker.ColumnHeaderBackgroundColor` property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 ColumnHeaderBackgroundColor="Green"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                ColumnHeaderBackgroundColor = Color.Green
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Text color 

Text color of the column header can be customized by setting the `SfTimePicker.ColumnHeaderTextColor` property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 ColumnHeaderTextColor="Red"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                ColumnHeaderTextColor = Color.Red
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Font 

This section explains the Font customization of the column header text.

#### FontFamily

FontFamily of the column header text can be customized by setting the `SfTimePicker.ColumnHeaderFontFamily` property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 ColumnHeaderFontFamily="Times New Roman"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                ColumnHeaderFontFamily = "Times New Roman"
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

#### FontSize

FontSize of the column header text can be customized by setting the `SfTimePicker.ColumnHeaderFontSize` property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                ColumnHeaderFontSize="18"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                ColumnHeaderFontSize = 18
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}   

#### FontAttribute

FontAttribute of the column header text can be customized by setting the `SfTimePicker.ColumnHeaderFontAttribute` property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 ColumnHeaderFontAttribute="Bold"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                ColumnHeaderFontAttribute = FontAttributes.Bold
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Footer customization

SfTimePicker allows customizing background and text color of the OK and Cancel buttons of the footer.

### Enable or disable footer 

TimePicker allows enabling or disabling the footer section by setting the `SfTimePicker.ShowFooter` property to true or false. The default value of `SfTimePicker.ShowFooter` property is "false".

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 ShowFooter="True"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                ShowFooter = true
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### OK and Cancel buttons customizations

#### Background

Background colors of the OK and Cancel buttons can be customized by setting the `SfTimePicker.OKButtonBackgroundColor` and `SfTimePicker.CancelButtonBackgroundColor` properties.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 ShowFooter="True"
                                 OKButtonBackgroundColor="Pink"
                                 CancelButtonBackgroundColor="Pink"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                OKButtonBackgroundColor = Color.Pink,
                CancelButtonBackgroundColor = Color.Pink
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

#### Text-Color 

Text colors of the OK and Cancel buttons can be customized by setting the `SfTimePicker.OKButtonTextColor` and `SfTimePicker.CancelButtonTextColor` properties.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 ShowFooter="True"
                                 OKButtonTextColor="Brown"
                                 CancelButtonTextColor="Brown"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                OKButtonTextColor = Color.Brown,
                CancelButtonTextColor = Color.Brown
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Perform validation with default validation button

TimePicker allows performing validation based on OK or Cancel button by using `SfTimePicker.OkCommand` and `SfTimePicker.CancelCommand`.

The following example shows how to use the OkCommand and the CancelCommand. When you click the OK button, the background color of the selected item will change to green. When you click the Cancel button, the background color of the selected item will change to red.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.BindingContext>
        <local:CommandDemoViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 OkCommand="{Binding OkCommand}"
                                 CancelCommand="{Binding CancelCommand}"
                                 ColumnHeaderFontAttribute="Bold"
                                 SelectionBackgroundColor="{Binding Background}"
                                 ShowFooter="True"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using System.ComponentModel;
using System.Runtime.CompilerServices;
using System.Windows.Input;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
        }
    }

    // ViewModel
    public class CommandDemoViewModel : INotifyPropertyChanged
    {

        private Color _background = Color.Accent;

        public Color Background
        {
            get { return _background; }
            set
            {
                _background = value;
                NotifyPropertyChanged();
            }
        }

        private void NotifyPropertyChanged([CallerMemberName] String propertyName = "")
        {
            PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
        }

        public event PropertyChangedEventHandler PropertyChanged;

        public CommandDemoViewModel()
        {
            OkButton();
            CancelButton();
            this.Background = Color.Accent;
        }

        private void OkButton()
        {
            this.Background = Color.Green;
        }

        private void CancelButton()
        {
            this.Background = Color.Red;
        }
        public ICommand OkCommand => new Command(OkButton);

        public ICommand CancelCommand => new Command(CancelButton);
    }
}

{% endhighlight %}

{% endtabs %}

### Customization of footer

This feature allows the users to have a custom view in the footer part of the control in Date Picker.

{% tabs %}

{% highlight xaml %}

<ContentPage.Content>
        <StackLayout>
            <datePicker:SfDatePicker
                ShowFooter="True"
                WidthRequest="350"
                HeightRequest="350">                
            <datePicker:SfDatePicker.FooterView>
                    <StackLayout>
                        <Button Text="Accept" FontSize="Medium" FontAttributes="Bold"/>
                    </StackLayout>
                </datePicker:SfDatePicker.FooterView>
            </datePicker:SfDatePicker>
        </StackLayout>
</ContentPage.Content>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
namespace Sample
{
    [XamlCompilation(XamlCompilationOptions.Compile)]
    public partial class DatePicker : ContentPage
    {
        SfDatePicker datePicker;
        public DatePicker()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            datePicker = new SfDatePicker();
            datePicker.ShowFooter = true;
            datePicker.FooterView = new Button() { Text = "Accept" };
            stackLayout.Children.Add(datePicker);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Selected item customization

SfTimePicker allows customizing the SelectedItems's background, text color, and fonts.

### Background

Background color of the SelectedItem can be customized by setting the `SfTimePicker.SelectionBackgroundColor` property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 SelectionBackgroundColor="Yellow"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                SelectionBackgroundColor = Color.Yellow
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Text-Color 

Text color of the SelectedItem can be customized by setting the `SfTimePicker.SelectedItemTextColor` property.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 SelectedItemTextColor="Red"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                SelectedItemTextColor = Color.Red
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}
{% endtabs %}

### Font 

This section explains about the Font customization of SelectedItem text.

#### FontFamily

FontFamily of the SelectedItem text can be customized by setting the `SfTimePicker.SelectedItemFontFamily` property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 SelectedItemFontFamily="Times New Roman"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                SelectedItemFontFamily = "Times New Roman"
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

#### FontSize

FontSize of the SelectedItem text can be customized by setting the `SfTimePicker.SelectedItemFontSize` property.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 SelectedItemFontSize="18"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                SelectedItemFontSize = 18
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}   

#### FontAttribute

FontAttribute of the SelectedItem text can be customized by setting the `SfTimePicker.SelectedItemFontAttribute` property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 SelectedItemFontAttribute="Italic"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                SelectedItemFontAttribute = FontAttributes.Italic
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Unselected item customization

SfTimePicker allows customizing the Unselected item's text color, and fonts.

### Text-Color 

Text color of the unselected item can be customized by setting the `SfTimePicker.UnselectedItemTextColor` property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 UnselectedItemTextColor="Green"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                UnselectedItemTextColor = Color.Green
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Font 

This section explains about the Font customization of unselected item text.

#### FontFamily

FontFamily of the unselected item text can be customized by setting the `SfTimePicker.UnselectedItemFontFamily` property.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                UnselectedItemFontFamily="Arial"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                UnselectedItemFontFamily = "Arial"
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

#### FontSize

FontSize of the unselected item text can be customized by setting `SfTimePicker.UnselectedItemFontSize` property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 UnselectedItemFontSize="16"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                UnselectedItemFontSize = 16
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}   

#### FontAttribute

FontAttribute of the unselected item text can be customized by setting the `SfTimePicker.UnselectedItemFontAttribute` property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 UnselectedItemFontAttribute="Bold"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                UnselectedItemFontAttribute = FontAttributes.Bold
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

