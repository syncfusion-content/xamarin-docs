---
layout: post
title: Messages | SfChat | Xamarin | Syncfusion
description: Describes about the available message types that comes built-in and how to create different types of messages in Xamarin.Forms chat control.
platform: xamarin
control: SfChat
documentation: ug
---

# Messages in Xamarin Chat (SfChat)

## Configuring common settings for the message

<table>
<tr>
<td>{{'[Message.Author](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.MessageBase.html#Syncfusion_XForms_Chat_MessageBase_Author)'| markdownify }}</td>
<td>Specify the avatar and name of the message sender using {{'[Author.Avatar](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.Author.html#Syncfusion_XForms_Chat_Author_Avatar)'| markdownify }} and {{'[Author.Name](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.Author.html#Syncfusion_XForms_Chat_Author_Name)'| markdownify }} properties respectively.</td>
</tr>
<tr>
<td>{{'[Message.DateTime](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.MessageBase.html#Syncfusion_XForms_Chat_MessageBase_DateTime)'| markdownify }}</td>
<td>To display message created or received time.</td>
</tr>
</table>

## Setting current user for conversation

The [SfChat.CurrentUser](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_CurrentUser) helps differentiate between the sender and receiver of the messages. On any given chat window, the `SfChat.CurrentUser` is meant to be the sender(author of outgoing messages). Refer the below code example to set up a current user in a chat.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
                    <sfChat:SfChat x:Name="sfChat"
                           Messages="{Binding Messages}"
                           CurrentUser="{Binding CurrentUser}"
                           ShowOutgoingMessageAvatar="True" />
	<ContentPage.Content>	
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Chat;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfChat sfChat;
        GettingStartedViewModel viewModel;
        public MainPage()
        {
            InitializeComponent();
            this.sfChat = new SfChat();
            this.viewModel = new GettingStartedViewModel();
            this.sfChat.Messages = viewModel.Messages;
            this.sfChat.CurrentUser = viewModel.CurrentUser;
            this.sfChat.ShowOutgoingMessageAvatar = true;
            this.Content = sfChat;
        }
    }
}

/// <summary>
/// View model class for chat view.
/// </summary>
public class GettingStartedViewModel : INotifyPropertyChanged
{
    private ObservableCollection<object> messages;

    /// <summary>
    /// current user of chat.
    /// </summary>
    private Author currentUser;

    public GettingStartedViewModel()
    {
        this.Messages = new ObservableCollection<object>();
        this.CurrentUser = new Author() { Name = "Nancy" ,Avatar = "People_Circle16.png" };
        this.GenerateMessages();
    }

    /// <summary>
    /// Gets or sets the current user.
    /// </summary>
    public Author CurrentUser
    {
        get
        {
            return this.currentUser;
        }
        set
        {
            this.currentUser = value;
            RaisePropertyChanged("CurrentUser");
        }
    }

    /// <summary>
    /// Gets or sets the message conversation.
    /// </summary>
    public ObservableCollection<object> Messages
    {
        get
        {
            return this.messages;
        }
        set
        {
            this.messages = value;
        }
    }
        
    /// <summary>
    /// Property changed handler.
    /// </summary>
    public event PropertyChangedEventHandler PropertyChanged;

    /// <summary>
    /// Occurs when property is changed.
    /// </summary>
    /// <param name="propName">changed property name<param>
    public void RaisePropertyChanged(string propName)
    {
        if (this.PropertyChanged != null)
        {
            this.PropertyChanged(this, new PropertyChangedEventArgs(propName));
        }
    }

    private void GenerateMessages()
    {
        this.Messages.Add(new TextMessage()
        {
            Author = CurrentUser,
            Text = "Hi guys, good morning! I'm very delighted to share with you the news that our team is going to launch a new mobile application.",
        });
    }
}

{% endhighlight %}
{% endtabs %}

![Xamarin Forms chat current user](SfChat_images/xamarin-forms-chat-current-user.png)

## Text message

[TextMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.TextMessage.html) is used to display plain text as a message. The following code example explains how to add a simple text message.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
                    <sfChat:SfChat x:Name="sfChat"
                           Messages="{Binding Messages}"
                           CurrentUser="{Binding CurrentUser}"
                           ShowOutgoingMessageAvatar="True" />
	<ContentPage.Content>	
</ContentPage>

{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.Chat;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfChat sfChat;
        GettingStartedViewModel viewModel;
        public MainPage()
        {
            InitializeComponent();
            this.sfChat = new SfChat();
            this.viewModel = new GettingStartedViewModel();
            this.sfChat.Messages = viewModel.Messages;
            this.sfChat.CurrentUser = viewModel.CurrentUser;
            this.sfChat.ShowOutgoingMessageAvatar = true;
            this.Content = sfChat;
        }
    }
}

/// <summary>
/// View model class for chat view.
/// </summary>
public class GettingStartedViewModel : INotifyPropertyChanged
{
    private ObservableCollection<object> messages;

    /// <summary>
    /// current user of chat.
    /// </summary>
    private Author currentUser;

    public GettingStartedViewModel()
    {
        this.Messages = new ObservableCollection<object>();
        this.CurrentUser = new Author() { Name = "Nancy",Avatar = "People_Circle16.png" };
        this.GenerateMessages();
    }

    /// <summary>
    /// Gets or sets the current user.
    /// </summary>
    public Author CurrentUser
    {
        get
        {
            return this.currentUser;
        }
        set
        {
            this.currentUser = value;
            RaisePropertyChanged("CurrentUser");
        }
    }

    /// <summary>
    /// Gets or sets the message conversation.
    /// </summary>
    public ObservableCollection<object> Messages
    {
        get
        {
            return this.messages;
        }
        set
        {
            this.messages = value;
        }
    }

    /// <summary>
    /// Property changed handler.
    /// </summary>
    public event PropertyChangedEventHandler PropertyChanged;

    /// <summary>
    /// Occurs when property is changed.
    /// </summary>
    /// <param name="propName">changed property name<param>
    public void RaisePropertyChanged(string propName)
    {
        if (this.PropertyChanged != null)
        {
            this.PropertyChanged(this, new PropertyChangedEventArgs(propName));
        }
    }

    private void GenerateMessages()
    {
        this.Messages.Add(new TextMessage()
        {
            Author = CurrentUser,
            Text = "Hi guys, good morning! I'm very delighted to share with you the news that our team is going to launch a new mobile application.",
        });
        this.Messages.Add(new TextMessage()
        {
            Author = new Author() { Name = "Andrea",Avatar = "People_Circle2.png" },
            Text = "Oh! That's great.",
        });
        this.Messages.Add(new TextMessage()
        {
            Author = new Author() { Name = "Harrison",Avatar = "People_Circle14.png" },
            Text = "That is good news.",
        });
        this.Messages.Add(new TextMessage()
        {
            Author = new Author() { Name = "Margaret",Avatar = "People_Circle7.png" },
            Text = "What kind of application is it and when are we going to launch?",
        });
    }
}

