---
layout: post
title: Popup Events| SfPopupLayout |Xamarin| Syncfusion
description: Use the built-in events available in Xamarin.Forms PopupLayout to control the opening and closing of popup based on conditions or requirements.
platform: Xamarin
control: SfPopupLayout
documentation: ug
--- 

# Popup Events And Commands

There are four built-in events in the SfPopupLayout control namely:

* Opening
* Opened
* Closing
* Closed

## Opening event

The [SfPopupLayout.Opening](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html) event will be fired whenever opening the PopupView in the application. It can cancel popup opening with `CancelEventArgs` that contains the following property:

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true): Popup opening is based on this value.

{% tabs %}
{%highlight Xaml%}
<sfPopup:SfPopupLayout x:Name="popupLayout" Opening="PopupLayout_Opening"/>
{%endhighlight%}

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.Opening += PopupLayout_Opening;
    ....
}

private void PopupLayout_Opening(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

## Opened event

The [SfPopupLayout.Opened](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html) event will be fired whenever displaying the PopupView in the application.

You can execute your own set of codes once the popup is opened, and visible in the application in its respective event handler.

{% tabs %}
{%highlight Xaml%}
<sfPopup:SfPopupLayout x:Name="popupLayout" 
Opened="PopupLayout_Opened"/>
{%endhighlight%}

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.Opened += PopupLayout_Opened;
    ....
}

private void PopupLayout_Opened(object sender, EventArgs e)
{
   // Codes that needs to be executed once popup is visible in the screen.
}
{% endhighlight %}
{% endtabs %}

## Closing event

The [SfPopupLayout.Closing](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html) event will be fired whenever closing the PopupView in the application. It can cancel popup closing with `CancelEventArgs` that contains the following property:

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true): Popup opening is based on this value.

{% tabs %}
{%highlight Xaml%}
<sfPopup:SfPopupLayout x:Name="popupLayout"  Closing="PopupLayout_Closing"/>
{%endhighlight%}

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.Closing += PopupLayout_Closing;
    ....
}

private void PopupLayout_Closing(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

## Closed event

The [SfPopupLayout.Closed](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html) event will be fired whenever dismissing the PopupView from the view.

You can execute your own set of codes once the popup is completely closed in its respective event handler.

{% tabs %}
{%highlight Xaml%}
<sfPopup:SfPopupLayout x:Name="popupLayout" Closed="PopupLayout_Closed"/>
{%endhighlight%}

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.Closed += PopupLayout_Closed;
    ....
}

private void PopupLayout_Closed(object sender, EventArgs e)
{
    // Codes that needs to be executed once popup is completely closed.
}
{% endhighlight %}
{% endtabs %}

## Accept command

