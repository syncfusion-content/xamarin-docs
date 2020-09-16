---
layout: post
title: Popup positioning | SfPopupLayout |Xamarin| Syncfusion
description: Position the popup at the center, absolute postion, relative to another view and relative with absolute postion using the Xamarin.Forms PopupLayout.
platform: Xamarin
control: SfPopupLayout
documentation: ug
--- 

# Popup Positioning

The SfPopupLayout allows showing the popup content at various available positions.

Following are the list of options available to show SfPopupLayout at various positions.

<table>
<tr>
<th> Methods / Properties </th>
<th> Description </th>
</tr>
<tr>
<td> {{'[SfPopupLayout.IsOpen](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html#Syncfusion_XForms_PopupLayout_SfPopupLayout_IsOpen)'| markdownify }} </td>
<td> Shows the `SfPopupLayout` at center.</td>
</tr>
<tr>
<td> {{'[SfPopupLayout.Show](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html#Syncfusion_XForms_PopupLayout_SfPopupLayout_Show_System_Boolean_)'| markdownify }} </td>
<td> Similar as <code>SfPopupLayout.IsOpen</code> property.</td>
</tr>
<tr>
<td> {{'[SfPopupLayout.Show(x-position, y-position)](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html#Syncfusion_XForms_PopupLayout_SfPopupLayout_Show_System_Boolean_)'| markdownify }} </td>
<td> Shows the `SfPopupLayout` at the specified X and y positions.</td>
</tr>
<tr>
<td> {{'[SfPopupLayout.ShowAtTouchPoint()](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html#Syncfusion_XForms_PopupLayout_SfPopupLayout_ShowAtTouchPoint)'| markdownify }} </td>
<td> Shows the `SfPopupLayout` at the touch point.</td>
</tr>
<tr>
<td> {{'[SfPopupLayout.ShowRelativeToView(View, RelativePosition)](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html#Syncfusion_XForms_PopupLayout_SfPopupLayout_ShowRelativeToView_Xamarin_Forms_View_Syncfusion_XForms_PopupLayout_RelativePosition_System_Double_System_Double_)'| markdownify }} </td>
<td> Shows the `SfPopupLayout` at the position relative to the specified view.</td>
</tr>
<tr>
<td> {{'[SfPopupLayout.ShowRelativeToView(View, RelativePosition,x-position,y-position)](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html#Syncfusion_XForms_PopupLayout_SfPopupLayout_ShowRelativeToView_Xamarin_Forms_View_Syncfusion_XForms_PopupLayout_RelativePosition_System_Double_System_Double_)'| markdownify }} </td>
<td> Shows the `SfPopupLayout` at an absolute x, y coordinate from the relative position of the specified view.</td>
</tr>
<tr>
<td> {{'[SfPopupLayout.PopupView.IsFullScreen](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.PopupView.html#Syncfusion_XForms_PopupLayout_PopupView_IsFullScreen)'| markdownify }} </td>
<td> Shows the `SfPopupLayout` in full width and height of the screen.</td>
</tr>
<td> {{'[SfPopupLayout.Show(bool)](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html#Syncfusion_XForms_PopupLayout_SfPopupLayout_Show_System_Boolean_)'| markdownify }} </td>
<td> Similar as <code>SfPopupLayout.PopupView.IsFullScreen</code> property. </td>
</tr>
</table>

## Center positioning

SfPopupLayout can be shown at the center by using the following options.

  * [IsOpen property](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html#Syncfusion_XForms_PopupLayout_SfPopupLayout_IsOpen)
  * [SfPopupLayout.Show](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html#Syncfusion_XForms_PopupLayout_SfPopupLayout_Show_System_Boolean_)

To open the SfPopupLayout, use the `SfPopupLayout.IsOpen` property as in the following code sample.

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popupLayout">
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" 
               VerticalOptions="Start"   HorizontalOptions="FillAndExpand" Clicked="ClickToShowPopup_Clicked" />
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
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            // Shows SfPopupLayout at the center of the view.
            popupLayout.IsOpen = true;
        }
    }
}
{% endhighlight %}

Executing the above codes renders the following output in iOS, Android and Windows Phone devices respectively.

![Popup with center positioning](GettingStarted_images/IsOpen_Property.png)

To open the SfPopupLayout, use the [SfPopupLayout.Show](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html#Syncfusion_XForms_PopupLayout_SfPopupLayout_Show_System_Boolean_) method as in the following code sample.

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popupLayout">
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" 
               VerticalOptions="Start"  HorizontalOptions="FillAndExpand" Clicked="ClickToShowPopup_Clicked" />
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
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
           // Shows SfPopupLayout at the center of the view.
           popupLayout.Show();
        }
    }
}
{% endhighlight %}

