---
layout: post
title: Scrolling | SfChat | Xamarin | Syncfusion
description: Describes about the auto-scroll capabilities, events and methods to handle scrolling in Xamarin.Forms chat control.
platform: xamarin
control: SfChat
documentation: ug
---

# Scrolling in Xamarin Chat (SfChat)

## Scroll to message

You can scroll to a particular message programmatically using the [SfChat.ScrollToMessage(Object)](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_ScrollToMessage_System_Object_) method.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStattedViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
        <StackLayout x:Name="stack" Orientation="Vertical">
            <Button x:Name="ScrollTo" Text="Scroll to message" HeightRequest="100" Clicked="ScrollTo_Clicked"/>
            <sfChat:SfChat x:Name="sfChat"
                       Messages="{Binding Messages}"
                       SendMessageCommand="{Binding SendMessage}"
                       CurrentUser="{Binding CurrentUser}"
                       CanAutoScrollToBottom ="False"
                       ShowOutgoingMessageAvatar="True" />
        </StackLayout>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight C# %}

//MainPage.Xaml.cs
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent ();
    }

    private void ScrollTo_Clicked(object sender, EventArgs e)
    {
        // Scroll to the sixth message in the collection.
        this.sfChat.ScrollToMessage(this.viewModel.Messages[5]);
    }
}
{% endhighlight %}
{% endtabs %}


## Auto scroll chat control to bottom when new message is added

By default the SfChat control is scrolled to the bottom to show the newly added message. If you want to disable this auto scroll, set [SfChat.CanAutoScrollToBottom](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_CanAutoScrollToBottom) as `false`.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStattedViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
            <sfChat:SfChat x:Name="sfChat"
                       Messages="{Binding Messages}"
                       CurrentUser="{Binding CurrentUser}"
                       CanAutoScrollToBottom ="False"/>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% endtabs %}

## Scrolled event

The `SfChat` control comes with built-in [SfChat.Scrolled](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html) event that will be fired whenever the chat control is scrolled. You can get the current scroll offset, whether scrolling has reached the top or bottom of the message list in the [ChatScrolledEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.ChatScrolledEventArgs.html). You can handle this event to restrict the auto-scroll in chat for newly added messages, if the user had already scrolled up manually and was currently not at the bottom of the chat when the new message was added. 

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:ViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>

    <ContentPage.Content>
        <StackLayout>
            <sfChat:SfChat x:Name="sfChat"      
                           Messages="{Binding Messages}"
                           CurrentUser="{Binding CurrentUser}"
                           Scrolled="SfChat_Scrolled" />
        </StackLayout>
    </ContentPage.Content>
</ContentPage>       
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        ViewModel viewModel = new ViewModel();
        SfChat sfChat = new SfChat();
        sfChat.Messages = viewModel.Messages;
        sfChat.CurrentUser = viewModel.CurrentUser;
        sfChat.Scrolled += SfChat_Scrolled; ;
    }
    private void SfChat_Scrolled(object sender, ChatScrolledEventArgs e)
    {
        // The chat will not be auto scrolled to the bottom,
        // if the user is not currently at the bottom end of the chat at the time of the arrival of the new message
        // but rather already manually scrolled above to read old messages.
        this.sfChat.CanAutoScrollToBottom = e.IsReachedBottom;
    }
}

{% endhighlight %}
{% endtabs %}
