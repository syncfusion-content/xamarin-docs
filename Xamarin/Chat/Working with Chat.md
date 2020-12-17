---
layout: post
title: Working with Chat | SfChat | Xamarin | Syncfusion
description: This topic describes how to interact with messages in Xamarin.Forms Chat(SfChat) using events and Commands.
platform: xamarin
control: SfChat
documentation: ug
---

# Interacting with Chat Messages

## Message Tapped Event and Command

The SfChat control comes with built-in SfChat.MessageTapped event and SfChat.MessageTappedCommand that will be fired upon tapping a message. You can get the tapped Message, and the interacted(tapped) Point via the MessageTappedEventArgs as MessageTappedEventArgs.Message and MessageTappedEventArgs.Point respectively, in both the MessageTapped event handler and action of MessageTappedCommand.

### MessageTapped Event

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:d="http://xamarin.com/schemas/2014/forms/design"
             xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
             xmlns:local="clr-namespace:ChatInteraction"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"     
             mc:Ignorable="d"
             x:Class="ChatInteraction.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <sfChat:SfChat x:Name="sfChat"
                       MessageTapped="SfChat_MessageTapped"
                       Messages="{Binding Messages}"
                       CurrentUser="{Binding CurrentUser}"                      
                       ShowOutgoingMessageAvatar="True" >
        </sfChat:SfChat>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight C# %}
using Xamarin.Forms;

namespace ChatInteraction
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            sfChat.MessageTapped += SfChat_MessageTapped;
        }

        private void SfChat_MessageTapped(object sender, Syncfusion.XForms.Chat.MessageTappedEventArgs e)
        {
            App.Current.MainPage.DisplayAlert("Message", " Tapped on message :" + e.Message.Author.Name, "Ok");
        }
    }
}
{% endhighlight %}
{% endtabs %}

### MessageTapped Command

{% tabs %}
{% highlight xaml %}
<ContentPage.BindingContext>
    <local:ViewModel/>
</ContentPage.BindingContext>
<ContentPage.Content>
            <sfChat:SfChat x:Name="sfChat"  
                           MessageTappedCommand="{Binding TappedCommand}" />
</ContentPage.Content>
{% endhighlight %}
{% highlight C# %}

//ViewModel.cs

public class ViewModel : INotifyPropertyChanged
{
    public Command<object> tappedCommand;

    public ViewModel()
    {
	    // assigning command action to ICommand type property
        TappedCommand = new Command<object>(MessageTapped);
    }
    
	// ICommand type property for binding with sfChat.MessageTappedCommand
    public Command<object> TappedCommand
    {
        get { return tappedCommand; }
        set { tappedCommand = value; }
    }
     
    private void MessageTapped(object args)
    {
          var MessageTappedArgs = args as MessageTappedEventArgs;
          App.Current.MainPage.DisplayAlert("Message", "Tapped on Message :" + MessageTappedArgs.Message.Author.Name, "Ok");
    }
}
{% endhighlight %}
{% endtabs %}

## Message DoubleTapped Event and Command

The SfChat control comes with built-in SfChat.MessageDoubleTapped event and SfChat.MessageDoubleTappedCommand that will be fired upon double tapping a message. You can get the double tapped Message, and the interacted(double tapped) Point via the MessageDoubleTappedEventArgs as MessageDoubleTappedEventArgs.Message and MessageDoubleTappedEventArgs.Point respectively, in both the MessageDoubleTapped event handler and action of MessageDoubleTappedCommand.

### MessageDoubleTapped Event

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:d="http://xamarin.com/schemas/2014/forms/design"
             xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
             xmlns:local="clr-namespace:ChatInteraction"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"            
             mc:Ignorable="d"
             x:Class="ChatInteraction.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <sfChat:SfChat x:Name="sfChat"
                           MessageDoubleTapped="SfChat_MessageDoubleTapped"
                           Messages="{Binding Messages}"
                           CurrentUser="{Binding CurrentUser}"                      
                           ShowOutgoingMessageAvatar="True" >
        </sfChat:SfChat>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight C# %}
using Xamarin.Forms;

namespace ChatInteraction
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            sfChat.MessageDoubleTapped += SfChat_MessageDoubleTapped;        
        }

        private void SfChat_MessageDoubleTapped(object sender, Syncfusion.XForms.Chat.MessageDoubleTappedEventArgs e)
        {
            App.Current.MainPage.DisplayAlert("Message", " Tapped on message :" + e.Message.Author.Name, "Ok");
        }
    }
}
{% endhighlight %}
{% endtabs %}

