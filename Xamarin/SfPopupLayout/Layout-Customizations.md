---
layout: post
title: Popup Layouts | SfPopupLayout |Xamarin | Syncfusion
description: Built-in layouts and border customization options available in Xamarin.Forms PopupLayout.
platform: Xamarin
control: SfPopupLayout
documentation: ug
--- 

# Layout Customizations

The SfPopupLayout supports two types of [SfPopupLayout.PopupView.AppearanceMode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.AppearanceMode.html). By default, the `AppearanceMode.OneButton` is set. You can change the appearance by using the `SfPopupLayout.PopupView.AppearanceMode` property.

The two different appearance modes in the SfPopupLayout are as follows:

<table>
<tr>
<th> Modes </th>
<th> Description </th>
</tr>
<tr>
<td> {{'[OneButton](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.AppearanceMode.html)'| markdownify }} </td>
<td> Shows the SfPopupLayout with one button in the footer view. This is the default value.</td>
</tr>
<tr>
<td> {{'[TwoButton](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.AppearanceMode.html)'| markdownify }} </td>
<td> Shows the SfPopupLayout with two buttons in the footer view.</td>
</tr>
</table>

## Popup with one button in the footer

In the following code example, set the `SfPopupLayout.PopupView.AppearanceMode` property as `OneButton` which displays only the Accept button in the footer view.

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popupLayout">
   <sfPopup:SfPopupLayout.PopupView>
            <sfPopup:PopupView AppearanceMode="OneButton" />
   </sfPopup:SfPopupLayout.PopupView>
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" Clicked += ClickToShowPopup_Clicked/>
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();           
            // Setting the AppearanceMode as OneButton
            popupLayout.PopupView.AppearanceMode = AppearanceMode.OneButton;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
             popupLayout.Show();
        }
    }
}
{% endhighlight %}

Executing the above codes renders the following output in iOS, Android and Windows Phone devices respectively.

![Popup with one button](GettingStarted_images/AppearanceMode_OneButton.png)

## Popup with two buttons in the footer

In the following code example, set the `SfPopupLayout.PopupView.AppearanceMode` property as `TwoButton` which displays both Accept button and Decline button in the footer view.

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popupLayout">
    <sfPopup:SfPopupLayout.PopupView>
            <sfPopup:PopupView AppearanceMode="TwoButton" />
    </sfPopup:SfPopupLayout.PopupView>
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" Clicked="ClickToShowPopup_Clicked" />
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
          
            // Setting the AppearanceMode as TwoButton
            popupLayout.PopupView.AppearanceMode = AppearanceMode.TwoButton;        
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
             popupLayout.Show();
        }
    }
}

{% endhighlight %}

Executing the above codes renders the following output in iOS, Android and Windows Phone devices respectively.

![Popup with two button](GettingStarted_images/AppearanceMode_TwoButton.png)

## Popup without header

You can display the Popup without header by using the property, [SfPopupLayout.PopupView.ShowHeader](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~ShowHeader.html), find the code example of the same below.

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popupLayout">
   <sfPopup:SfPopupLayout.PopupView>
            <sfPopup:PopupView ShowHeader="False"/>
   </sfPopup:SfPopupLayout.PopupView>
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" Clicked += ClickToShowPopup_Clicked/>
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();                       
            popupLayout.PopupView.ShowHeader = false;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
             popupLayout.Show();
        }
    }
}

{% endhighlight %}

![Popup without header](PopupLayout_images/ShowHeader_False.png)

## Popup without Footer

You can display the Popup without footer by using the property, [SfPopupLayout.PopupView.ShowFooter](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~ShowFooter.html), find the code example of the same below.

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popupLayout">
   <sfPopup:SfPopupLayout.PopupView>
            <sfPopup:PopupView ShowFooter="False"/>
   </sfPopup:SfPopupLayout.PopupView>
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" Clicked += ClickToShowPopup_Clicked/>
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();                       
            popupLayout.PopupView.ShowFooter = false;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
             popupLayout.Show();
        }
    }
}
{% endhighlight %}

![Popup without footer](PopupLayout_images/ShowFooter_False.png)

## Popup without header and footer

You can display only the content of the SfPopupLayout, by removing the header and footer by using [SfPopupLayout.PopupView.ShowHeader](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~ShowHeader.html) and [SfPopupLayout.PopupView.ShowFooter](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~ShowFooter.html), code example of the same below.

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popupLayout">
   <sfPopup:SfPopupLayout.PopupView>
            <sfPopup:PopupView ShowFooter="False" ShowHeader="False"/>
   </sfPopup:SfPopupLayout.PopupView>
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" Clicked += ClickToShowPopup_Clicked/>
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();                       
            popupLayout.PopupView.ShowFooter = false;
            popupLayout.PopupView.ShowHeader = false;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
             popupLayout.Show();
        }
    }
}
{% endhighlight %}