{% endhighlight %}
{% endtabs %}

![Xamarin Forms chat text message](SfChat_images/xamarin-forms-chat-text-message.png)

## Date picker message

[DatePickerMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.DatePickerMessage.html) is used to show a date picker as a message to let users select a date. Once a date is selected, the selected date will be added as a `TextMessage` in the chat window. The [SendMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html) event and [SendMessageCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_SendMessageCommand) will be executed upon selecting a date from the date picker.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
        <sfChat:SfChat x:Name="sfChat"
                       Messages="{Binding Messages}"
                       SendMessage="SfChat_SendMessage"
                       CurrentUser="{Binding CurrentUser}"
                       ShowOutgoingMessageAvatar="True" />
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}

using Syncfusion.XForms.Chat;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfChat sfChat;
        GettingStartedViewModel viewModel;
        public MainPage()
        {
            InitializeComponent();
            sfChat = new SfChat();
            viewModel = new GettingStartedViewModel();
            this.sfChat.Messages = viewModel.Messages;
            this.sfChat.CurrentUser = viewModel.CurrentUser;
            this.sfChat.ShowOutgoingMessageAvatar = true;
            this.sfChat.SendMessage += this.SfChat_SendMessage;
            this.Content = sfChat;
        }

        /// <summary>
        /// Raised when current user sends message to bot using Chat UI.
        /// </summary>
        /// <param name="sender"><see cref="SfChat"/> as sender.</param>
        /// <param name="e"><see cref="SendMessageEventArgs"/> as parameter.</param>
        private void SfChat_SendMessage(object sender, SendMessageEventArgs e)
        {
            // Denotes the date selected from the date picker.
            var selectedDate = e.Message.Text;
        }
    }
}

/// <summary>
/// View model class for chat view.
/// </summary>
public class GettingStartedViewModel : INotifyPropertyChanged
{
    private ObservableCollection<object> messages;

    /// <summary>
    /// current user of chat.
    /// </summary>
    private Author currentUser;

    public GettingStartedViewModel()
    {
        this.Messages = new ObservableCollection<object>();
        this.CurrentUser = new Author() { Name = "Nancy", Avatar = "People_Circle16.png" };
        this.GenerateMessages();
    }

    /// <summary>
    /// Gets or sets the current user.
    /// </summary>
    public Author CurrentUser
    {
        get
        {
            return this.currentUser;
        }
        set
        {
            this.currentUser = value;
            RaisePropertyChanged("CurrentUser");
        }
    }

    /// <summary>
    /// Gets or sets the message conversation.
    /// </summary>
    public ObservableCollection<object> Messages
    {
        get
        {
            return this.messages;
        }
        set
        {
            this.messages = value;
        }
    }

    /// <summary>
    /// Property changed handler.
    /// </summary>
    public event PropertyChangedEventHandler PropertyChanged;

    /// <summary>
    /// Occurs when property is changed.
    /// </summary>
    /// <param name="propName">changed property name<param>
    public void RaisePropertyChanged(string propName)
    {
        if (this.PropertyChanged != null)
        {
            this.PropertyChanged(this, new PropertyChangedEventArgs(propName));
        }
    }

    private void GenerateMessages()
    {
        this.Messages.Add(new TextMessage()
        {
            Author = CurrentUser,
            Text = "Flight to USA",
        });
        this.Messages.Add(new DatePickerMessage()
        {
            Author = new Author() { Name = "Travel Bot",Avatar = "Aeroplane.png" },
            Text = "Select departure date",
            SelectedDate = DateTime.Now
        });
    }
}

{% endhighlight %}
{% endtabs %}

![Xamarin Forms chat date picker message](SfChat_images/xamarin-forms-chat-date-picker.png)

## Time picker message

[TimePickerMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.TimePickerMessage.html) is used to show a time picker as a message to let users select time. Once time is selected, the selected time is added as a `TextMessage`. The [SfChat.SendMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html) event and [SfChat.SendMessageCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_SendMessageCommand) will be executed upon selecting a time from the time picker.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
        <sfChat:SfChat x:Name="sfChat"
                       Messages="{Binding Messages}"
                       SendMessage="SfChat_SendMessage"
                       CurrentUser="{Binding CurrentUser}"
                       ShowOutgoingMessageAvatar="True" />
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.Chat;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfChat sfChat;
        GettingStartedViewModel viewModel;
        public MainPage()
        {
            InitializeComponent();
            sfChat = new SfChat();
            viewModel = new GettingStartedViewModel();
            this.sfChat.Messages = viewModel.Messages;
            this.sfChat.CurrentUser = viewModel.CurrentUser;
            this.sfChat.ShowOutgoingMessageAvatar = true;
            this.sfChat.SendMessage += this.SfChat_SendMessage;
            this.Content = sfChat;
        }

        /// <summary>
        /// Raised when current user sends message to bot using Chat UI.
        /// </summary>
        /// <param name="sender"><see cref="SfChat"/> as sender.</param>
        /// <param name="e"><see cref="SendMessageEventArgs"/> as parameter.</param>
        private void SfChat_SendMessage(object sender, SendMessageEventArgs e)
        {
            // Denotes the time selected from the time picker.
            var selectedTime =  e.Message.Text;
        }
    }
}

/// <summary>
/// View model class for chat view.
/// </summary>
public class GettingStartedViewModel : INotifyPropertyChanged
{
    private ObservableCollection<object> messages;

    /// <summary>
    /// current user of chat.
    /// </summary>
    private Author currentUser;

    public GettingStartedViewModel()
    {
        this.Messages = new ObservableCollection<object>();
        this.CurrentUser = new Author() { Name = "Nancy",Avatar = "People_Circle16.png" };
        this.GenerateMessages();
    }

    /// <summary>
    /// Gets or sets the current user.
    /// </summary>
    public Author CurrentUser
    {
        get
        {
            return this.currentUser;
        }
        set
        {
            this.currentUser = value;
            RaisePropertyChanged("CurrentUser");
        }
    }

    /// <summary>
    /// Gets or sets the message conversation.
    /// </summary>
    public ObservableCollection<object> Messages
    {
        get
        {
            return this.messages;
        }
        set
        {
            this.messages = value;
        }
    }

    /// <summary>
    /// Property changed handler.
    /// </summary>
    public event PropertyChangedEventHandler PropertyChanged;