Executing the above codes renders the following output in iOS, Android and Windows Phone devices respectively.

![Popup with default look](GettingStarted_images/ShowPopup.png)

## Absolute positioning

To open the SfPopupLayout in specific X,Y coordinates, use the `SfPopupLayout.Show(x-position, y-position)` property as in the following code sample.

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popupLayout">
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" 
               VerticalOptions="Start" HorizontalOptions="FillAndExpand" Clicked="ClickToShowPopup_Clicked" />
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
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
           // Shows SfPopupLayout at x-position 100 and y position 100.
           popupLayout.Show(100, 700);
        }
    }
}
{% endhighlight %}

Executing the above codes renders the following output in iOS, Android and Windows Phone devices respectively.

![Absolute positioning of Popup](GettingStarted_images/ShowAtXYPosition.png)

## Position popup at touch point

To open the SfPopupLayout from the touch point in the screen, use the [SfPopupLayout.ShowAtTouchPoint](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html#Syncfusion_XForms_PopupLayout_SfPopupLayout_ShowAtTouchPoint) method as in the following code sample.

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popupLayout">
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" 
               VerticalOptions="Start" HorizontalOptions="FillAndExpand" Clicked="ClickToShowPopup_Clicked" />
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
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            // Shows SfPopupLayout at the touch point.
            popupLayout.ShowAtTouchPoint();
        }
    }
}
{% endhighlight %}

Executing the above codes renders the following output in iOS, Android and Windows Phone devices respectively.

![Showing Popup at touch point](GettingStarted_images/ShowAtTouchPoint.png)

N> Positioning popup at touch point is not supported when using the approach of `Displaying popup on the fly`.

## Relative positioning

SfPopupLayout can be shown at the relative position by using the following method.

### Display popup relative to a view

To open the SfPopupLayout relative to a view, use the `SfPopupLayout.ShowRelativeToView(View, RelativePosition,x-position,y-position)` method.

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popupLayout">
   <sfPopup:SfPopupLayout.Content>
    <StackLayout x:Name="mainLayout" VerticalOptions="Center" HorizontalOptions="Center">
        <StackLayout VerticalOptions="CenterAndExpand" HorizontalOptions="StartAndExpand">
          <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" TextColor="White" 
                  HeightRequest="60" VerticalOptions="Center" Margin="100,0,0,0" HorizontalOptions="Center" BackgroundColor="Blue" Clicked="ClickToShowPopup_Clicked"/>
        </StackLayout>
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
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
           // Shows SfPopupLayout at the bottom of the label.
           popupLayout.ShowRelativeToView(label, RelativePosition.AlignBottom, 0, 0);
        }
    }
}

{% endhighlight %}

Executing the above codes renders the following output in iOS, Android and Windows Phone devices respectively.

![Relative positioning of Popup](GettingStarted_images/RelativeToBottom.png)

### Display popup relatively to a view with absolute coordinates

The SfPopupLayout can be displayed at an absolute x, y coordinate from the relative position of the specified view by using the following method.

To open the SfPopupLayout in the specific x, y coordinate relative to a view, use the `SfPopupLayout.ShowRelativeToView(View, RelativePosition,x-position,y-position)` method.

 {% tabs %}
 {% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,200,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popupLayout">
   <sfPopup:SfPopupLayout.Content>
    <StackLayout x:Name="mainLayout" VerticalOptions="StartAndExpand" HorizontalOptions="Start">
        <StackLayout VerticalOptions="StartAndExpand" HorizontalOptions="StartAndExpand">
          <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" TextColor="White" 
                  HeightRequest="60" VerticalOptions="Start" Margin="50,0,0,0" HorizontalOptions="StartAndExpand" BackgroundColor="Blue" 
                  Clicked="ClickToShowPopup_Clicked"/>
        </StackLayout>
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            // Shows SfPopupLayout at the bottom of the label and with absolute relative position.
              popupLayout.ShowRelativeToView(label, RelativePosition.AlignBottom,50,50);
        }
    }
}
{% endhighlight %}
{% endtabs %}

![Absolute positioning of Popup](GettingStarted_images/AbsoluteRelativePosition.png)

You can pass both negative and positive values as parameters to the `SfPopupLayout.ShowRelativeToView(View, RelativePosition, x-position, y-position)`. The popup will be positioned by considering the relative position as (0, 0) the center point. For example, if you have set the `RelativePosition` as `RelativePosition.BottomRight` and `RelativeView` as a button, bottom right corner of the button will be considered as the 0, 0 point and a negative x-position value will place the popup to the left of that point and a positive x-position value will place the popup to the right of that point. The same applies for y-position also.