## Customizing popup header

Any view can be added as the header content using the [SfPopupLayout.PopupView.HeaderTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~HeaderTemplate.html) property. Refer to the following code example in which a label is added as a header content.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
 <sfPopup:SfPopupLayout x:Name="popupLayout">
  <sfPopup:SfPopupLayout.PopupView>
        <sfPopup:PopupView ShowCloseButton="False">
            <sfPopup:PopupView.HeaderTemplate>
                <DataTemplate>
                    <Label Text="Customized Header" 
                               FontAttributes="Bold"
                               BackgroundColor="Blue"
                               FontSize="16"
                               HorizontalTextAlignment="Center"
                               VerticalTextAlignment="Center"
                               />
                </DataTemplate>
            </sfPopup:PopupView.HeaderTemplate>
        </sfPopup:PopupView>
    </sfPopup:SfPopupLayout.PopupView>
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        DataTemplate headerTemplateView;
        Label headerContent;

        public MainPage()
        {
            InitializeComponent();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
            headerTemplateView = new DataTemplate(() =>
            {
                headerContent = new Label();
                headerContent.Text = "Customized Header";
                headerContent.FontAttributes = FontAttributes.Bold;
                headerContent.BackgroundColor = Color.FromRgb(0, 0, 225);
                headerContent.FontSize = 16;
                headerContent.HorizontalTextAlignment = TextAlignment.Center;
                headerContent.VerticalTextAlignment = TextAlignment.Center;
                return headerContent;
            });

            popupLayout.PopupView.ShowCloseButton = false;
            // Adding HeaderTemplate of the SfPopupLayout
            popupLayout.PopupView.HeaderTemplate = headerTemplateView;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            popupLayout.Show();
        }
    }
}

{% endhighlight %}

{% endtabs %}

Executing the above codes renders the following output in iOS, Android and Windows Phone devices respectively.

![Popup with header template](PopupLayout_images/HeaderTemplate.png)

## Customizing popup footer

Any view can be added as the footer content using the [SfPopupLayout.PopupView.FooterTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~ContentTemplate.html) property. Refer to the following code example in which a label is added as a footer content.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
 <sfPopup:SfPopupLayout x:Name="popupLayout">
    <sfPopup:SfPopupLayout.PopupView>
        <sfPopup:PopupView>
            <sfPopup:PopupView.FooterTemplate>
                <DataTemplate>
                    <Label Text="Customized Footer" 
                               FontAttributes="Bold"
                               BackgroundColor="Blue"
                               FontSize="16"
                               HorizontalTextAlignment="Center"
                               VerticalTextAlignment="Center"
                               />
                </DataTemplate>
            </sfPopup:PopupView.FooterTemplate>
        </sfPopup:PopupView>
    </sfPopup:SfPopupLayout.PopupView>
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        DataTemplate footerTemplateView;
        Label footerContent;

        public MainPage()
        {
            InitializeComponent();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
            footerTemplateView = new DataTemplate(() =>
            {
                footerContent = new Label();
                footerContent.Text = "Customized Footer";
                footerContent.FontAttributes = FontAttributes.Bold;
                footerContent.BackgroundColor = Color.FromRgb(0, 0, 225);
                footerContent.FontSize = 16;
                footerContent.HorizontalTextAlignment = TextAlignment.Center;
                footerContent.VerticalTextAlignment = TextAlignment.Center;
                return footerContent;
            });

            // Adding FooterTemplate of the SfPopupLayout
            popupLayout.PopupView.FooterTemplate = footerTemplateView;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            popupLayout.Show();
        }
    }
}

{% endhighlight %}

{% endtabs %}

Executing the above codes renders the following output in iOS, Android and Windows Phone devices respectively.

![Popup with footer template](PopupLayout_images/FooterTemplate.png)

## Customizing popup content

Any view can be added as popup content by using the [SfPopupLayout.PopupView.ContentTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~ContentTemplate.html) property. Refer to the following code example in which a label is added as a popup content.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
 <sfPopup:SfPopupLayout x:Name="popupLayout">
    <sfPopup:SfPopupLayout.PopupView>
        <sfPopup:PopupView>
            <sfPopup:PopupView.ContentTemplate>
                <DataTemplate>
                    <Label Text="This is SfPopupLayout" BackgroundColor="SkyBlue"
                           HorizontalTextAlignment="Center"/>
                </DataTemplate>
            </sfPopup:PopupView.ContentTemplate>
        </sfPopup:PopupView>
    </sfPopup:SfPopupLayout.PopupView>
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" 
               HorizontalOptions="FillAndExpand"  Clicked="ClickToShowPopup_Clicked" />
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        DataTemplate templateView;
        Label popupContent;

        public MainPage()
        {
            InitializeComponent();            
            templateView = new DataTemplate(() =>
            {
                popupContent = new Label();
                popupContent.Text = "This is the SfPopupLayout";
                popupContent.BackgroundColor = Color.LightSkyBlue;
                popupContent.HorizontalTextAlignment = TextAlignment.Center;
                return popupContent;
            });

            // Adding ContentTemplate of the SfPopupLayout
            popupLayout.PopupView.ContentTemplate = templateView;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            popupLayout.Show();
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Popup with custom content](GettingStarted_images/ContentView.png)

