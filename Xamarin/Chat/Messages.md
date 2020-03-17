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
<td>{{'[Message.Author](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.MessageBase~Author.html)'| markdownify }}</td>
<td>Specify the avatar and name of the message sender using {{'[Author.Avatar](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.Author~Avatar.html)'| markdownify }} and {{'[Author.Name](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.Author~Name.html)'| markdownify }} properties respectively.</td>
</tr>
<tr>
<td>{{'[Message.DateTime](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.MessageBase~DateTime.html)'| markdownify }}</td>
<td>To display message created or received time.</td>
</tr>
<tr>
<td>{{'[Message.TimestampFormat](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.MessageBase~TimestampFormat.html)'| markdownify }}</td>
<td>To format the Message.DateTime.</td>
</tr>
</table>

## Setting current user for conversation

The [SfChat.CurrentUser](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~CurrentUser.html) helps differentiate between the sender and receiver of the messages. On any given chat window, the `SfChat.CurrentUser` is meant to be the sender(author of outgoing messages). Refer the below code example to set up a current user in a chat.

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

[TextMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.TextMessage.html) is used to display plain text as a message. The following code example explains how to add a simple text message.

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
            this.sfChat.ShowIncomingMessageAvatar = true;
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

[DatePickerMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.DatePickerMessage.html) is used to show a date picker as a message to let users select a date. Once a date is selected, the selected date will be added as a `TextMessage` in the chat window. The [SendMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~SendMessage_EV.html) event and [SendMessageCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~SendMessageCommand.html) will be executed upon selecting a date from the date picker.

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

[TimePickerMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.TimePickerMessage.html) is used to show a time picker as a message to let users select time. Once time is selected, the selected time is added as a `TextMessage`. The`SfChat.SendMessage` event and `SfChat.SendMessageCommand` will be executed upon selecting a time from the time picker.

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

[CalendarMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.CalendarMessage.html) is used to display a calendar as a message to let users select a date. The date selected from the calendar will be added as a `TextMessage`. The `SendMessage` event and `SendMessageCommand` will be executed upon selecting a date from the calendar.

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

[HyperlinkMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.HyperlinkMessage.html) is used to share URL as a message. Along with the link, the thumbnail, title and description of the URL are automatically fetched and displayed. The following code example illustrates how to add a hyperlink message.

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

## Sending message

The `SfChat.CurrentUser` can send messages using the send button in the message input area at the bottom of the chat control. Tapping the send button or pressing <kbd>Enter</kbd> key (in UWP) will create a new text message with the text in the editor and add it to the [SfChat.Messages] collection. The `SendMessage` event and `SendMessageCommand`will be executed upon tapping the send button.

**Cancel the message from sending**

The newly added message can be canceled from sending, in the `SendMessage` event handler and `SendMessageCommand` by setting the [Handled](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SendMessageEventArgs~Handled.html) value as `true` in the provided [SendMessageEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SendMessageEventArgs.html).

**SendMessage Event handler**