    /// <summary>
    /// Occurs when property is changed.
    /// </summary>
    /// <param name="propName">changed property name<param>
    public void RaisePropertyChanged(string propName)
    {
        if (this.PropertyChanged != null)
        {
            this.PropertyChanged(this, new PropertyChangedEventArgs(propName));
        }
    }

    private void GenerateMessages()
    {
        this.Messages.Add(new TextMessage()
        {
            Author = CurrentUser,
            Text = "Consultation with Dr.Harry tomorrow.",
        });

        this.Messages.Add(new TimePickerMessage()
        {
            Author = new Author() { Name = "Health care", Avatar = "Healthcare.png" },
            Text = "Select convenient time to meet Dr.Harry for health check up.",
            // Time picker display time.
            SelectedTime = new TimeSpan(8, 30, 00),
        });
    }
}

{% endhighlight %}
{% endtabs %}

![Xamarin Forms chat time picker message](SfChat_images/xamarin-forms-chat-time-picker.png)

## Calendar message

[CalendarMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.CalendarMessage.html) is used to display a calendar as a message to let users select a date. The date selected from the calendar will be added as a `TextMessage`. The [SfChat.SendMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html) event and [SfChat.SendMessageCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_SendMessageCommand) will be executed upon selecting a date from the calendar.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
        <sfChat:SfChat x:Name="sfChat"
                       Messages="{Binding Messages}"
                       SendMessage="SfChat_SendMessage"
                       CurrentUser="{Binding CurrentUser}"
                       ShowOutgoingMessageAvatar="True" />
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.Chat;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfChat sfChat;
        GettingStartedViewModel viewModel;
        public MainPage()
        {
            InitializeComponent();
            sfChat = new SfChat();
            viewModel = new GettingStartedViewModel();
            this.sfChat.Messages = viewModel.Messages;
            this.sfChat.CurrentUser = viewModel.CurrentUser;
            this.sfChat.ShowOutgoingMessageAvatar = true;
            this.sfChat.SendMessage += this.SfChat_SendMessage;
            this.Content = sfChat;
        }

        /// <summary>
        /// Raised when current user sends message to bot using Chat UI.
        /// </summary>
        /// <param name="sender"><see cref="SfChat"/> as sender.</param>
        /// <param name="e"><see cref="SendMessageEventArgs"/> as parameter.</param>
        private void SfChat_SendMessage(object sender, SendMessageEventArgs e)
        {   
            // Denotes the date selected from the calendar.
            var selectedDate = e.Message.Text;
        }
    }
}

/// <summary>
/// View model class for chat view.
/// </summary>
public class GettingStartedViewModel : INotifyPropertyChanged
{
    private ObservableCollection<object> messages;

    /// <summary>
    /// current user of chat.
    /// </summary>
    private Author currentUser;

    public GettingStartedViewModel()
    {
        this.Messages = new ObservableCollection<object>();
        this.CurrentUser = new Author() { Name = "Nancy", Avatar ="People_Circle16.png" };
        this.GenerateMessages();
    }

    /// <summary>
    /// Gets or sets the current user.
    /// </summary>
    public Author CurrentUser
    {
        get
        {
            return this.currentUser;
        }
        set
        {
            this.currentUser = value;
            RaisePropertyChanged("CurrentUser");
        }
    }

    /// <summary>
    /// Gets or sets the message conversation.
    /// </summary>
    public ObservableCollection<object> Messages
    {
        get
        {
            return this.messages;
        }
        set
        {
            this.messages = value;
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
        this.Messages.Add(new TextMessage()
        {
            Author = CurrentUser,
            Text = "Appointment with Dr.Harry.",
        });

        this.Messages.Add(new CalendarMessage()
        {
            Author = new Author() { Name = "Health care", Avatar = "Healthcare.png" },
            Text = "Select convenient date to meet Dr.Harry for health check up.",
            SelectedDate = DateTime.Now,
        });
    }
}

{% endhighlight %}
{% endtabs %}

![Xamarin Forms chat calendar message](SfChat_images/xamarin-forms-chat-calendar-message.png)

## Hyperlink message

[HyperlinkMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.HyperlinkMessage.html) is used to share URL as a message. Along with the link, the thumbnail, title and description of the URL are automatically fetched and displayed. The following code example illustrates how to add a hyperlink message.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
                    <sfChat:SfChat x:Name="sfChat"
                           Messages="{Binding Messages}"
                           CurrentUser="{Binding CurrentUser}"
                           ShowOutgoingMessageAvatar="True" />
	<ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.Chat;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfChat sfChat;
        GettingStartedViewModel viewModel;
        public MainPage()
        {
            InitializeComponent();
            this.sfChat = new SfChat();
            this.viewModel = new GettingStartedViewModel();
            this.sfChat.Messages = viewModel.Messages;
            this.sfChat.CurrentUser = viewModel.CurrentUser;
            this.sfChat.ShowOutgoingMessageAvatar = true;
            this.Content = sfChat;
        }
    }
}

/// <summary>
/// View model class for chat view.
/// </summary>
public class GettingStartedViewModel : INotifyPropertyChanged
{
    private ObservableCollection<object> messages;

    /// <summary>
    /// current user of chat.
    /// </summary>
    private Author currentUser;

    public GettingStartedViewModel()
    {
        this.Messages = new ObservableCollection<object>();
        this.CurrentUser = new Author() { Name = "Nancy", Avatar = "People_Circle16.png" };
        this.GenerateMessages();
    }

    /// <summary>
    /// Gets or sets the current user.
    /// </summary>
    public Author CurrentUser
    {
        get
        {
            return this.currentUser;
        }
        set
        {
            this.currentUser = value;
            RaisePropertyChanged("CurrentUser");
        }
    }