To display ListView as the content of the popup, refer [here](https://help.syncfusion.com/xamarin/sfpopuplayout/faq#show-listview-as-a-popup).

# Auto-sizing

The SfPopupLayout supports four types of [SfPopupLayout.PopupView.AutoSizeMode]. By default, the `AutoSizeMode.None` is set. You can change the AutoSizeMode by using the `SfPopupLayout.PopupView.AutoSizeMode` property.

The four different autosize modes in the SfPopupLayout are as follows:

<table>
<tr>
<th> Modes </th>
<th> Description </th>
</tr>
<tr>
<td> {{'[None]' }} </td>
<td> SfPopupView will not autosizing. This is the default value.</td>
</tr>
<tr>
<td> {{'[Both]'}} </td>
<td> SfPopupView width and height will be autosizing that is based on content template of SfPopupView</td>
</tr>
<tr>
<td> {{'[Width]'}} </td>
<td> SfPopupView width will be autosizing that is based on content template of SfPopupView</td>
</tr>
<tr>
<td> {{'[Height]'}} </td>
<td> SfPopupView height will be autosizing that is based on content template of SfPopupView</td>
</tr>
</table>

## AutoSizeMode.None

The `SfPopupView` width and height will not autosizing and this is default value of `SfPopupLayout.PopupView.AutoSizeMode` property. Refer the below code snippet the same.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:SfPopuplayout"
             x:Class="SfPopuplayout.MainPage"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
  <ContentPage.Content>
    <sfPopup:SfPopupLayout x:Name="popUpLayout">
        <sfPopup:SfPopupLayout.PopupView>
            <sfPopup:PopupView AutoSizeMode="None">
                <sfPopup:PopupView.ContentTemplate>
                    <DataTemplate>
                        <StackLayout Padding="5,5,5,0">
                            <Label Text="Window loads under the parent window surrounded by an overlay which prevents clicking anywhere else on the screen apart from the control of the modal. Modal opens in the same window. It also does not require any user action to open, and give callbacks when closing or opening the modal."
                            BackgroundColor="White"
                            LineBreakMode="WordWrap"
                           />
                        </StackLayout>
                    </DataTemplate>
                </sfPopup:PopupView.ContentTemplate>
            </sfPopup:PopupView>
        </sfPopup:SfPopupLayout.PopupView>
        <sfPopup:SfPopupLayout.Content>
            <StackLayout x:Name="mainLayout">
                <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
            </StackLayout>
        </sfPopup:SfPopupLayout.Content>
    </sfPopup:SfPopupLayout>
  </ContentPage.Content>
</ContentPage>



{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.PopupLayout;
namespace SfPopuplayout
{
	public partial class MainPage : ContentPage
	{
        public MainPage()
        {
            InitializeComponent();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
            popUpLayout.PopupView.AutoSizeMode = AutoSizeMode.None;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            popUpLayout.Show();
        }

    }
}

{% endhighlight %}

{% endtabs %}

## AutoSizeMode.Both

The `SfPopupView` width and height will be autosizing and that size based on content template of `SfPopupView`. Refer the below code snippet the same.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:SfPopuplayout"
             x:Class="SfPopuplayout.MainPage"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
  <ContentPage.Content>
    <sfPopup:SfPopupLayout x:Name="popUpLayout">
        <sfPopup:SfPopupLayout.PopupView>
            <sfPopup:PopupView AutoSizeMode="Both">
                <sfPopup:PopupView.ContentTemplate>
                    <DataTemplate>
                        <StackLayout Padding="5,5,5,0">
                            <Label Text="Window loads under the parent window surrounded by an overlay which prevents clicking anywhere else on the screen apart from the control of the modal. Modal opens in the same window. It also does not require any user action to open, and give callbacks when closing or opening the modal."
                            BackgroundColor="White"
                            LineBreakMode="WordWrap"
                           />
                        </StackLayout>
                    </DataTemplate>
                </sfPopup:PopupView.ContentTemplate>
            </sfPopup:PopupView>
        </sfPopup:SfPopupLayout.PopupView>
        <sfPopup:SfPopupLayout.Content>
            <StackLayout x:Name="mainLayout">
                <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
            </StackLayout>
        </sfPopup:SfPopupLayout.Content>
    </sfPopup:SfPopupLayout>
  </ContentPage.Content>
</ContentPage>



{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.PopupLayout;
namespace SfPopuplayout
{
	public partial class MainPage : ContentPage
	{
        public MainPage()
        {
            InitializeComponent();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
            popUpLayout.PopupView.AutoSizeMode = AutoSizeMode.Both;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            popUpLayout.Show();
        }

    }
}

{% endhighlight %}

{% endtabs %}

## AutoSizeMode.Height

The `SfPopupView` height only will be autosizing and that size based on content template height of `SfPopupView`. Refer the below code snippet the same.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:SfPopuplayout"
             x:Class="SfPopuplayout.MainPage"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
  <ContentPage.Content>
    <sfPopup:SfPopupLayout x:Name="popUpLayout">
        <sfPopup:SfPopupLayout.PopupView>
            <sfPopup:PopupView AutoSizeMode="Height">
                <sfPopup:PopupView.ContentTemplate>
                    <DataTemplate>
                        <StackLayout Padding="5,5,5,0">
                            <Label Text="Window loads under the parent window surrounded by an overlay which prevents clicking anywhere else on the screen apart from the control of the modal. Modal opens in the same window. It also does not require any user action to open, and give callbacks when closing or opening the modal."
                            BackgroundColor="White"
                            LineBreakMode="WordWrap"
                           />
                        </StackLayout>
                    </DataTemplate>
                </sfPopup:PopupView.ContentTemplate>
            </sfPopup:PopupView>
        </sfPopup:SfPopupLayout.PopupView>
        <sfPopup:SfPopupLayout.Content>
            <StackLayout x:Name="mainLayout">
                <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
            </StackLayout>
        </sfPopup:SfPopupLayout.Content>
    </sfPopup:SfPopupLayout>
  </ContentPage.Content>
</ContentPage>



{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.PopupLayout;
namespace SfPopuplayout
{
	public partial class MainPage : ContentPage
	{
        public MainPage()
        {
            InitializeComponent();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
            popUpLayout.PopupView.AutoSizeMode = AutoSizeMode.Height;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            popUpLayout.Show();
        }

    }
}

{% endhighlight %}

{% endtabs %}

Executing the above codes renders the following output in Android devices respectively.

![PopupView with autoSize as height](PopupLayout_images/PopupView_AutoSize_Height.jpg)

## AutoSizeMode.Width

The `SfPopupView` width only will be autosizing and that size based on content template width of `SfPopupView`. Refer the below code snippet the same.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:SfPopuplayout"
             x:Class="SfPopuplayout.MainPage"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
  <ContentPage.Content>
        <sfPopup:SfPopupLayout x:Name="popUpLayout">
            <sfPopup:SfPopupLayout.PopupView>
                <sfPopup:PopupView AutoSizeMode="Width" HeaderTitle="Modal Window">
                    <sfPopup:PopupView.ContentTemplate>
                        <DataTemplate>
                            <StackLayout Padding="5,5,5,0">
                                <Label Text="Window loads under the parent window surrounded by an overlay which prevents clicking anywhere else on the screen apart from the control of the modal. Modal opens in the same window. It also does not require any user action to open, and give callbacks when closing or opening the modal."
                            BackgroundColor="White"
                            LineBreakMode="WordWrap"
                            WidthRequest="350"
                           />
                            </StackLayout>
                        </DataTemplate>
                    </sfPopup:PopupView.ContentTemplate>
                </sfPopup:PopupView>
            </sfPopup:SfPopupLayout.PopupView>
            <sfPopup:SfPopupLayout.Content>
                <StackLayout x:Name="mainLayout">
                    <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
                </StackLayout>
            </sfPopup:SfPopupLayout.Content>
        </sfPopup:SfPopupLayout>
    </ContentPage.Content>
</ContentPage>



{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.PopupLayout;
namespace SfPopuplayout
{
	public partial class MainPage : ContentPage
	{
        public MainPage()
        {
            InitializeComponent();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
            popUpLayout.PopupView.AutoSizeMode = AutoSizeMode.Width;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            popUpLayout.Show();
        }
    }
}

{% endhighlight %}

{% endtabs %}

Executing the above codes renders the following output in Android devices respectively.

![PopupView with autoSize as width](PopupLayout_images/PopupView_AutoSize_Width.jpg)

Sample Link: You can download the above sample code by clicking [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/AutoSize_SfPopuplayout1703576210).