### MessageDoubleTapped Command

{% tabs %}
{% highlight xaml %}
<ContentPage.BindingContext>
    <local:ViewModel/>
</ContentPage.BindingContext>
<ContentPage.Content>
            <sfChat:SfChat x:Name="sfChat"  
                           MessageDoubleTappedCommand="{Binding DoubleTappedCommand}" />
</ContentPage.Content>
{% endhighlight %}
{% highlight C# %}

//ViewModel.cs

public class ViewModel : INotifyPropertyChanged
{
   public Command<object> doubleTappedCommand;

    public ViewModel()
    {
        // assigning command action to ICommand type property
        DoubleTappedCommand = new Command<object>(MessageDoubleTapped);
    }

    // ICommand type property for binding with sfChat.MessageDoubleTappedCommand
    public Command<object> DoubleTappedCommand
    {
        get { return doubleTappedCommand; }
        set { doubleTappedCommand = value; }
    }

    private void MessageDoubleTapped(object args)
    {
        var MessageDoubleTappedArgs = args as MessageDoubleTappedEventArgs;
        App.Current.MainPage.DisplayAlert("Message", "DoubleTapped on Message :" + MessageDoubleTappedArgs.Message.Author.Name, "Ok");
    }
}
{% endhighlight %}
{% endtabs %}

## Message LongPressed Event and Command

The SfChat control comes with built-in SfChat.MessageLongPressed event and SfChat.MessageLongPressedCommand that will be fired upon long pressing a message. You can get the long pressed Message, and the interacted(long pressed) Point via the MessageLongPressedEventArgs as MessageLongPressedEventArgs.Message and MessageLongPressedEventArgs.Point respectively, in both the MessageLongPressed event handler and action of MessageLongPressedCommand.

### MessageLongPressed Event

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:d="http://xamarin.com/schemas/2014/forms/design"
             xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
             xmlns:local="clr-namespace:ChatInteraction"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"            
             mc:Ignorable="d"
             x:Class="ChatInteraction.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <sfChat:SfChat x:Name="sfChat"
                       MessageLongPressed="SfChat_MessageLongPressed"
                       Messages="{Binding Messages}"
                       CurrentUser="{Binding CurrentUser}"                      
                       ShowOutgoingMessageAvatar="True" >
        </sfChat:SfChat>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight C# %}
using Xamarin.Forms;

namespace ChatInteraction
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            sfChat.MessageLongPressed += SfChat_MessageLongPressed;

        }

        private void SfChat_MessageLongPressed(object sender, Syncfusion.XForms.Chat.MessageLongPressedEventArgs e)
        {
            App.Current.MainPage.DisplayAlert("Message", " Tapped on message :" + e.Message.Author.Name, "Ok");
        }       
    }
}
{% endhighlight %}
{% endtabs %}

### MessageLongPressed Command

{% tabs %}
{% highlight xaml %}
<ContentPage.BindingContext>
    <local:ViewModel/>
</ContentPage.BindingContext>
<ContentPage.Content>
            <sfChat:SfChat x:Name="sfChat"  
                           MessageLongPressedCommand ="{Binding LongPressedCommand }" />
</ContentPage.Content>
{% endhighlight %}
{% highlight C# %}

//ViewModel.cs

public class ViewModel : INotifyPropertyChanged
{
    public Command<object> longPressedCommand;

    public ViewModel()
    {
	    // assigning command action to ICommand type property
        LongPressedCommand = new Command<object>(MessageLongPressed);
    }

    // ICommand type property for binding with sfChat.MessageLongPressedCommand
    public Command<object> LongPressedCommand
    {
        get { return longPressedCommand; }
        set { longPressedCommand = value; }
    }

    private void MessageLongPressed(object args)
    {
        var MessageLongPressedArgs = args as MessageLongPressedEventArgs;
        App.Current.MainPage.DisplayAlert("Message", "LongPressed on Message :" + MessageLongPressedArgs.Message.Author.Name, "Ok");
    }
}
{% endhighlight %}
{% endtabs %}