    /// <summary>
    /// Gets or sets the message conversation.
    /// </summary>
    public ObservableCollection<object> Messages
    {
        get
        {
            return this.messages;
        }
        set
        {
            this.messages = value;
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
        this.Messages.Add(new TextMessage()
        {
            Author = new Author() { Name = "Michale", Avatar = "People_Circle23.png" },
            Text = "We should develop this app in Xamarin, since it provides native experience and performance.",
        });

        this.Messages.Add(new TextMessage()
        {
            Author = CurrentUser,
            Text = "I haven't heard of Xamarin. What's Xamarin?",
        });

        this.Messages.Add(new HyperlinkMessage()
        {
            Author = new Author() { Name = "Michale", Avatar = "People_Circle23.png" },
            Text = "Refer the following documentation link to learn more about xamarin.",
            Url = "https://docs.microsoft.com/en-us/xamarin/get-started/what-is-xamarin",
        });
    }
}

{% endhighlight %}
{% endtabs %}

![Xamarin Forms chat hyper link message](SfChat_images/xamarin-forms-chat-hyperlink-message.png)

### Adding hyperlink message as an outgoing message

Unlike the other messages, the `HyperlinkMessage` can also be shown as an outgoing message. To add an `HyperlinkMessage` as an outgoing message just set the [HyperlinkMessage.Author](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.MessageBase.html#Syncfusion_XForms_Chat_MessageBase_Author) as [SfChat.CurrentUser](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_CurrentUser).

![Send hyper link message](SfChat_images/xamarin-forms-chat-outgoing-hyperlink-message.png)

## Image message

[ImageMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.ImageMessage.html) is used to display an image as a message. Using the [ImageMessage.Source](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.ImageMessage.html#Syncfusion_XForms_Chat_ImageMessage_Source), [ImageMessage.Size](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.ImageMessage.html#Syncfusion_XForms_Chat_ImageMessage_Size) and [ImageMessage.Aspect](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.ImageMessage.html#Syncfusion_XForms_Chat_ImageMessage_Aspect) properties you can display the desired image in the desired height and width as a message in the chat control.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
                    <sfChat:SfChat x:Name="sfChat"
                           Messages="{Binding Messages}"
                           CurrentUser="{Binding CurrentUser}"
                           ShowOutgoingMessageAvatar="True" />
	<ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.Chat;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfChat sfChat;
        GettingStartedViewModel viewModel;
        public MainPage()
        {
            InitializeComponent();
            this.sfChat = new SfChat();
            this.viewModel = new GettingStartedViewModel();
            this.sfChat.Messages = viewModel.Messages;
            this.sfChat.CurrentUser = viewModel.CurrentUser;
            this.sfChat.ShowOutgoingMessageAvatar = true;
            this.Content = sfChat;
        }
    }
}

/// <summary>
/// View model class for chat view.
/// </summary>
public class GettingStartedViewModel : INotifyPropertyChanged
{
    private ObservableCollection<object> messages;

    /// <summary>
    /// current user of chat.
    /// </summary>
    private Author currentUser;

    public GettingStartedViewModel()
    {
        this.Messages = new ObservableCollection<object>();
        this.CurrentUser = new Author() { Name = "Nancy", Avatar = "People_Circle16.png" };
        this.GenerateMessages();
    }

    private void GenerateMessages()
    {
        this.messages.Add(new TextMessage()
        {
            Author = CurrentUser,
            Text = "I was delight to buy some sport cars can you suggest some cars",
            DateTime = new DateTime(2020, 03, 15),
        });

        this.Messages.Add(new ImageMessage()
        {
            Aspect = Xamarin.Forms.Aspect.AspectFill,
            Source = "Car1.jpeg",
            Author = new Author() { Name = "Andrea", Avatar = "People_Circle23.png" },
            Text = "",
            DateTime = new DateTime(2020, 10, 02),
        });

        this.Messages.Add(new ImageMessage()
        {
            Aspect = Xamarin.Forms.Aspect.AspectFit,
            Source = "Car2.jpg",
            Text="LcMaren",
            Author = new Author() { Name = "Andrea", Avatar = "People_Circle23.png" },
        });

        this.Messages.Add(new ImageMessage()
        {
            Aspect = Xamarin.Forms.Aspect.Fill,
            Source = "Car3.jpg",
            Text="Bugatti",
            Author = new Author() { Name = "Andrea", Avatar = "People_Circle23.png" },
        });
    }

    /// <summary>
    /// Gets or sets the current user.
    /// </summary>
    public Author CurrentUser
    {
        get
        {
            return this.currentUser;
        }
        set
        {
            this.currentUser = value;
            RaisePropertyChanged("CurrentUser");
        }
    }

    /// <summary>
    /// Gets or sets the message conversation.
    /// </summary>
    public ObservableCollection<object> Messages
    {
        get
        {
            return this.messages;
        }
        set
        {
            this.messages = value;
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
}

{% endhighlight %}
{% endtabs %}

![Xamarin Forms chat image message](SfChat_images/Xamarin-Forms-chat-image-message.png)

### Event and command

The `ImageMessage` comes with in-built [SfChat.ImageTapped](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html) event and [SfChat.ImageTappedCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_ImageTappedCommand) that will be fired upon tapping an image message. You can get the instance of the `ImageMessage` that was tapped in the [ImageTappedEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.ImageTappedEventArgs.html) as `ImageTappedEventArgs.Message`. You can handle this event/command to achieve requirements like to show the image in full screen, or show options for sharing the image etc.

**ImageTapped event**

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:ChatSample"
             x:Class="ChatSample.MainPage">
    <ContentPage.BindingContext>
        <local:ViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
            <sfChat:SfChat x:Name="chat" 
                           Messages="{Binding Messages}"
                           CurrentUser="{Binding CurrentUser}"
                           ShowOutgoingMessageAvatar="True"
                           ShowAttachmentButton="True"
                           ImageTapped="chat_ImageTapped">
        </sfChat:SfChat>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}

//MainPage.cs

public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
    }

    private void sfChat_ImageTapped(object sender, ImageTappedEventArgs e)
    {
        // Check if a particular image message was tapped.
        if(args.Message.Source == ImageSource.FromFile("car1.png"))
        {
            // Do desired actions like displaying the image in full screen.
        }
    }
}

{% endhighlight %}
{% endtabs %}

**ImageTappedCommand**

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:ChatSample"
             x:Class="ChatSample.MainPage">
    <ContentPage.BindingContext>
        <local:ViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
            <sfChat:SfChat x:Name="chat"
                           Messages="{Binding Messages}"
                           CurrentUser="{Binding CurrentUser}"
                           ShowOutgoingMessageAvatar="True"
                           ImageTappedCommand="{Binding Command}">
        </sfChat:SfChat>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}

//ViewModel.cs
...
public ViewModel()
{
    this.messages = new ObservableCollection<object>();
    this.CurrentUser = new Author() { Name = "Nancy", Avatar = "Nancy.png" };
    Command = new Command(Tapped);
    this.GenerateMessages();
}

private void Tapped(object args)
{
    // Check if a particular image message was tapped.
    if((args as ImageTappedEventArgs).Message.Source == ImageSource.FromFile("car1.png"))
    {
        // Do desired actions like displaying the image in full screen.
    }
}
...
{% endhighlight %}
{% endtabs %}

