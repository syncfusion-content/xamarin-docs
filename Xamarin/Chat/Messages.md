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

[TimePickerMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.TimePickerMessage.html) is used to show a time picker as a message to let users select time. Once time is selected, the selected time is added as a `TextMessage`. The [SfChat.SendMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~SendMessage_EV.html) event and [SfChat.SendMessageCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~SendMessageCommand.html) will be executed upon selecting a time from the time picker.

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

[CalendarMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.CalendarMessage.html) is used to display a calendar as a message to let users select a date. The date selected from the calendar will be added as a `TextMessage`. The [SfChat.SendMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~SendMessage_EV.html) event and [SfChat.SendMessageCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~SendMessageCommand.html) will be executed upon selecting a date from the calendar.

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

## Image message

[ImageMessage](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.ImageMessage.html) is used to display an image as a message. Using the [ImageMessage.Source](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.ImageMessage~Source.html), [ImageMessage.Size](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.ImageMessage~Size.html) and [ImageMessage.Aspect](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.ImageMessage~Aspect.html) properties you can display the desired image in the desired height and width as a message in the chat control.

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

The `ImageMessage` comes with in-built [SfChat.ImageTapped](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~ImageTapped_EV.html) event and [SfChat.ImageTappedCommand](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~ImageTappedCommand.html) that will be fired upon tapping an image message. You can get the instance of the `ImageMessage` that was tapped in the [ImageTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.ImageTappedEventArgs.html) as `ImageTappedEventArgs.Message`. You can handle this event/command to achieve requirements like to show the image in full screen, or show options for sharing the image etc.

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

Unlike the other messages, the `ImageMessage` can also be shown as an outgoing message. To add an `ImageMessage` as an outgoing message just set the [ImageMessage.Author](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.MessageBase~Author.html) as [SfChat.CurrentUser](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~CurrentUser.html). You can also add an image message when clicking the attachment button as shown [here](https://help.syncfusion.com/xamarin/chat/attachment-button).

![Send image message](SfChat_images/ImageMessage_Outgoing.png)

### Displaying a GIF as an image message

You can write style targeting the [ControlTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~ControlTemplate.html) property of the [ChatImageView](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.ChatImageView.html) and add it to the application's resources as shown below. You can assign your custom template view that is capable of loading a GIF image as the `ControlTemplate` of `ChatImageView` using `Style.Setter`. Here in the below code example we have loaded our `CustomImageView` as `ControlTemplate` of the `ChatImageView`.

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

## Sending message

The [SfChat.CurrentUser](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~CurrentUser.html) can send messages using the send button in the message input area at the bottom of the chat control. Tapping the send button or pressing <kbd>Enter</kbd> key (in UWP) will create a new text message with the text in the editor and add it to the [SfChat.Messages] collection. The [SfChat.SendMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~SendMessage_EV.html) event and [SfChat.SendMessageCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~SendMessageCommand.html) will be executed upon tapping the send button.

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

By default the SfChat control is scrolled to the bottom to show the newly added message. If you want to disable this auto scroll, set [SfChat.CanAutoScrollToBottom](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~CanAutoScrollToBottom.html) as `false`. Additionally you can also scroll to a particular message programmatically using the [SfChat.ScrollToMessage(Object)](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~ScrollToMessage.html) method.

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

## Show the avatar for outgoing message

By default the author name and avatar are not displayed for the outgoing messages(messages sent by the [SfChat.CurrentUser](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~CurrentUser.html)). This can be customized in the [SendMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~SendMessage_EV.html) event handler or [SendMessageCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~SendMessageCommand.html) command's execution.

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

The message's avatar and author name visibility can be hidden using [SfChat.ShowOutgoingMessageAvatar](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~ShowOutgoingMessageAvatar.html) ,[SfChat.ShowIncomingMessageAvatar](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~ShowIncomingMessageAvatar.html) ,[SfChat.ShowOutgoingMessageAuthorName](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~ShowOutgoingMessageAuthorName.html) and [SfChat.ShowIncomingMessageAuthorName](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~ShowIncomingMessageAuthorName.html) properties respectively.

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