N> To open the SfPopupLayout relative to a view without absolute position, pass the x-position and y-position parameters as 0 in `SfPopupLayout.ShowRelativeToView(View, RelativePosition,x-position,y-position)`.

### Show relative to view in MVVM

To open the SfPopupLayout relative to a view in MVVM assign values to the `SfPopupLayout.RelativeView` and `SfPopup.RelativePosition` properties and use the `SfPopupLayout.IsOpen` property to open or close the popup using binding.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">

<ContentPage.BindingContext>
    <local:ViewModel x:Name="viewModel" />
</ContentPage.BindingContext>
    
<ContentPage.Content>
    <sfPopup:SfPopupLayout x:Name="popupLayout" IsOpen="{Binding DisplayPopup}" RelativePosition="AlignBottom" AbsoluteX="0" AbsoluteY="0">
        <sfPopup:SfPopupLayout.Content>
            <StackLayout >
                <Label x:Name="relativeView" Text="Showing Popup at relative position in MVVM" VerticalOptions="StartAndExpand" HorizontalOptions="FillAndExpand" HorizontalTextAlignment="Center" HeightRequest="60" LineBreakMode="WordWrap" FontSize="Medium" BackgroundColor="Blue" TextColor="White"/>
            </StackLayout>
        </sfPopup:SfPopupLayout.Content>
        <sfPopup:SfPopupLayout.RelativeView>
            <x:Reference Name="relativeView"/>
        </sfPopup:SfPopupLayout.RelativeView>
    </sfPopup:SfPopupLayout>
</ContentPage.Content>

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
        }

        protected override void OnAppearing()
        {
            base.OnAppearing();
            viewModel.DisplayPopup = true;
        }
    }
}
{% endhighlight %}
{% endtabs %}

// ViewModel
public class ViewModel: INotifyPropertyChanged
{
    private bool displayPopup;

    public  bool DisplayPopup
    {
        get { return displayPopup; }
        set { displayPopup = value; RaisePropertyChanged("DisplayPopup"); }
    }

    public ViewModel()
    {
        this.displayPopup = false;
    }

    public void RaisePropertyChanged(string propName)
    {
        if (this.PropertyChanged != null)
            this.PropertyChanged(this, new PropertyChangedEventArgs(propName));
    }

    public event PropertyChangedEventHandler PropertyChanged;
}

Executing the above codes renders the following output in Android device respectively.

![Relative positioning of Popup in MVVM](PopupLayout_images/ShowingPopupAtRelativePositionInMVVM.jpg)

## Display the popup with Padding

The SfPopupLayout allows users to set padding for the PopupView when the space between the popup and the screen is less than the minimum padding value of 5 pixels. The custom padding value set in the sample will not apply when the space between the popup and the screen is already greater than 5 pixels. For cases where you want to position your popup farther away from the screen use the [SfPopupLayout.Show(double,double)](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html#Syncfusion_XForms_PopupLayout_SfPopupLayout_Show_System_Double_System_Double_) as shown [here](https://help.syncfusion.com/xamarin/sfpopuplayout/popup-positioning#absolute-positioning).

{% tabs %}
{% highlight xaml %}
    <ContentPage.Content>
        <sfPopup:SfPopupLayout x:Name="popupLayout" Padding="15,15,15,15">
            <sfPopup:SfPopupLayout.PopupView>
                <sfPopup:PopupView AppearanceMode="TwoButton"
                                   IsFullScreen="True"
                                   AcceptButtonText="SAVE"
                                   DeclineButtonText="CANCEL"
                                   HeaderTemplate="{StaticResource HeaderViewTemplate}"
                                   ContentTemplate="{StaticResource ContentViewTemplate}"/>
            </sfPopup:SfPopupLayout.PopupView>
            <sfPopup:SfPopupLayout.Content>
                <StackLayout x:Name="layout">
                    <Button x:Name="clickToShowPopup" Text="ClickToShowPopup"  Clicked="ClickToShowPopup_Clicked" />
                </StackLayout>
            </sfPopup:SfPopupLayout.Content>
        </sfPopup:SfPopupLayout>
    </ContentPage.Content>
{% endhighlight %}

{% highlight c# %}
            SfPopupLayout popupLayout = new SfPopupLayout();
            popupLayout.Padding = new Thickness(15, 15, 15, 15);
            popupLayout.PopupView.IsFullScreen = true;
            popupLayout.PopupView.HeaderTemplate = GetHeaderTemplate();
            popupLayout.PopupView.ContentTemplate = GetContentTemplate();
{% endhighlight %}
{% endtabs %}

![Popup with Padding](PopupLayout_images/SfPopupLayoutPadding_Android.png)