You can download the complete project demo to show the tapped image in full screen from [here](https://github.com/SyncfusionExamples/How-to-display-the-tapped-image-in-full-screen-in-Xamarin.Forms-chat).

### Adding image message as an outgoing message

Unlike the other messages, the `ImageMessage` can also be shown as an outgoing message. To add an `ImageMessage` as an outgoing message just set the [ImageMessage.Author](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.MessageBase.html#Syncfusion_XForms_Chat_MessageBase_Author) as [SfChat.CurrentUser](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_CurrentUser). You can also add an image message when clicking the attachment button as shown [here](https://help.syncfusion.com/xamarin/chat/attachment-button).

![Send image message](SfChat_images/ImageMessage_Outgoing.png)

### Displaying a GIF as an image message

You can write style targeting the [ControlTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html) property of the [ChatImageView](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.ChatImageView.html) and add it to the application's resources as shown below. You can assign your custom template view that is capable of loading a GIF image as the `ControlTemplate` of `ChatImageView` using `Style.Setter`. Here in the below code example we have loaded our `CustomImageView` as `ControlTemplate` of the `ChatImageView`.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:d="http://xamarin.com/schemas/2014/forms/design"
             xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
             xmlns:local="clr-namespace:GettingStarted"
             xmlns:sfchat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             mc:Ignorable="d"
             x:Class="GettingStarted.ImageMessageCustomTemplate">
    <ContentPage.BindingContext>
        <local:ImageMessageViewModel x:Name="viewModel" />
    </ContentPage.BindingContext>

    <ContentPage.Resources>
        <ResourceDictionary>
            <Style TargetType="sfchat:ChatImageView">
                <Setter Property="ControlTemplate">
                    <Setter.Value>
                        <ControlTemplate>
                            <local:CustomImageView/>
                        </ControlTemplate>
                    </Setter.Value>
                </Setter>
            </Style>
        </ResourceDictionary>
    </ContentPage.Resources>

    <ContentPage.Content>
        <sfchat:SfChat x:Name="sfChat" 
                           ShowOutgoingMessageAvatar="True"
                           Messages="{Binding Messages}"
                           CurrentUser="{Binding CurrentUser}">
        </sfchat:SfChat>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}

namespace GettingStarted
{
    [XamlCompilation(XamlCompilationOptions.Compile)]
    public partial class ImageMessageCustomTemplate : ContentPage
    {
        public ImageMessageCustomTemplate(bool HideAvatar = false)
        {
            InitializeComponent();
            this.viewModel.Messages.Clear();
            GenerateMessages();
        }

        private void GenerateMessages()
        {
            this.viewModel.Messages.Add(new ImageMessage()
            {
                Aspect = Xamarin.Forms.Aspect.AspectFill,
                Source = "resource://GettingStarted.bird.gif",
                Author = new Author() { Name = "Andrea", Avatar = "People_Circle2.png" },
            });

            this.viewModel.Messages.Add(new ImageMessage()
            {
                Aspect = Xamarin.Forms.Aspect.AspectFit,
                Source = "Image1.jpg",
                Author = new Author() { Name = "Andrea", Avatar = "People_Circle2.png" },
            });

            this.viewModel.Messages.Add(new ImageMessage()
            {
                Aspect = Xamarin.Forms.Aspect.Fill,
                Source = "resource://GettingStarted.bird.gif",
                Author = new Author() { Name = "Andrea", Avatar = "People_Circle2.png" },
            });
        }
    }
}
{% endhighlight %}
{% endtabs %}

**CustomImageView created in the sample level with `FFImageLoading` control loaded as its content to host the GIF** 
{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="UTF-8"?>
<ContentView xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:d="http://xamarin.com/schemas/2014/forms/design"
             xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
             xmlns:ffimageloading="clr-namespace:FFImageLoading.Svg.Forms;assembly=FFImageLoading.Svg.Forms"
             mc:Ignorable="d"
             x:Class="GettingStarted.CustomImageView">
    <ffimageloading:SvgCachedImage 
        HeightRequest="400"
        WidthRequest="2300"
        HorizontalOptions="StartAndExpand" 
        VerticalOptions="Center" 
        Aspect="AspectFit" 
        x:Name="imageWave" 
        Source="{TemplateBinding BindingContext.Source}"
        Margin="0"/>
</ContentView>

{% endhighlight %}
{% highlight c# %}

namespace GettingStarted
{
    [XamlCompilation(XamlCompilationOptions.Compile)]
    public partial class CustomImageView : ContentView
    {
        public CustomImageView()
        {
            InitializeComponent();
        }
    }
}
{% endhighlight %}
{% endtabs %}

You can download the complete project of this demo from [here](https://github.com/SyncfusionExamples/How-to-display-a-GIF-in-Xamarin.Forms-Chat).

## Card Message

You can show a list of interactive cards with each card containing an image, list of buttons and text (title, subtitle and description) to tie in with the cards of popular bot frameworks. Use the [Card.Image](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.Card.html#Syncfusion_XForms_Chat_Card_Image), [Card.Title](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.Card.html#Syncfusion_XForms_Chat_Card_Title), [Card.Subtitle](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.Card.html#Syncfusion_XForms_Chat_Card_Subtitle) and [Card.Description](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.Card.html#Syncfusion_XForms_Chat_Card_Description) properties to display image, title, subtitle and description in a card respectively.

You can also show one or more buttons in a card as options to choose from. Create the [CardButton](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.CardButton.html) with necessary [CardButton.Title](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.CardButton.html#Syncfusion_XForms_Chat_CardButton_Title)(the text to be displayed in the button) and [CardButton.Value](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.CardButton.html#Syncfusion_XForms_Chat_CardButton_Value)(the text value that should be added as response message when button is clicked, usually the title of the card) and add it to the [Card.Buttons](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.Card.html#Syncfusion_XForms_Chat_Card_Buttons) collection.

Upon creating the individual cards, add them to a [Card](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.Card.html) typed collection and assign this collection of cards to the [CardMessage.Cards](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.CardMessage.html#Syncfusion_XForms_Chat_CardMessage_Cards) property. The card message auto-sizes itself in height based on the card contents(the text and button count) of the largest card in the list of cards.

If you dont want to display images, buttons or text(title, subtitle, description) in a card simply do not set values to the required properties. For example if you dont want to display image in a card, do no set any value to the [Card.Image](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.Card.html#Syncfusion_XForms_Chat_Card_Image) property.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
                    <sfChat:SfChat x:Name="sfChat"
                           Messages="{Binding Messages}"
                           CurrentUser="{Binding CurrentUser}"
                           ShowOutgoingMessageAvatar="True" />
	<ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.Chat;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfChat sfChat;
        GettingStartedViewModel viewModel;
        public MainPage()
        {
            InitializeComponent();
            this.sfChat = new SfChat();
            this.viewModel = new GettingStartedViewModel();
            this.sfChat.Messages = viewModel.Messages;
            this.sfChat.CurrentUser = viewModel.CurrentUser;
            this.sfChat.ShowOutgoingMessageAvatar = true;
            this.Content = sfChat;
        }
    }
}

/// <summary>
/// View model class for chat view.
/// </summary>
public class GettingStartedViewModel : INotifyPropertyChanged
{
    private ObservableCollection<object> messages;
	private ObservableCollection<Card> cardsCollection;

    /// <summary>
    /// current user of chat.
    /// </summary>
    private Author currentUser;

    public GettingStartedViewModel()
    {
        this.Messages = new ObservableCollection<object>();
        this.CurrentUser = new Author() { Name = "Nancy", Avatar = "People_Circle16.png" };
		this.GenerateCards();
        this.GenerateMessages();
    }

	private void GenerateCards()
    {
		cardsCollection = new ObservableCollection<Card>();
		Card card1 = new Card()
		{
			Title = "San Francisco",
            Description = "A popular tourist destination, San Francisco is known for its cool summers, fog, steep rolling hills, eclectic mix of architecture, and landmarks, including the Golden Gate Bridge, cable cars, the former Alcatraz Federal Penitentiary, Fisherman's Wharf, and its Chinatown district.",
			Image = "SanFrancisco.png",
		};
		card1.Buttons.Add(new CardButton() { Title = "Choose", Value = "San Francisco" });

		Card card2 = new Card()
		{
			Title = "Miami",
			Description = " Miami, officially the City of Miami, is the seat of Miami-Dade County, and the cultural, economic and financial center of South Florida in the United States. The city covers an area of about 56 square miles between the Everglades to the west and Biscayne Bay to the east.",
			Image = "Miami.png",
		};
		card2.Buttons.Add(new CardButton() { Title = "Choose", Value = "Miammi" });

		Card card3 = new Card()
		{
			Title = "Las Vegas",
			Description = "Las Vegas is an internationally renowned major resort city, known primarily for its gambling, shopping, fine dining, entertainment, and nightlife. The Las Vegas Valley as a whole serves as the leading financial, commercial, and cultural center for Nevada.",
			Image = "LasVegas.png",
		};
		card3.Buttons.Add(new CardButton() { Title = "Choose", Value = "Las Vegas" });

		Card card4 = new Card()
		{
			Title = "Dallas",
			Description = "Dallas, a modern metropolis in north Texas, is a commercial and cultural hub of the region. Downtowns Sixth Floor Museum at Dealey Plaza commemorates the site of President John F. Kennedys assassination in 1963. In the Arts District, the Dallas Museum of Art and the Crow Collection of Asian Art cover thousands of years of art. The sleek Nasher Sculpture Center showcases contemporary sculpture.",
			Image = "Dallas.png",
		};
		card4.Buttons.Add(new CardButton() { Title = "Choose", Value = "Dallas" });

		this.CardsCollection.Add(card1);
		this.CardsCollection.Add(card2);
		this.CardsCollection.Add(card3);
		this.CardsCollection.Add(card4);
    }	
	
    private void GenerateMessages()
    {
        Messages.Add(new CardMessage()
        {
			Cards = CardsCollection,
            Author = new Author(){Name="Stacy", Avatar= ImageSource.FromResource("Stacy.png")}
		});
    }

    /// <summary>
    /// Gets or sets the current user.
    /// </summary>
    public Author CurrentUser
    {
        get
        {
            return this.currentUser;
        }
        set
        {
            this.currentUser = value;
            RaisePropertyChanged("CurrentUser");
        }
    }

    /// <summary>
    /// Gets or sets the message conversation.
    /// </summary>
    public ObservableCollection<object> Messages
    {
        get
        {
            return this.messages;
        }
        set
        {
            this.messages = value;
        }
    }
	
	/// <summary>
    /// Gets or sets the Collection of type <see cref="Card"/>.
    // </summary>
    public ObservableCollection<Card> CardsCollection
    {
		get
		{
			return cardsCollection;
		}
		set
		{
			cardsCollection = value;
			RaiseNotifyPropertyChanged(nameof(CardsCollection));
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
}

{% endhighlight %}
{% endtabs %}

**Card message with button**
![Xamarin Forms chat card message](SfChat_images/xamarin-forms-chat-card-message.png)

**Card message without button**
![Xamarin Forms chat card message](SfChat_images/xamarin-forms-chat-card-message1.png)

### Event and Command

The CardMessage comes with built-in [SfChat.CardTapped](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html) event and [SfChat.CardCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_CardCommand) that will be fired upon tapping a button in a card or tapping any card in the message . You can get the selected `Card`, the clicked `CardButton` and the actual [CardMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.CardMessage.html) via the [CardTappedEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.CardTappedEventArgs.html) as [CardTappedEventArgs.Card](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.CardTappedEventArgs.html#Syncfusion_XForms_Chat_CardTappedEventArgs_Card), [CardTappedEventArgs.Action](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.CardTappedEventArgs.html#Syncfusion_XForms_Chat_CardTappedEventArgs_Action) and [CardTappedEventArgs.Message](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.CardTappedEventArgs.html#Syncfusion_XForms_Chat_CardTappedEventArgs_Message) respectively, in both the `CardTapped` event handler and action of `CardCommand`. Handling this event/command by setting [CardTappedEventArgs.Handled](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.CardTappedEventArgs.html#Syncfusion_XForms_Chat_CardTappedEventArgs_Handled) prevents the `Card.Title` or `CardButton.Value` from getting added as a new message.

N> The `Action` argument in `CardTappedEventArgs` holds a valid value only only when clicking the `CardButton` in a card. Tapping elsewhere inside the card fires the `CardTapped` event and `CardCommand` with `Action` as null in the `CardTappedEventArgs`. If the `CardTappedEventArgs.Action` is null, the `CardTappedEventArgs.Card.Title` is added as a new message, else the `CardTappedEventArgs.Action.Value` is added as a new message.

**Card Tapped Event**
{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
                    <sfChat:SfChat x:Name="sfChat"
                           Messages="{Binding Messages}"
                           CurrentUser="{Binding CurrentUser}"
                           CardTapped="ChatCardTapped"/>
	<ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.Chat;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfChat sfChat;
        GettingStartedViewModel viewModel;
        public MainPage()
        {
            InitializeComponent();
            this.sfChat = new SfChat();
            this.viewModel = new GettingStartedViewModel();
            this.sfChat.Messages = viewModel.Messages;
            this.sfChat.CurrentUser = viewModel.CurrentUser;
            this.Content = sfChat;
        }
		
		private void ChatCardTapped(object sender, Syncfusion.XForms.Chat.CardTappedEventArgs e)
        {
             e.Message.HideAfterSelection = false;
        }
    }
}
{% endhighlight %}
{% endtabs %}

**Card Command**
{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
                    <sfChat:SfChat x:Name="sfChat"
                           Messages="{Binding Messages}"
                           CurrentUser="{Binding CurrentUser}"
                           CardCommand="{Binding CardTappedCommand}"/>
	<ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}
//ViewModel.cs
public class GettingStartedViewModel : INotifyPropertyChanged
...
public GettingStartedViewModel()
{
	this.Messages = new ObservableCollection<object>();
	this.CurrentUser = new Author() { Name = "Nancy", Avatar = "People_Circle16.png" };
	this.GenerateCards();
	this.GenerateMessages();
	this.CardTappedCommand = new Command(CardTapped);
}
private void CardTapped(object args)
{
	(args as CardTappedEventArgs).Handled = true;
}
...
{% endhighlight %}
{% endtabs %}

## Template for message

SfChat allows to load custom templates for all incoming and outgoing message using [SfChat.MessageTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_MessageTemplate) property. You can customize the message views as per your liking with the support to load template for each individual message by using a custom template selector derived from [ChatMessageTemplateSelector](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.ChatMessageTemplateSelector.html) and assigning it to [SfChat.MessageTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_MessageTemplate) as shown below. Load custom templates based on the message type, text, author, etc. The limits are endless.

We have loaded a custom template if the message's text contains a particular text value in the below code example.

{% tabs %}
{% highlight c# %}
using Syncfusion.XForms.Chat;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfChat sfChat;
        GettingStartedViewModel viewModel;
        public MainPage()
        {
            InitializeComponent();
            sfChat = new SfChat();
            viewModel = new GettingStartedViewModel();
            this.sfChat.Messages = viewModel.Messages;
            this.sfChat.CurrentUser = viewModel.CurrentUser;
            this.sfChat.MessageTemplate = new MyCustomMessageTemplateSelector() { Chat = this.sfChat };
            this.Content = sfChat;
        }
    }
}

public class MyCustomMessageTemplateSelector : ChatMessageTemplateSelector
{
    private readonly DataTemplate ratingDataTemplate;
    public MyCustomMessageTemplateSelector(SfChat chat) : base(chat)
    {
        this.ratingDataTemplate = new DataTemplate(typeof(RatingTemplate));
    }

    protected override DataTemplate OnSelectTemplate(object item, BindableObject container)
    {
        if (item as ITextMessage != null && item as ITextMessage.Text == "How would you rate your interaction with our travel bot?")
        {
            // returns a custom rating template for this messages.
            return this.ratingDataTemplate; 
        }
        else
        {
            // returns default template for all other messages.
            return base.OnSelectTemplate(item, container);
        }
    }
}
{% endhighlight %}
{% endtabs %}

![Xamarin Forms chat message template](SfChat_images/xamarin-forms-chat-message-template.png)

You can also download the entire source code of this demo [here](https://github.com/SyncfusionExamples/Chat-Message-Template-Xamarin.Forms).


## Sending message

The [SfChat.CurrentUser](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_CurrentUser) can send messages using the send button in the message input area at the bottom of the chat control. Tapping the send button or pressing <kbd>Enter</kbd> key (in UWP) will create a new text message with the text in the editor and add it to the [SfChat.Messages] collection. The [SfChat.SendMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html) event and [SfChat.SendMessageCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_SendMessageCommand) will be executed upon tapping the send button.

**Cancel the message from sending**

The newly added message can be canceled from sending, in the `SendMessage` event handler and `SendMessageCommand` by setting the [Handled](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SendMessageEventArgs.html#Syncfusion_XForms_Chat_SendMessageEventArgs_Handled) value as `true` in the provided [SendMessageEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SendMessageEventArgs.html).

**SendMessage Event handler**

{% tabs %}
{% highlight c# %}
 
this.sfChat.SendMessage += this.SfChat_SendMessage;

/// <summary>
/// Raised when current user sends message to bot using Chat UI.
/// </summary>
/// <param name="sender"><see cref="SfChat"/> as sender.</param>
/// <param name="e"><see cref="SendMessageEventArgs"/> as parameter.<param>
private void SfChat_SendMessage(object sender, SendMessageEventArgs e)
{
    e.Handled = true;
}

{% endhighlight %}
{% endtabs %}

**SendMessage command**

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
        <sfChat:SfChat x:Name="sfChat"
                       Messages="{Binding Messages}"
                       SendMessageCommand="{Binding SendMessageCommand}"
                       CurrentUser="{Binding CurrentUser}" />
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}

/// <summary>
/// View model class for chat view.
/// </summary>
public class GettingStartedViewModel : INotifyPropertyChanged
{
    private ICommand sendMessageCommand;

    /// <summary>
    /// current user of chat.
    /// </summary>
    private Author currentUser;
    
    public GettingStartedViewModel()
    {
        SendMessageCommand = new SendMessageCommandExt();
    }

    /// <summary>
    /// Gets or sets the message conversation.
    /// </summary>
    public ICommand SendMessageCommand
    {
        get
        {
            return this.sendMessageCommand;
        }
        set
        {
            this.sendMessageCommand = value;
            RaisePropertyChanged("SendMessageCommand")
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
}

public class SendMessageCommandExt : ICommand
{
    public event EventHandler CanExecuteChanged;

    public bool CanExecute(object parameter)
    {
        return true;
    }

    public void Execute(object parameter)
    {
        (parameter as SendMessageEventArgs).Handled = true;
    }
}

{% endhighlight %}
{% endtabs %}

## Show keyboard always

By default the keyboard will be open in view, even after a message is sent or focus is lost just like in most mainstream chat applications. To hide the keyboard after the message has been sent or lost focus set the [SfChat.ShowKeyboardAlways](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_ShowKeyboardAlways) property to `false`.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel/>
    </ContentPage.BindingContext>
    
       <ContentPage.Content>
        <sfChat:SfChat x:Name="sfChat"
                       Messages="{Binding Messages}"
                       ShowKeyboardAlways="False"/> />
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% endtabs %}

N> This property is not applicable for Android platform and the keyboard will be hidden after a message is sent or when focus is lost. Refer the below work around to show the keyboard always in android platform.

In the MainActivity.cs of your Xamarin.Forms.Android project, override the `CurrentFocus` property and in its getter, if `SfChatRenderer.IsChatEditorFocused()` method returns true, then return null, else return `base.CurrentFocus` as shown below.

{% tabs %}
{% highlight c# %}
 public class MainActivity : global::Xamarin.Forms.Platform.Android.FormsAppCompatActivity
 {
   ...
   public override View CurrentFocus
        {
            get
            {
                if (SfChatRenderer.IsChatEditorFocused(base.CurrentFocus))
                {
                    return null;
                }

                return base.CurrentFocus;
            }
        }
	...
}
{% endhighlight %}
{% endtabs %}

## Restricting multi-line input in editor (single line messages) in Xamarin.Forms chat

By default the user can type multi-line messages by inserting new lines using the editor in the chat control for outgoing messages. However, you can restrict multi-line input from the users and show a send button in the keyboard so that users can no longer insert a new line in messages by setting the [SfChat.AllowMultilineInput](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_AllowMultilineInput) property as false.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns = "http://xamarin.com/schemas/2014/forms"
            xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
            xmlns:local="clr-namespace:Sample.AutoScroll_ToBottom.ViewModel"
            xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
            x:Class="MultilineMessages">
   <ContentPage.BindingContext>
       <local:ViewModel/>
   </ContentPage.BindingContext>
   <ContentPage.Content>
       <sfChat:SfChat x:Name="sfChat"                    
                      Messages="{Binding Messages}"
                      CurrentUser="{Binding CurrentUser}"
                      AllowMultilineInput="False"/>
   </ContentPage.Content>

{% endhighlight %}
{% endtabs %}

N> In iOS you cannot scroll horizontally on the editor when `AllowMultilineInput` is set as `false`.

## Show avatar and author name for outgoing message

By default the author name and avatar are not displayed for the outgoing messages(messages sent by the [SfChat.CurrentUser](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_CurrentUser)). You can choose to either show or hide the avatar and name for all outgoing messages using the [SfChat.ShowOutgoingMessageAvatar](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_ShowOutgoingMessageAvatar) and [SfChat.ShowOutgoingMessageAuthorName](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_ShowOutgoingMessageAuthorName) properties respectively.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
        <sfChat:SfChat x:Name="sfChat"
                       Messages="{Binding Messages}"
                       CurrentUser="{Binding CurrentUser}" 
                       ShowOutgoingMessageAvatar="True"
                       ShowOutgoingMessageAuthorName="True"/>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% endtabs %}

## Customize the shape of the message

The `SfChat` allows to change the shape of the messages by using the [SfChat.MessageShape](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_MessageShape) property.

To customize `MessageShape` in the SfChat, refer the below code example:

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
        <sfChat:SfChat x:Name="sfChat"
                       Messages="{Binding Messages}"
                       MessageShape="DualTearDrop"
                       CurrentUser="{Binding CurrentUser}" />
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.Chat;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfChat sfChat;
        GettingStartedViewModel viewModel;
        public MainPage()
        {
            InitializeComponent();
            sfChat = new SfChat();
            viewModel = new GettingStartedViewModel();
            this.sfChat.Messages = viewModel.Messages;
            this.sfChat.CurrentUser = viewModel.CurrentUser;
            this.sfChat.MessageShape = MessageShape.DualTearDrop;
            this.Content = sfChat;
        }
    }
}

{% endhighlight %}
{% endtabs %}

![Xamarin Forms chat message shape](SfChat_images/xamarin-forms-chat-dual-tear.png)

## Hide the message input view

The SfChat allows to hide the message input view(editor) by setting false to [SfChat.ShowMessageInputView](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_ShowMessageInputView) property.

To hide `ShowMessageInputView` in the SfChat, refer the below code example:

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
        <sfChat:SfChat x:Name="sfChat"
                       Messages="{Binding Messages}"
                       ShowMessageInputView="False"
                       CurrentUser="{Binding CurrentUser}" />
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.Chat;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfChat sfChat;
        GettingStartedViewModel viewModel;
        public MainPage()
        {
            InitializeComponent();
            sfChat = new SfChat();
            viewModel = new GettingStartedViewModel();
            this.sfChat.Messages = viewModel.Messages;
            this.sfChat.CurrentUser = viewModel.CurrentUser;
            this.sfChat.ShowMessageInputView = false;
            this.Content = sfChat;
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Hide avatar and author name for incoming messages

By default the author name and avatar are displayed for the incoming messages(messages sent by users other than the [SfChat.CurrentUser](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_CurrentUser)). You can choose to either show or hide the avatar and name for all incoming messages using the [SfChat.ShowIncomingMessageAvatar](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_ShowIncomingMessageAvatar) and [SfChat.ShowIncomingMessageAuthorName](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_ShowIncomingMessageAuthorName) properties respectively.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfChat="clr-namespace:Syncfusion.XForms.Chat;assembly=Syncfusion.SfChat.XForms"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage">

    <ContentPage.BindingContext>
        <local:GettingStartedViewModel/>
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
        <sfChat:SfChat x:Name="sfChat"
                       Messages="{Binding Messages}"
                       CurrentUser="{Binding CurrentUser}" 
                       ShowIncomingMessageAvatar="False"
                       ShowIncomingMessageAuthorName="False"/>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% endtabs %}

![Xamarin Forms chat hiding avatar and author visibility](SfChat_images/xamarin-forms-chat-hide-avatar-name.png)


## Messages without author (System Generated Messages / Admin messages) in Xamarin chat

With the help of templates, you can also display messages showing any piece of information, like the security messages in WhatsApp or any other admin messages. These messages can be added to the `SfChat.Messages` collection without any value for `Message.Author`.
In the below code example, we have loaded a custom template if the message's author is null to show a security message from admin.

{% tabs %}
{% highlight c# %}
using Syncfusion.XForms.Chat;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfChat sfChat;
        GettingStartedViewModel viewModel;
        public MainPage()
        {
            InitializeComponent();
            sfChat = new SfChat();
            viewModel = new GettingStartedViewModel();
            this.sfChat.Messages = viewModel.Messages;
            this.sfChat.CurrentUser = viewModel.CurrentUser;
            this.sfChat.MessageTemplate = new CustomMessageTemplateSelector() { Chat = this.sfChat };
            this.Content = sfChat;
        }
    }
}

public class MessageTemplateSelector : ChatMessageTemplateSelector
{
	private readonly DataTemplate customMessageTemplate;
	public MessageTemplateSelector(SfChat sfChat):base(sfChat)
	{
		this.customMessageTemplate = new DataTemplate(typeof(CustomMessageTemplate));
	}

	protected override DataTemplate OnSelectTemplate(object item, BindableObject container)
	{
		var message = item as IMessage;
		if (message == null)
		return null;

		if (item as ITextMessage != null)
		{
			if ((item as ITextMessage).Author == null)
			{
				return customMessageTemplate;
			}
			else
			{
				return base.OnSelectTemplate(item,container);
			}
		}
		else
		{
			return null;
		}
	}
}
{% endhighlight %}
{% endtabs %}

![Xamarin Forms chat message template](SfChat_images/xamarin-forms-chat-systemGenerated-custom-messageTemplate.png)

You can also download the entire source code of this demo [here](https://github.com/SyncfusionExamples/Chat-System-Generated-Message-Template)