{% tabs %}
{% highlight c# %}
 
this.sfChat.SendMessage += this.SfChat_SendMessage;

/// <summary>
/// Raised when current user sends message to bot using Chat UI.
/// </summary>
/// <param name="sender"><see cref="SfChat"/> as sender.</param>
/// <param name="e"><see cref="SendMessageEventArgs"/> asparameter.<param>
private void SfChat_SendMessage(object sender, SendMessageEventArgse)
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

## Scroll down the chat control to bottom when new message is added

The SfChat allows to scroll down the chat control to bottom programmatically by using the [SfChat.ScrollToMessage(Object)](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~ScrollToMessage.html) method. By default the message is scrolled at end of chat.  

In the below example, chat control is scrolled down to bottom when a new message is added in Messages collection.

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
    <ContentPage.Behaviors>
        <local:MainPageBehavior></local:MainPageBehavior>
    </ContentPage.Behaviors>
    
    <ContentPage.Content>
        <sfChat:SfChat x:Name="sfChat"
                       Messages="{Binding Messages}"
                       SendMessageCommand="{Binding SendMessage}"
                       CurrentUser="{Binding CurrentUser}"
                       ShowOutgoingMessageAvatar="True" />
    </ContentPage.Content>

</ContentPage>


{% endhighlight %}

{% highlight C# %}
 public class MainPageBehavior: Behavior<MainPage>
    {

       private GettingStattedViewModel viewModel;

       private SfChat sfChat;
        public MainPageBehavior()
        {

        }

        protected override void OnAttachedTo(MainPage bindable)
        {
            this.sfChat = bindable.FindByName<SfChat>("sfChat");
            this.viewModel = bindable.FindByName<GettingStattedViewModel>("viewModel");
            this.viewModel.Messages.CollectionChanged += Messages_CollectionChanged;

            base.OnAttachedTo(bindable);
        }

        private async void Messages_CollectionChanged(object sender, System.Collections.Specialized.NotifyCollectionChangedEventArgs e)
        {
            if (e.Action == NotifyCollectionChangedAction.Add)
            {
                foreach (var chatItem in e.NewItems)
                {
                    TextMessage textMessage = chatItem as TextMessage;
                    if (textMessage != null && textMessage.Author == this.viewModel.CurrentUser)
                    {
                       (sender as SfChat).ShowOutgoingMessageAvatar = false;
                    }
                    else
                    {
                        await Task.Delay(50);
                        this.sfChat.ScrollToMessage(chatItem);
                    }
                }
            }

        }

        protected override void OnDetachingFrom(MainPage bindable)
        {
            this.viewModel.Messages.CollectionChanged -= Messages_CollectionChanged;
            this.sfChat = null;
            this.viewModel = null;
            base.OnDetachingFrom(bindable);
        }
    }
{% endhighlight %}
{% endtabs %}

You can download the example from [Github](https://github.com/SyncfusionExamples/How-to-scroll-down-the-chat-control-at-bottom-when-new-message-is-added).

## Show the avatar for outgoing message

By default the author name and avatar are not displayed for the outgoing messages(messages sent by the `SfChat.CurrentUser`). This can be customized in the `SendMessage` event handler or `SendMessageCommand's` execution.

**SendMessage Event handler**

{% tabs %}
{% highlight c# %}
 
this.sfChat.SendMessage += this.SfChat_SendMessage

/// <summary>
/// Raised when current user sends message to bot using Chat UI.
/// </summary>
/// <param name="sender"><see cref="SfChat"/> as sender.</param>
/// <param name="e"><see cref="SendMessageEventArgs"/> as parameter.</param>
private void SfChat_SendMessage(object sender, SendMessageEventArgs e)
{
    (sender as SfChat).ShowOutgoingMessageAvatar = true;
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

{% highlight C# %}

public class SendMessageCommandExt : ICommand
{
    public event EventHandler CanExecuteChanged;
    
    public bool CanExecute(object parameter)
    {
        return true;
    }

    public void Execute(object parameter)
    {
        (parameter as SfChat).ShowOutgoingMessageAvatar = true;
    }
}

{% endhighlight %}
{% endtabs %}

## Customize the shape of the message

The `SfChat` allows to change the shape of the messages by using the [SfChat.MessageShape](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~MessageShape.html) property.

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

The SfChat allows to hide the message input view(editor) by setting false to [SfChat.ShowMessageInputView](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~ShowMessageInputView.html) property.

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

## Hide avatar and author name for messages

The message's avatar and author name visibility can be hidden using [SfChat.ShowAvatar](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~ShowAvatar.html) and [SfChat.ShowAuthorName](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~ShowAuthorName.html) properties respectively.

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
                       ShowOutgoingMessageAvatar="False"
                       ShowIncomingMessageAvatar="False"
					   ShowOutgoingMessageAuthorName="False"
                       ShowIncomingMessageAuthorName="False"
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
            this.sfChat.ShowOutgoingMessageAvatar = false;
            this.sfChat.ShowIncomingMessageAvatar = false;
			this.sfChat.ShowOutgoingMessageAuthorName = false;
            this.sfChat.ShowIncomingMessageAuthorName = false;
            this.Content = sfChat;
        }
    }
}

{% endhighlight %}
{% endtabs %}

![Xamarin Forms chat hiding avatar and author visibility](SfChat_images/xamarin-forms-chat-hide-avatar-name.png)

N> SfChat allows to change visibility of avatar and author name of a particular message using [Message.ShowAvatar](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.MessageBase~ShowAvatar.html) and [Message.ShowAuthorName](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.MessageBase~ShowAuthorName.html). By default the `Message.ShowAvatar` property has higher priority than the `SfChat.ShowAvatar` property.

## Template for message

SfChat allows to load custom templates for incoming and outgoing message using [SfChat.MessageTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~MessageTemplate.html) property. 

To load custom `MessageTemplate` in the SfChat, refer the below code example:

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
            this.sfChat.MessageTemplate = new MyDataTemplateSelector() { Chat = this.sfChat };
            this.Content = sfChat;
        }
    }
}

public class ChatMessageTemplateSelector : DataTemplateSelector
{
    private readonly DataTemplate incomingDataTemplate;
    private readonly DataTemplate outgoingDataTemplate;
    private readonly DataTemplate ratingDataTemplate;

    internal SfChat Chat
    {
        get;
        set;
    }

    public ChatMessageTemplateSelector()
    {
        this.incomingDataTemplate = new DataTemplate(typeof(IncomingTemplate));
        this.outgoingDataTemplate = new DataTemplate(typeof(OutgoingTemplate));
        this.ratingDataTemplate = new DataTemplate(typeof(RatingTemplate));
    }

    protected override DataTemplate OnSelectTemplate(object item, BindableObject container)
    {
        var message = item as IMessage;
        if (message == null)
            return null;


        if (message.Author == Chat.CurrentUser)
        {
            return outgoingDataTemplate;
        }
        else
        {
            if (item as ITextMessage != null)
            {
                if ((item as ITextMessage).Text == "How would you rate your interaction with our travel bot?")
                {
                    return ratingDataTemplate;
                }
                else
                {
                    return incomingDataTemplate;
                }
            }
            else
            {
                return null;
            }
        }
    }
}

{% endhighlight %}
{% endtabs %}

![Xamarin Forms chat message template](SfChat_images/xamarin-forms-chat-message-template.png)

You can also download the entire source code of this demo [here](https://github.com/SyncfusionExamples/Chat-Message-Template-Xamarin.Forms).