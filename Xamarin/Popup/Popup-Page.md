---
layout: post
title: Popup page | Fullscreen | Auto-size | Popup | Xamarin | Syncfusion
description: Display popup as a page increase the reusablility.
platform: Xamarin
control: SfPopupLayout
documentation: ug
---



# How to use Xamarin.Forms popup as a page?

We achieve popup as a page in Xamain.Forms by creating the SfPopupLayout as view or class file. When we need it, we may call up the SfPopupLayout. Main purpose of Popup as page is reusability. 

## How to handle the Popup as page?

* Set the view into SfPopupLayout and inside the SfPopupLayout we can create the PopupView.
* In PopupPage.xaml.cs file we need to set SfPopupLayout.IsOpen=true to show the PopupView.
* Add the template into SfPopupLayout.PopupView.ContentTemplate,SfPopupLayout.PopupView.HeaderTemplate.
* Now we can used it in `MainPage` or where we needed.

In the below code snippet we created the sample for Popup as a page by simple login page:

### 1. PopupPage.xaml and PopupPage.cs

{% tabs %}

{% highlight xaml %}

<!--PopupPage.xaml  -->
<!--In this  -->
    <?xml version="1.0" encoding="utf-8" ?>
<sfPopup:SfPopupLayout xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
               xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms"
             xmlns:local="clr-namespace:Popup"
             x:Class="Popup.PopupPage"
               IsOpen="True"    
              x:Name="popup">
    <sfPopup:PopupView AppearanceMode="OneButton" x:Name="popupview">
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
            popup.PopupView.HeaderTemplate = header;   //Insert the header template into HeaderTemplate.header was created in the PopupPage.xaml.
            popup.PopupView.ContentTemplate = content; //Insert the content template into ContentTemplate.content was created in the PopupPage.xaml.
        }
    }

{% endhighlight %}

{% endtabs %}

### 2.MainPage.xaml and PopupViewModel.cs.

{% tabs %}

{% highlight xaml %}

<!--MainPage.xaml -->

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
                UserName = " ";
                Password = " ";
            }
            else
            {
                UserName = " ";
                Password = " ";
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