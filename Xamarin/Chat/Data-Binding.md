---
layout: post
title: Data Binding | SfChat | Xamarin | Syncfusion
description: Data binding in Xamarin.Forms Chat(SfChat) using ItemsSource & ItemsSourceConverter property for using existing data collections as message collection in SfChat
platform: xamarin
control: SfChat
documentation: ug
---

# Data Binding in Xamarin.Forms Chat (SfChat)

The SfChat control allows to bind any existing collection of data objects as message collection using the [SfChat.ItemSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_ItemsSource) and [SfChat.ItemsSourceConverter](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_ItemsSourceConverter) property as follows.
First, bind the existing collection of data objects to the `SfChat.ItemsSource` property. Next, create a class derived from `IChatMessageConverter` interface and set it to the `SfChat.ItemsSourceConverter` property as shown below. The `IChatMessageConverter` interface provides the methods `ConvertToChatMessage` and `ConvertToData` to convert an item of an existing collection to a chat message and to convert a chat message to an item of the existing data collection respectively. Similarly these two methods `ConvertToChatMessage` and `ConvertToData` will be fired whenever a new item is added/removed/replaced in the existing data collection or in the chat message collection respectively.

Implementation of a custom message converter class with conversion logics to convert from data to message and vice versa.
{% tabs %}
{% highlight c# %}

/// <summary>
/// Defines methods that can be used to convert data objects to chat messages and vice versa.
/// </summary>
public class MessageConverter : IChatMessageConverter
{
    /// <summary>
    /// Converts given data object to a chat message.
    /// </summary>
    /// <param name="data">The data object to be converted as a chat message.</param>
    /// <param name="chat">Instance of <see cref="SfChat"/>. </param>
    /// <returns>Returns the data object as a chat message.</returns>
    public IMessage ConvertToChatMessage(object data, SfChat chat)
    {
        var message = new TextMessage();
        var item = data as MessageModel;

        message.Text = item.Text;
        message.Author = item.User;
        message.Data = item;
        if (item.Suggestions != null)
        {
            message.Suggestions = item.Suggestions;
        }
        return message;
    }

    /// <summary>
    /// Converts the given chat message to a data object.
    /// </summary>
    /// <param name="chatMessage">The chat message that is to be converted as a data object.</param>
    /// <param name="chat">Instance of <see cref="SfChat"/>. </param>
    /// <returns>Returns the chat message as a data object.</returns>
    public object ConvertToData(object chatMessage, SfChat chat)
    {
        var message = new MessageModel();
        var item = chatMessage as TextMessage;

        message.Text = item.Text;
        message.User = chat.CurrentUser;
        if (message.Suggestions != null)
        {
            message.Suggestions = chat.Suggestions;
        }
        return message;
    }
}

{% endhighlight %}
{% endtabs %}

Assigning values to the `SfChat.ItemsSource` and `SfChat.ItemsSourceConverter` properties.
{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:App7"                   
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             x:Class="App7.MainPage">

    <ContentPage.Resources>
        <ResourceDictionary>
            <local:MessageConverter x:Key="MessageConverter" />
        </ResourceDictionary>
    </ContentPage.Resources>

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>

    <ContentPage.Content>
        <sfChat:SfChat x:Name="sfChat" 
                       CurrentUser="{Binding CurrentUser}"                                                    
                       ItemsSource="{Binding MessageCollection }"  
                       ItemsSourceConverter="{StaticResource MessageConverter}" />
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight C# %}
using Syncfusion.XForms.Chat;
using Xamarin.Forms;

namespace App7
{
    public partial class MainPage : ContentPage
    {
        SfChat sfChat;
        GettingStartedViewModel viewModel;
        MessageConverter messageConverter;
        public MainPage()
        {
            InitializeComponent();
            sfChat = new SfChat();
            messageConverter = new MessageConverter();
            viewModel = new GettingStartedViewModel();
            sfChat.CurrentUser = viewModel.CurrentUser;
            sfChat.ItemsSource = viewModel.MessageCollection;
            sfChat.ItemsSourceConverter = messageConverter;
            Content = sfChat;
        }
    }
}

{% endhighlight %}
{% endtabs %}

You can download the entire working sample from [here](https://github.com/SyncfusionExamples/How-to-convert-data-objects-to-messages-in-MVVM-in-Xamarin.Forms-chat-SfChat-).