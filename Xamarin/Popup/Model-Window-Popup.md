---
layout: post
title: Modal Window Popup | SfPopupLayout |Xamarin| Syncfusion
description: Use the Xamarin.Forms PopupLayout as Modal Window restricting user interaction with your application until closing the window.
platform: Xamarin
control: SfPopupLayout
documentation: ug
--- 

# Modal Window Popup in Xamarin.Forms

You can use popup layout as modal window by using the built-in Close icon and the [SfPopupLayout.StaysOpen](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html#Syncfusion_XForms_PopupLayout_SfPopupLayout_StaysOpenProperty) property prevents interaction with your application until you close the window.

`Modal`: Window loads under the parent window surrounded by an overlay which prevents clicking anywhere else on the screen apart from the control of the modal.

Modal does not require any action to open. It opens in the same window and gives callbacks when closing or opening the window.

Refer to the following code example in which the popup will close only if you click on Close icon.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
 <sfPopup:SfPopupLayout x:Name="popUpLayout" StaysOpen="True">
    <sfPopup:SfPopupLayout.PopupView>
        <sfPopup:PopupView HeightRequest="230"
                           HeaderTitle="Modal Window"
                           ShowFooter="False">
            <sfPopup:PopupView.ContentTemplate>
                <DataTemplate>
                    <Label Text="Window loads under the parent window surrounded by an 
                           overlay which prevents clicking anywhere else on the screen 
                           apart from the control of the modal. Modal opens in the same 
                           window. It also does not require any user action to open, and 
                           give callbacks when closing or opening the modal."
                           WidthRequest="260"
                           BackgroundColor="White"
                           HorizontalOptions="FillAndExpand"
                           />
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
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        DataTemplate contentTemplateView;
        Label popupContent;

        public MainPage()
        {
            InitializeComponent();
            contentTemplateView = new DataTemplate(() =>
            {
                popupContent = new Label();
                popupContent.Text = "Window loads under the parent window surrounded by an overlay which prevents clicking anywhere else on the screen apart from the control of the modal. Modal opens in the same window. It also does not require any user action to open, and give callbacks when closing or opening the modal.";
                popupContent.WidthRequest = 260;
                popupContent.BackgroundColor = Color.White;
                popupContent.HorizontalOptions = LayoutOptions.FillAndExpand;
                return popupContent;
            });

            popupLayout.PopupView.HeightRequest = 230;
            popupLayout.PopupView.HeaderTitle = "Modal Window";
            popupLayout.PopupView.ContentTemplate = contentTemplateView;
            popupLayout.PopupView.ShowFooter = false;

            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            // Below code ensures that the popup doesn't collapse when user interacts outside the popup.
            popupLayout.StaysOpen = true;
            popupLayout.PopupView.ShowCloseButton = true;
            popupLayout.IsOpen = true;            
        }
    }
}

{% endhighlight %}

{% endtabs %}

Executing the above codes renders the following output in iOS, Android and Windows Phone devices respectively.

![Popup as ModelWindow](GettingStarted_images/ModelWindow.png)