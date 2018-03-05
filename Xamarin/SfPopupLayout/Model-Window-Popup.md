---
layout: post
title: Model Window Popup | SfPopupLayout |Xamarin| Syncfusion
description: Model Window Popup with SfPopupLayout
platform: Xamarin
control: SfPopupLayout
documentation: ug
--- 

# Model Window Popup

You can use pop-up layout as model window by using the built-in close icon and [SfPopupLayout.StaysOpen](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~StaysOpenProperty.html) property to prevent the user from interacting with your application until they close the window.

Model Window will loads under the parent window surrounded by the overlay which prevents users to click anywhere else on screen other then the content of the modal.

Modal also doesn't require any user action to open.

Modal opens in the same window.

Modal gives callbacks when you close or open the modal.

Refer the below code example in which popup will close only if you click cancel button, ok button or close icon.

## Displaying Popup when SfPopupLayout is set as root view :

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
 <sfPopup:SfPopupLayout x:Name="popUpLayout">
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
                popupContent.Text = "Window which loads under the parent window surrounded by the overlay which prevents users to click anywhere else on screen other then the content of the modal.Modal also doesn't require any user action to open.Modal opens in the same window.Modal gives callbacks when you close or open the modal.";
                popupContent.WidthRequest = 260;
                popupContent.BackgroundColor = Color.White;
                popupContent.HorizontalOptions = LayoutOptions.FillAndExpand;
                return popupContent;
            });

            popupLayout.PopupView.HeightRequest = 270;
            popupLayout.PopupView.AppearanceMode = AppearanceMode.TwoButton;
            popupLayout.PopupView.AcceptButtonText = "OK";
            popupLayout.PopupView.DeclineButtonText = "Cancel";
            popupLayout.PopupView.HeaderTitle = "Model Window";
            popupLayout.PopupView.ContentTemplate = contentTemplateView;

            popupLayout.PopupView.AcceptCommand = new AcceptButtonCustomCommand();
            popupLayout.PopupView.DeclineCommand = new DeclineButtonCustomCommand();

            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            // Below code ensures that the popup doesnot collapse when user interacts outside the popup.
            popupLayout.StaysOpen = true;
            popupLayout.PopupView.ShowCloseButton = true;
            popupLayout.IsOpen = true;            
        }
    }
}
{% endhighlight %}

{% highlight c# %}

//AcceptButtonCustomCommand

public class AcceptButtonCustomCommand : ContentPage, ICommand
{
    event EventHandler ICommand.CanExecuteChanged
    {
        add
        {
           
        }
        remove
        {
           
        }
    }
    bool ICommand.CanExecute(object parameter)
    {
        // Returning true allows the popup to collapse.
        return true;
    }
    void ICommand.Execute(object parameter)
    {
      
    }
}

{% endhighlight %}

{% highlight c# %}

//DeclineButtonCustomCommand

public class DeclineButtonCustomCommand : ContentPage, ICommand
{
    event EventHandler ICommand.CanExecuteChanged
    {
        add
        {
           
        }
        remove
        {
           
        }
    }
    bool ICommand.CanExecute(object parameter)
    {
        // Returning true allows the popup to collapse.
        return true;
    }
    void ICommand.Execute(object parameter)
    {
      
    }
}

{% endhighlight %}

This is how the final output will look like on iOS device.
![](GettingStarted_images/ModelView_iOS.png)