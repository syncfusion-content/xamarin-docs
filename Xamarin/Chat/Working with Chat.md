---
layout: post
title: Working with Chat | SfChat | Xamarin | Syncfusion
description: This topic describes how to use the interacting Events and Commands on messages in syncfusion Xamarin.Forms chat control.
platform: xamarin
control: SfChat
documentation: ug
---

# Interacting with Chat Messages

## Message Tapped Event and Command

### MessageTapped Event

The SfChat. MessageTapped event will be triggered while tapping on the messages with MessageTappedEventArgs properties as follows.

*Message  : Gets the instance of the IMessage that was interacted with.
*Position : Gets the touch position as point on the tapped message. 

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

The SfChat.MessageTappedCommand will be executed when tapping on the messages in SfChat. You can directly assign any ICommand type property to the SfChat.MessageTappedCommand. By configuring this, the chat comes handy if you have your own logics determining whether to execute the command or not.

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
    }
}
{% endhighlight %}
{% endtabs %}

## Message DoubleTapped Event and Command

### MessageDoubleTapped Event

The SfChat.MessageDoubleTapped event will be triggered while double tapping on the messages with MessageDoubleTappedEventArgs properties as follows.

*Message  : Gets the instance of the IMessage that was interacted with.
*Position : Gets the touch position as point on the tapped message. 

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

The SfChat.MessageDoubleTappedCommand will be executed when double tapping on the messages in SfChat. You can directly assign any ICommand type property to the SfChat.MessageDoubleTappedCommand. By configuring this, the chat comes handy if you have your own logics determining whether to execute the command or not.

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
    }
}
{% endhighlight %}
{% endtabs %}

## Message LongPressed Event and Command

### MessageLongPressed Event

The SfChat.MessageLongPressed event will be triggered while long pressing on the messages with MessageLongPressedEventArgs properties as follows.

*Message  : Gets the instance of the IMessage that was interacted with.
*Position : Gets the touch position as point on the tapped message. 

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

The SfChat.MessageLongPressedCommand will be executed when double tapping on the messages in SfChat. You can directly assign any ICommand type property to the SfChat.MessageLongPressedCommand. By configuring this, the chat comes handy if you have your own logics determining whether to execute the command or not.

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
    }
}
{% endhighlight %}
{% endtabs %}



