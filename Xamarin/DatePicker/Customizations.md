---
layout: post
title: Customizations in Xamarin DatePicker control | Syncfusion
description: Learn here all about Customizations support in Syncfusion Xamarin DatePicker (SfDatePicker) control and more.
platform: Xamarin
control: Picker
documentation: ug
---

# Customizations in Xamarin DatePicker (SfDatePicker)

You can customize the header, column header, footer, selected item, and unselected item of the SfDatePicker.

## Header customization

SfDatePicker allows customizing the header's background, text color, and fonts.

### Enable or disable header 

SfDatePicker allows enabling or disabling the header section by setting the [`SfDatePicker.ShowHeader`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_ShowHeader) property to True or False. The default value of [`SfDatePicker.ShowHeader`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_ShowHeader) property is "True".

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 ShowHeader="False"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                ShowHeader = false
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Set header text

SfDatePicker allows providing custom text to its header by setting the [`SfDatePicker.HeaderText`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html#Syncfusion_XForms_Pickers_SfDatePicker_HeaderText) property. The default value of [`SfDatePicker.HeaderText`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html#Syncfusion_XForms_Pickers_SfDatePicker_HeaderText) property is "Date Picker".

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 HeaderText="Select a date"/>
    </ContentPage.Content>
</ContentPage>
 
{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                HeaderText = "Select a date"
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Background

Background color of the header can be customized by setting the [`SfDatePicker.HeaderBackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_HeaderBackgroundColor) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 HeaderBackgroundColor="SkyBlue"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                HeaderBackgroundColor = Color.SkyBlue
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Text color 

Text color of the header can be customized by setting the [`SfDatePicker.HeaderTextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_HeaderTextColor) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 HeaderTextColor="Red"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                HeaderTextColor = Color.Red; 
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Font 

This section explains the Font customization of header text.

#### FontFamily

FontFamily of the header text can be customized by setting the [`SfDatePicker.HeaderFontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_HeaderFontFamily) property.

{% tabs %}

{% highlight xaml %}

<<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 HeaderFontFamily="Times New Roman"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                HeaderFontFamily = "Times New Roman"
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

#### FontSize

FontSize of the header text can be customized by setting the [`SfDatePicker.HeaderFontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_HeaderFontSize) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 HeaderFontSize="18"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                HeaderFontSize = 18
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}   

#### FontAttribute

FontAttribute of the header text can be customized by setting the [`SfDatePicker.HeaderFontAttribute`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_HeaderFontAttribute) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 HeaderFontAttribute="Italic"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                HeaderFontAttribute = FontAttributes.Italic
            };

            this.Content = datePicker;
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

SfDatePicker allows customizing the column header's background, text color, and fonts.

### Enable or disable column header 

SfDatePicker allows enabling or disabling the column header section by setting the [`SfDatePicker.ShowColumnHeader`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_ShowColumnHeader) property to True or False. The default value of [`SfDatePicker.ShowColumnHeader`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_ShowColumnHeader) property is "True".

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 ShowColumnHeader="False"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                ShowColumnHeader = false
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Set custom column header 

