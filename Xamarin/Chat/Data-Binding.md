---
layout: post
title: Data Binding | SfChat | Xamarin | Syncfusion
description: This topic describes Data Binding in Xamarin.Forms Chat(SfChat).This could be achived through ItemsSource and ItemsSourceConverter property.
platform: xamarin
control: SfChat
documentation: ug
---

# Data Binding in Xamarin.Forms Chat (SfChat)

The SfChat control allows to bind collection of a data object, and it will be converted to chat messages. In order to bind Collection of data object, set the [SfChat.ItemSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_ItemsSource) and [SfChat.ItemsSourceConverter](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_ItemsSourceConverter) property as follows.

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

The sample class used to hold the needed information for the chat items

{% tabs %}
{% highlight c# %}

public class MessageModel
{
    public MessageModel()
    {
    }

    public ChatSuggestions Suggestions { get; set; }
    public Author User { get; set; }
    public string Text { get; set; }
}

{% endhighlight %}
{% endtabs %}

The Converter class of type [IChatMessageConverter](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.IChatMessageConverter.html) in order to convert the data object into chat messages and vice versa:

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

The ViewModel class containing a collection of Chat items.

{% tabs %}
{% highlight c# %}

public class GettingStartedViewModel : INotifyPropertyChanged
{
    /// <summary>
    /// Current user of chat.
    /// </summary>
    private Author currentAuthor;

    ObservableCollection<MessageModel> messageCollection;

    public GettingStartedViewModel()
    {
        MessageModel messageModel = new MessageModel();
        this.messageCollection = new ObservableCollection<MessageModel>();
        this.currentAuthor = new Author() { Name = "Nancy", Avatar = "People_Circle2.png" };
        this.GenerateMessages();
    }

    /// <summary>
    /// Gets or sets the collection of messages of a conversation.
    /// </summary>
    public ObservableCollection<MessageModel> MessageCollection
    {
        get
        {
            return this.messageCollection;
        }

        set
        {
            this.messageCollection = value;
            RaisePropertyChanged("messageCollection");
        }
    }

    /// <summary>
    /// Gets or sets the current user of the message.
    /// </summary>
    public Author CurrentUser
    {
        get
        {
            return this.currentAuthor;
        }
        set
        {
            this.currentAuthor = value;
            RaisePropertyChanged("CurrentUser");
        }
    }

    /// <summary>
    /// Property changed handler.
    /// </summary>
    public event PropertyChangedEventHandler PropertyChanged;

    /// <summary>
    /// Occurs when property is changed.
    /// </summary>
    /// <param name="propName">changed property name</param>
    public void RaisePropertyChanged(string propName)
    {
        if (this.PropertyChanged != null)
        {
            this.PropertyChanged(this, new PropertyChangedEventArgs(propName));
        }
    }

    private void GenerateMessages()
    {
        this.messageCollection.Add(new MessageModel()
        {
            User = currentAuthor,
            Text = "Hi guys, good morning! I'm very delighted to share with you the news that our team is going to launch a new mobile application.",
        });

        this.messageCollection.Add(new MessageModel()
        {
            User = new Author() { Name = "Andrea", Avatar = "People_Circle7.png" },
            Text = "Oh! That's great.",
        });

        this.messageCollection.Add(new MessageModel()
        {
            User = new Author() { Name = "Harrison", Avatar = "People_Circle5.png" },
            Text = "That is good news.",
        });
    }
}
        
{% endhighlight %}
{% endtabs %}
