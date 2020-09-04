---
layout: post
title: Xamarin.Forms Popup MVVM| SfPopupLayout| Xamarin| Syncfusion
description: Describes about how to use Syncfusion Xamarin.Forms Popup in MVVM and use commands to handle user responses.
platform: Xamarin
control: SfPopupLayout
documentation: ug
--- 

## How to show Xamarin.Forms popup from ViewModel?

SfPopup can be used in MVVM architecture applications easily. In the below example [SfPopupLayout.IsOpen](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.PopupLayout.SfPopupLayout.html#Syncfusion_XForms_PopupLayout_SfPopupLayout_IsOpen) property is bound to a property in the ViewModel based on which the popup is opened or closed. Refer the below code example to display popup in MVVM.

In the below code snippet, note that the Binding context is set for the page and the property (DisplayPopup) of the ViewModel is bound to the `SfPopupLayout.IsOpen`.

{% tabs %}

{% highlight xaml %}

<ContentPage.BindingContext>
    <local:ViewModel />
</ContentPage.BindingContext>

<sfpopup:SfPopupLayout x:Name="popup" IsOpen="{Binding DisplayPopup}">
    <sfpopup:SfPopupLayout.Content>
        <StackLayout x:Name="rootView">
            <Button x:Name="isOpenButton" Text="Click to open popup" Command="{Binding OpenPopupCommand}"/>
        </StackLayout>
    </sfpopup:SfPopupLayout.Content>
</sfpopup:SfPopupLayout>

{% endhighlight %}

{% highlight c# %}

// ViewModel.cs

public class ViewModel : INotifyPropertyChanged
{
    private bool displayPopup;

    public ICommand OpenPopupCommand { get; set; }

    public bool DisplayPopup
    {
        get
        {
            return displayPopup;
        }
        set
        {
            displayPopup = value;
            RaisePropertyChanged("DisplayPopup");
        }
    }

    public ViewModel()
    {
        OpenPopupCommand = new Command(OpenPopup);
    }

    private void OpenPopup()
    {
        DisplayPopup = true;
    }

    #region INotifyPropertyChanged

    public event PropertyChangedEventHandler PropertyChanged;

    private void RaisePropertyChanged(string propertyName)
    {
        if(this.PropertyChanged != null)
        {
            this.PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
        }
    }

    #endregion

}

{% endhighlight %}

{% endtabs %}

## How to use commands for popup buttons?

SfPopupLayout provides command support for the popup buttons,

*[SfPopupLayout.PopupView.AcceptCommand](https://help.syncfusion.com/xamarin/popup/popup-events?cs-save-lang=1&cs-lang=csharp#accept-command)

*[SfPopupLayout.PopupView.DeclineCommand](https://help.syncfusion.com/xamarin/popup/popup-events?cs-save-lang=1&cs-lang=csharp#decline-command)

## How to use Xamarin.Forms popup as a page?

To use SfPopupLayout as a page, create a new XAML file with SfPopupLayout in it. You can use this XAML file instance (SfPopupLayout view), across any file in your project wherever you may want to display a popup, thus allowing you to reuse the same instance of the popup where you can modify or change the required properties alone based on the current context to be displayed.

The below code snippet shows how to create a popup in XAML file. We have created a simple popup to show error message popup to user on a unsuccessful login.

{% tabs %}

{% highlight xaml %}
  
//PopupPage.xaml
 
<?xml version="1.0" encoding="utf-8" ?>
<sfPopup:SfPopupLayout xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms"
             x:Class="ControlsTest.PopupPage"
               x:Name="popup">
    <sfPopup:SfPopupLayout.PopupView>
        <sfPopup:PopupView>
            <sfPopup:PopupView.HeaderTemplate>
                <DataTemplate x:Name="header">
                    <StackLayout>
                        <Label Text="Login failed" HorizontalTextAlignment="Center"/>
                    </StackLayout>
                </DataTemplate>
            </sfPopup:PopupView.HeaderTemplate>
            <sfPopup:PopupView.ContentTemplate>
                <DataTemplate x:Name="content">
                    <StackLayout>
                        <Label Text="Incorrect credentials" VerticalOptions="Center"/>
                    </StackLayout>
                </DataTemplate>
            </sfPopup:PopupView.ContentTemplate>
        </sfPopup:PopupView>
    </sfPopup:SfPopupLayout.PopupView>
</sfPopup:SfPopupLayout>



{% endhighlight %}

{% highlight c# %}

//PopupPage.XAML.cs

public partial class PopupPage : SfPopupLayout
{
    public PopupPage ()
	{
        InitializeComponent();
    }
}

{% endhighlight %}

{% endtabs %}


The below code snippet shows how to consume the previously created SfPopupLayout page from inside a different content page.

{% tabs %}

{% highlight xaml %}

//MainPage.xaml

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ControlsTest"
             x:Class="ControlsTest.MainPage">
    
    <ContentPage.BindingContext>
        <local:PopupViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>

        <local:PopupPage x:Name="test" IsOpen="{Binding OpenPopup}"  HorizontalOptions="FillAndExpand" VerticalOptions="FillAndExpand">
        <local:PopupPage.Content>
            <StackLayout Orientation="Vertical">
                <Grid>
                    <Grid.RowDefinitions>
                        <RowDefinition Height="50"/>
                        <RowDefinition Height="50"/>
                    </Grid.RowDefinitions>
                    <Grid.ColumnDefinitions>
                        <ColumnDefinition Width="*"/>
                        <ColumnDefinition Width="*"/>
                    </Grid.ColumnDefinitions>
                    <Label Text="User Name:" Grid.Row="0" Grid.Column="0"/>
                    <Entry Text="{Binding UserName}" Grid.Row="0" Grid.Column="1"/>
                    <Label Text="Password:" Grid.Row="1" Grid.Column="0"/>
                    <Entry Text="{Binding Password}" Grid.Row="1" Grid.Column="1"/>
                </Grid>
                <Button x:Name="LoginButton" Text="Login" Command="{Binding LoginCommand}" HeightRequest="100" HorizontalOptions="CenterAndExpand" />
            </StackLayout>
        </local:PopupPage.Content>
    </local:PopupPage>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

// MainPage.Xaml.cs

[XamlCompilation(XamlCompilationOptions.Compile)]
public partial class UGPage : ContentPage
{
	public UGPage ()
	{
	    InitializeComponent ();
	}
}

//PopupViewModel.cs

class PopupViewModel : INotifyPropertyChanged
{
    #region Fields

    bool isOpen;
    string labelString, userName, password;

    #endregion

    #region PropertyChanged
    void OnPropertyChanged(string propertyName)
    {
        PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
    }

    public event PropertyChangedEventHandler PropertyChanged;
    #endregion

    #region Properties

    public ICommand LoginCommand { get; set; }

    public string LabelString
    {
        get { return labelString; }
        set
        {
            labelString = value;
            OnPropertyChanged(nameof(LabelString));
        }
    }
    public string UserName
    {
        get { return userName; }
        set
        {
            userName = value;
            OnPropertyChanged(nameof(UserName));
        }
    }
    public string Password
    {
        get { return password; }
        set
        {
            password = value;
            OnPropertyChanged(nameof(Password));
        }
    }
    public bool OpenPopup
    {
        get { return isOpen; }
        set
        {
            isOpen = value;
            OnPropertyChanged(nameof(OpenPopup));
        }
    }

    #endregion

    #region Constructor
    public PopupViewModel()
    {
        LoginCommand = new Command(Login);
    }
    #endregion

    #region Commands

    // Executed when the login button is clicked.
    private void Login()
    {
        // You can write your set of codes that needs to be executed.
        if ((UserName != "Syncfusion") || (Password != "12345"))
        {
            // If credentials are incorrect show the error message as popup.
            OpenPopup = true;
        }
    }

    #endregion
}

{% endhighlight %}

{% endtabs %}

## How to retrieve text value from entry control in Xamarin.Forms popup content template?

This can be done by binding the text property of the entry to a property in the view model class.

Refer to the following code example to retrieve text value from entry control in Xamarin.Forms popup content template.

{% tabs %}

{% highlight xaml %}

 <?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:Popup"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms"
             x:Class="Popup.MainPage">
    <ContentPage.BindingContext>
        <local:PopupViewModel x:Name="view"/>
    </ContentPage.BindingContext>

    <sfPopup:SfPopupLayout IsOpen="{Binding  PopupOpen}">
        <sfPopup:SfPopupLayout.PopupView>
            <sfPopup:PopupView AppearanceMode="TwoButton"
                    AcceptButtonText="Login" 
                    DeclineButtonText="Exit"         
                    AcceptCommand="{Binding PopupAcceptCommand}">
                    
                <sfPopup:PopupView.HeaderTemplate>
                    <DataTemplate>
                        <Label  Text="{Binding LabelString}" HorizontalOptions="Center"/>
                    </DataTemplate>
                </sfPopup:PopupView.HeaderTemplate>
                <sfPopup:PopupView.ContentTemplate>
                    <DataTemplate>
                        <Grid>
                            <Grid.RowDefinitions>
                                <RowDefinition Height="50"/>
                                <RowDefinition Height="50"/>
                            </Grid.RowDefinitions>
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="*"/>
                                <ColumnDefinition Width="*"/>
                            </Grid.ColumnDefinitions>
                            <Label Text="User Name:" Grid.Row="0" Grid.Column="0"/>
                            <Entry Text="{Binding UserName}" Grid.Row="0" Grid.Column="1"/>
                            <Label Text="Password:" Grid.Row="1" Grid.Column="0"/>
                            <Entry Text="{Binding Password}" Grid.Row="1" Grid.Column="1"/>
                        </Grid>
                    </DataTemplate>
                </sfPopup:PopupView.ContentTemplate>
             </sfPopup:PopupView>
            </sfPopup:SfPopupLayout.PopupView>
         <sfPopup:SfPopupLayout.Content>
            <StackLayout>
                    <Button  Text="ClickToShowPopup" 
               VerticalOptions="Center"  
               HorizontalOptions="Center" Command="{Binding ShowPopupCommand}" />
                <Label Text="{Binding ShowDetail}"
                VerticalOptions="CenterAndExpand"
                 HorizontalOptions="Center"
               LineBreakMode="NoWrap"
               BackgroundColor="Blue"
               TextColor="Red"
               IsVisible="{Binding Visible}"
               />
            </StackLayout>
            </sfPopup:SfPopupLayout.Content>
 </sfPopup:SfPopupLayout>
</ContentPage>




{% endhighlight %}

{% highlight c# %}

//PopupViewModel.cs

class PopupViewModel : INotifyPropertyChanged
    {
        bool isOpen, visible;
        string labelString, userName, password, showdetail;
        public event PropertyChangedEventHandler PropertyChanged;
        void OnPropertyChanged(string propertyName)
        {
            PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
        }
        public ICommand PopupAcceptCommand { get; set; }
        public ICommand ShowPopupCommand { get; set; }
        public string LabelString
        {
            get { return labelString; }
            set
            {
                labelString = value;
                OnPropertyChanged(nameof(LabelString));
            }
        }
        public string UserName
        {
            get { return userName; }
            set
            {
                userName = value;
                OnPropertyChanged(nameof(UserName));
            }
        }
        public string ShowDetail
        {
            get { return showdetail; }
            set
            {
                showdetail = value;
                OnPropertyChanged(nameof(ShowDetail));
            }
        }
        public string Password
        {
            get { return password; }
            set
            {
                password = value;
                OnPropertyChanged(nameof(Password));
            }
        }
        public bool PopupOpen
        {
            get { return isOpen; }
            set
            {
                isOpen = value;
                OnPropertyChanged(nameof(PopupOpen));
            }
        }
        public bool Visible
        {
            get { return visible; }
            set
            {
                visible = value;
                OnPropertyChanged(nameof(Visible));
            }
        }
        public PopupViewModel()
        {
            PopupAcceptCommand = new Command(PopupAccept); //CanExecute() will be call the PopupAccept method
            ShowPopupCommand = new Command(Popup);  //CanExecute() will be call the Popup method.
        }

        private void Popup()
        {
            PopupOpen = true;
            LabelString = "User Login";
            Visible = true;
        }

        private void PopupAccept()
        {
            // You can write your set of codes that needs to be executed.
            if ((UserName == "Syncfusion") && (Password == "12345"))
            {
             ShowDetail = "Login Successfully...";
               UserName = "";
                Password = "";
            }
            else
            {
                 ShowDetail = "Login Failed";
                UserName = "";
                Password = "";
             }
        }
    }

{% endhighlight %}

{% endtabs %}