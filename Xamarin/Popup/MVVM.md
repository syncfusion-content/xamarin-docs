---
layout: post
title: Popup using MVVM | SfPopupLayout |Xamarin | Syncfusion
description: Show the Xamarin.Forms Popup view in the Model-View-ViewModel.We need to set the viewmodel as a page Binding context.
platform: Xamarin
control: SfPopupLayout
documentation: ug
--- 
# MVVM

## How to show Xamarin.Forms popup from ViewModel?

SfPopup can be used in MVVM architecture applications easily. In the below example [SfPopupLayout.IsOpen](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~IsOpen.html) property is binded to a property in the ViewModel based on which the popup is opened or closed. Refer the below code example to display popup in MVVM.

In the below code snippet, note that the Binding context is set for the page and the property (DisplayPopup) of the ViewModel is binded to the [SfPopupLayout.IsOpen](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~IsOpen.html).

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

The commanding interface provides an alternative approach to implementing commands that is much better suited to the MVVM architecture. The ViewModel itself can contain commands, which are methods that are executed in reaction to a specific activity in the View such as a Button click will be fired the command.

In SfPopupLayout.PopupView we have two types of command:

*[SfPopupLayout.PopupView.AcceptCommand](https://help.syncfusion.com/xamarin/popup/popup-events?cs-save-lang=1&cs-lang=csharp#accept-command)

*[SfPopupLayout.PopupView.DeclineCommand](https://help.syncfusion.com/xamarin/popup/popup-events?cs-save-lang=1&cs-lang=csharp#decline-command)

# How to use Xamarin.Forms popup as a page?

We achieve popup as a page in Xamarin.Forms by creating the SfPopupLayout as view or class file. When we need it, we may call up the SfPopupLayout. Main purpose of Popup as page is its reusable.

## How to handle the Popup as page?

* Set the view into SfPopupLayout and inside the SfPopupLayout we can create the PopupView.
* In PopupPage.xaml.cs file we need to set SfPopupLayout.IsOpen=true to show the PopupView.
* Add the template into SfPopupLayout.PopupView.ContentTemplate,SfPopupLayout.PopupView.HeaderTemplate.
* Now we can used it in `MainPage` or where we needed.

In the below code snippet we created the sample for Popup as a page by simple login page:



{% tabs %}

{% highlight xaml %}
  
  //PopupPage.xaml
 
 <?xml version="1.0" encoding="utf-8" ?>
<sfPopup:SfPopupLayout xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
               xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms"
             xmlns:local="clr-namespace:Popup"
             x:Class="Popup.PopupPage"
               x:Name="popup">
    <sfPopup:PopupView>
        <sfPopup:PopupView.HeaderTemplate>
            <DataTemplate x:Name="header">
                <StackLayout>
                    <Label Text="Congratulation"/>
                </StackLayout>
            </DataTemplate>
        </sfPopup:PopupView.HeaderTemplate>
        <sfPopup:PopupView.ContentTemplate>
            <DataTemplate x:Name="content">
                <StackLayout>
                    <Label Text="Login Successfully..." VerticalOptions="Center"/>
                </StackLayout>
            </DataTemplate>
        </sfPopup:PopupView.ContentTemplate>
    </sfPopup:PopupView>
</sfPopup:SfPopupLayout>



{% endhighlight %}

{% highlight c# %}

//PopupPage.cs

public partial class PopupPage : SfPopupLayout
    {
        public PopupPage ()
		{
            InitializeComponent();
            popup.IsOpen = true;
            popup.PopupView.AcceptButtonText = "Ok";
            popup.PopupView.HeaderTemplate = header;   //Insert the header template into HeaderTemplate.header was created in the PopupPage.xaml.
            popup.PopupView.ContentTemplate = content; //Insert the content template into ContentTemplate.content was created in the PopupPage.xaml.
        }
    }

{% endhighlight %}

{% endtabs %}



{% tabs %}

{% highlight xaml %}

//MainPage.xaml

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
                    AcceptCommand="{Binding PopupAcceptCommand}"
                    DeclineCommand="{Binding PopupDeclineCommand}"
                               >
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
               HorizontalOptions="Center" Command="{Binding PopupCommand}" />
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
        string labelString,userName,password;
        public event PropertyChangedEventHandler PropertyChanged;
        void OnPropertyChanged(string propertyName)
        {
            PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
        }
        public ICommand PopupAcceptCommand { get; set; }
        public ICommand PopupDeclineCommand { get; set; }
        public ICommand PopupCommand { get; set; }
         public string LabelString { get { return labelString; }
            set
            {
                labelString = value;
                OnPropertyChanged(nameof(LabelString));
            } }
        public string UserName { get { return userName; } //Gets or Sets the value for the UserName.
            set {
                userName = value;
                OnPropertyChanged(nameof(UserName));
            }}
        public string Password { get { return password; } //Gets or Sets the value for the Password.
            set
            {
                password = value;
                OnPropertyChanged(nameof(Password));
            }
        }
        public bool PopupOpen {
            get { return isOpen; }
            set
            {
                isOpen = value;
                OnPropertyChanged(nameof(PopupOpen));
            } }
        public PopupViewModel() //Initialization of the PopupViewModel.
        {
            PopupAcceptCommand = new Command(PopupAccept); //CanExecute() will be call the PopupAccept method
            PopupDeclineCommand = new Command(PopupDecline); //CanExecute() will be call the PopupDecline method
            PopupCommand = new Command(Popup);  //CanExecute() will be call the Popup method.
        }

        private void Popup() //An action to perform when the PopupCommand fired and In this method was open the popupview
                            //by set PopupOpen value is true.
        {
            PopupOpen = true;
            LabelString = "User Login";
        }

        private void PopupAccept()//An action to perform when the PopupAcceptCommand fired.
        {
            // You can write your set of codes that needs to be executed.
            if ((UserName == "Syncfusion") && (Password == "12345"))
            {
                PopupPage page = new PopupPage();  //Initialize the PopupPage class it will run the Popup as a page.
                UserName = "";
                Password = "";
            }
            else
            {
                UserName = "";
                Password = "";
            }
        }

        private void PopupDecline()//An action to perform when the PopupDeclineCommand fired.
        {
            // You can write your set of codes that needs to be executed.
            PopupOpen = false;

        }
    }

{% endhighlight %}

{% endtabs %}

# How to Retrieve text value from entry control in Xamarin.Forms popup content template?

We can accomplish this by binding ViewModel property to the entry.

Refer to the following code example for retrieve text value from entry control in Xamarin.Forms popup content template.

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
                    AcceptCommand="{Binding PopupAcceptCommand}"
                    DeclineCommand="{Binding PopupDeclineCommand}"
                               >
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
               HorizontalOptions="Center" Command="{Binding PopupCommand}" />
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
        public ICommand PopupDeclineCommand { get; set; }
        public ICommand PopupCommand { get; set; }
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
            PopupDeclineCommand = new Command(PopupDecline); //CanExecute() will be call the PopupDecline method
            PopupCommand = new Command(Popup);  //CanExecute() will be call the Popup method.
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

        private void PopupDecline()
        {
            // You can write your set of codes that needs to be executed.
            PopupOpen = false;
            Visible = false;

        }
    }

{% endhighlight %}

{% endtabs %}