SfDatePicker allows providing custom text to its column header by setting the [`SfDatePicker.DayHeaderText`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html#Syncfusion_XForms_Pickers_SfDatePicker_DayHeaderText), [`SfDatePicker.MonthHeaderText`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html#Syncfusion_XForms_Pickers_SfDatePicker_MonthHeaderText), and [`SfDatePicker.YearHeaderText`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html#Syncfusion_XForms_Pickers_SfDatePicker_YearHeaderText) properties. Default value of [`SfDatePicker.DayHeaderText`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html#Syncfusion_XForms_Pickers_SfDatePicker_DayHeaderText) property is "Day", [`SfDatePicker.MonthHeaderText`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html#Syncfusion_XForms_Pickers_SfDatePicker_MonthHeaderText) is "Month", and [`SfDatePicker.YearHeaderText`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html#Syncfusion_XForms_Pickers_SfDatePicker_YearHeaderText) is "Year".

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 DayHeaderText="Day Column"
                                 MonthHeaderText="Month Column"
                                 YearHeaderText="Year Column"/>
    </ContentPage.Content>
</ContentPage>
 
{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                DayHeaderText = "Day Column",
                MonthHeaderText = "Month Column",
                YearHeaderText = "Year Column"
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Background

Background color of the column header can be customized by setting the [`SfDatePicker.ColumnHeaderBackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_ColumnHeaderBackgroundColor) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 ColumnHeaderBackgroundColor="Green"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                ColumnHeaderBackgroundColor = Color.Green
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Text color 

Text color of the column header can be customized by setting the [`SfDatePicker.ColumnHeaderTextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_ColumnHeaderTextColor) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 ColumnHeaderTextColor="Red"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                ColumnHeaderTextColor = Color.Red
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Font 

This section explains the Font customization of column header text.

#### FontFamily

FontFamily of the column header text can be customized by setting the [`SfDatePicker.ColumnHeaderFontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_ColumnHeaderFontFamily) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 ColumnHeaderFontFamily="Times New Roman"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                ColumnHeaderFontFamily = "Times New Roman"
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

#### FontSize

FontSize of the column header text can be customized by setting the [`SfDatePicker.ColumnHeaderFontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_ColumnHeaderFontSize) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                ColumnHeaderFontSize="18"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                ColumnHeaderFontSize = 18
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}   

#### FontAttribute

FontAttribute of the column header text can be customized by setting the [`SfDatePicker.ColumnHeaderFontAttribute`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_ColumnHeaderFontAttribute) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 ColumnHeaderFontAttribute="Bold"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                ColumnHeaderFontAttribute = FontAttributes.Bold
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Footer customization

SfDatePicker allows customizing background, text color of the OK and Cancel buttons of the footer.

### Enable or disable footer 

DatePicker allows enabling or disabling the footer section by setting the [`SfDatePicker.ShowFooter`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_ShowFooter) property to True or False. The default value of [`SfDatePicker.ShowFooter`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_ShowFooter) property is "False".

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 ShowFooter="True"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                ShowFooter = true
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### OK and Cancel buttons customizations

#### Background

Background colors of the OK and Cancel buttons can be customized by setting the [`SfDatePicker.OKButtonBackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_OKButtonBackgroundColor) and [`SfDatePicker.CancelButtonBackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_CancelButtonBackgroundColor)properties.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 ShowFooter="True"
                                 OKButtonBackgroundColor="Pink"
                                 CancelButtonBackgroundColor="Pink"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                OKButtonBackgroundColor = Color.Pink,
                CancelButtonBackgroundColor = Color.Pink
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

#### Text-Color 

Text colors of the OK and Cancel buttons can be customized by setting the [`SfDatePicker.OKButtonTextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_OKButtonTextColor) and [`SfDatePicker.CancelButtonTextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_CancelButtonTextColor) properties.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 ShowFooter="True"
                                 OKButtonTextColor="Brown"
                                 CancelButtonTextColor="Brown"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                OKButtonTextColor = Color.Brown,
                CancelButtonTextColor = Color.Brown
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Perform validation with default validation button

DatePicker allows performing validation based on the OK or Cancel button by using [`SfDatePicker.OkCommand`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html#Syncfusion_XForms_Pickers_SfDatePicker_OkCommand) and [`SfDatePicker.CancelCommand`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html#Syncfusion_XForms_Pickers_SfDatePicker_CancelCommand).

The following example shows how to use the OkCommand and the CancelCommand. When you click the OK button, the background color of the selected item will change to green. When you click the Cancel button, the background color of the selected item will change to red.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.BindingContext>
        <local:CommandDemoViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
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

namespace DatePickerSample
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

SfDatePicker allows customizing the SelectedItem's background, text color, and fonts.

### Background

The background color of the SelectedItem can be customized by setting the [`SfDatePicker.SelectionBackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_SelectionBackgroundColor) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 SelectionBackgroundColor="Yellow"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                SelectionBackgroundColor = Color.Yellow
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Text color 

Text color of the SelectedItem can be customized by setting the [`SfDatePicker.SelectedItemTextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_SelectedItemTextColor) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 SelectedItemTextColor="Red"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                SelectedItemTextColor = Color.Red
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Font 

This section explains the Font customization of SelectedItem text.

#### FontFamily

FontFamily of the SelectedItem text can be customized by setting the [`SfDatePicker.SelectedItemFontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_SelectedItemFontFamily) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 SelectedItemFontFamily="Times New Roman"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                SelectedItemFontFamily = "Times New Roman"
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

#### FontSize

FontSize of the SelectedItem text can be customized by setting the [`SfDatePicker.SelectedItemFontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_SelectedItemFontSize) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 SelectedItemFontSize="18"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                SelectedItemFontSize = 18
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}   

#### FontAttribute

FontAttribute of the SelectedItem text can be customized by setting the [`SfDatePicker.SelectedItemFontAttribute`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_SelectedItemFontAttribute) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 SelectedItemFontAttribute="Italic"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                SelectedItemFontAttribute = FontAttributes.Italic
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Unselected item customization

SfDatePicker allows customizing the Unselected item's text color and fonts.

### Text-Color 

Text color of the Unselected item can be customized by setting the [`SfDatePicker.UnselectedItemTextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_UnselectedItemTextColor) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 UnselectedItemTextColor="Green"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                UnselectedItemTextColor = Color.Green
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Font 

This section explains about the Font customization of Unselected item text.

#### FontFamily

FontFamily of the Unselected item text can be customized by setting the [`SfDatePicker.UnselectedItemFontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_UnselectedItemFontFamily) property.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                UnselectedItemFontFamily="Arial"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                UnselectedItemFontFamily = "Arial"
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

#### FontSize

FontSize of the Unselected item text can be customized by setting the [`SfDatePicker.UnselectedItemFontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_UnselectedItemFontSize) property.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 UnselectedItemFontSize="16"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                UnselectedItemFontSize = 16
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}   

#### FontAttribute

FontAttribute of the Unselected item text can be customized by setting the [`SfDatePicker.UnselectedItemFontAttribute`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_UnselectedItemFontAttribute) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 UnselectedItemFontAttribute="Bold"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                UnselectedItemFontAttribute = FontAttributes.Bold
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}