The [SfPopupLayout.PopupView.AcceptCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.PopupView.html#Syncfusion_XForms_PopupLayout_PopupView_AcceptCommand) will be fired when clicking the Accept button in the popup footer.

To handle the Accept button,

* Derive a class from `ICommand`, and implement the `ICommand` interface.
* To prevent popup from closing, return false in the `CanExecute()` override method and the `Execute()` override method will not be fired.
* Else return true in the `CanExecute()` override method and do the required operations in the `Execute()` method.
* Now create a property of your custom command type in the view model class and initialize it.
* Bind the property in the view model to the `SfPopupLayout.PopupView.AcceptCommand` in XAML.

{% tabs %}

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:Popup"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms"
             x:Class="Popup.MainPage">
    <ContentPage.BindingContext>
        <local:PopupViewModel/>
    </ContentPage.BindingContext>
    <sfPopup:SfPopupLayout IsOpen="{Binding PopupOpen}">
        <sfPopup:SfPopupLayout.PopupView>
            <sfPopup:PopupView AppearanceMode="TwoButton"
                          AcceptCommand="{Binding PopupAcceptCommand}"
                        DeclineCommand="{Binding PopupDeclineCommand}"   />
        </sfPopup:SfPopupLayout.PopupView>
        <sfPopup:SfPopupLayout.Content>
            <StackLayout>
                    <Button  Text="ClickToShowPopup" 
               VerticalOptions="Center"   HorizontalOptions="Center" Command="{Binding PopupCommand}" />
                </StackLayout>
            </sfPopup:SfPopupLayout.Content>
 </sfPopup:SfPopupLayout>
</ContentPage>
{% endhighlight %}

{% highlight c# %}
 //PopupViewModel.cs

 class PopupViewModel : INotifyPropertyChanged
{
        bool isOpen;
        public event PropertyChangedEventHandler PropertyChanged;
        void OnPropertyChanged(string propertyName)
        {
            PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
        }
        public ICommand PopupAcceptCommand { get; set; }
        public ICommand PopupDeclineCommand { get; set; }
        public ICommand PopupCommand { get; set; }
        public bool PopupOpen {
            get { return isOpen; }
            set
            {
                isOpen = value;
                OnPropertyChanged(nameof(PopupOpen));
            } }
        public PopupViewModel()
        {
            PopupAcceptCommand = new Command(PopupAccept); //CanExecute() will be call the PopupAccept method
            PopupDeclineCommand = new Command(PopupDecline); //CanExecute() will be call the PopupDecline method
            PopupCommand = new Command(Popup);
        }

        private void Popup()
        {
            PopupOpen = true;
        }

        private void PopupAccept()
        {
             // You can write your set of codes that needs to be executed.
        }

        private void PopupDecline()
        {
            // You can write your set of codes that needs to be executed.
        }
    }
{% endhighlight %}

{% endtabs %}

## Decline command

The [SfPopupLayout.PopupView.DeclineCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.PopupView.html#Syncfusion_XForms_PopupLayout_PopupView_DeclineCommand) will be fired when clicking the Decline button in the popup footer. 

To handle the Decline button,

* Derive a class from `ICommand`, and implement the `ICommand` interface.
* To prevent popup from closing, return false in the `CanExecute()` override method and the `Execute()` override method will not be fired.
* Else return true in the `CanExecute()` override method and do the required operations in the `Execute()` method.
* Now create a property of your custom command type in the view model class and initialize it.
* Bind the property in the view model to the `SfPopupLayout.PopupView.DeclineCommand` in XAML.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:Popup"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms"
             x:Class="Popup.MainPage">
    <ContentPage.BindingContext>
        <local:PopupViewModel/>
    </ContentPage.BindingContext>
    <sfPopup:SfPopupLayout IsOpen="{Binding PopupOpen}">
        <sfPopup:SfPopupLayout.PopupView>
            <sfPopup:PopupView AppearanceMode="TwoButton"
                          AcceptCommand="{Binding PopupAcceptCommand}"
                        DeclineCommand="{Binding PopupDeclineCommand}"   />
        </sfPopup:SfPopupLayout.PopupView>
        <sfPopup:SfPopupLayout.Content>
            <StackLayout>
                    <Button  Text="ClickToShowPopup" 
               VerticalOptions="Center"   HorizontalOptions="Center" Command="{Binding PopupCommand}" />
                </StackLayout>
            </sfPopup:SfPopupLayout.Content>
 </sfPopup:SfPopupLayout>
</ContentPage>


{% endhighlight %}

{% highlight c# %}

 //PopupViewModel.cs
 
     class PopupViewModel : INotifyPropertyChanged
{
        bool isOpen;
        public event PropertyChangedEventHandler PropertyChanged;
        void OnPropertyChanged(string propertyName)
        {
            PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
        }
        public ICommand PopupAcceptCommand { get; set; }
        public ICommand PopupDeclineCommand { get; set; }
        public ICommand PopupCommand { get; set; }
        public bool PopupOpen {
            get { return isOpen; }
            set
            {
                isOpen = value;
                OnPropertyChanged(nameof(PopupOpen));
            } }
        public PopupViewModel()
        {
            PopupAcceptCommand = new Command(PopupAccept); //CanExecute() will be execute the PopupAccept method
            PopupDeclineCommand = new Command(PopupDecline); //CanExecute() will be execute the PopupDecline method
            PopupCommand = new Command(Popup);
        }

        private void Popup()
        {
            PopupOpen = true;
        }

        private void PopupAccept()
        {
             // You can write your set of codes that needs to be executed.
        }

        private void PopupDecline()
        {
            // You can write your set of codes that needs to be executed.
        }
    }
{% endhighlight %}

{% endtabs %}
