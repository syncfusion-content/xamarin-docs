---
layout: post
title: DataTemplete | SfPopupLayout |Xamarin | Syncfusion
description: Retrieve text value from entry control in Xamarin.Forms popup content template.
platform: Xamarin
control: SfPopupLayout
documentation: ug
---
# How to Retrieve text value from entry control in Xamarin.Forms popup content template?

We can achieve this by Binding the Poperty of the ViewModel to the entry.

Refer to the following code example for Retrieve text value from entry control in Xamarin.Forms popup content template.

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
