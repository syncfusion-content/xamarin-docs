---
layout: post
title: Typing indicator in Xamarin.Forms Chat | SfChat | Xamarin | Syncfusion
description: Describes about the typing indicator feature and its available customizations in Xamarin.Forms chat control.
platform: xamarin
control: SfChat
documentation: ug
---

# Typing indicator in Xamarin.Forms Chat (SfChat)

Indicates with an animation, that a user(or users) is currently typing, thereby providing an enhanced user experience. To show/hide the typing indicator set the [SfChat.ShowTypingIndicator](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_ShowTypingIndicator) property to `true` or `false` respectively. To show user image and text in the typing indicator create a new instance of `SfChat.TypingIndicator`, set the [TypingIndicator.Authors](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.ChatTypingIndicator.html#Syncfusion_XForms_Chat_ChatTypingIndicator_Authors) and [TypingIndicator.Text](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.ChatTypingIndicator.html#Syncfusion_XForms_Chat_ChatTypingIndicator_Text) property and assign the typing indicator instance to the [SfChat.TypingIndicator](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_TypingIndicator) property.


To define `TypingIndicator` in SfChat, refer the below code example:

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
                       TypingIndicator="{Binding TypingIndicator}"
                       ShowTypingIndicator="{Binding ShowTypingIndicator}"
                       CurrentUser="{Binding CurrentUser}"
                       ShowOutgoingMessageAvatar="True"/>
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
            this.sfChat.TypingIndicator = viewModel.TypingIndicator;
            this.sfChat.ShowTypingIndicator = viewModel.ShowTypingIndicator;
            this.Content = sfChat;
        }
    }
}

public class GettingStartedViewModel : INotifyPropertyChanged
{
    private ObservableCollection<object> messages;

    /// <summary>
    /// current user of chat.
    /// </summary>
    private Author currentUser;

    /// <summary>
    /// Indicates the typing indicator visibility. 
    /// </summary>
    private bool showTypingIndicator;

    /// <summary>
    /// Chat typing indicator.
    /// </summary>
    private ChatTypingIndicator typingIndicator;

    public GettingStartedViewModel()
    {
        this.Messages = new ObservableCollection<object>();
        this.TypingIndicator = new ChatTypingIndicator();
        this.TypingIndicator.Authors.Add(new Author() { Name = "Harrison", Avatar = "People_Circle14.png" }        
        this.TypingIndicator.AvatarViewType = AvatarViewType.Image;
        this.TypingIndicator.Text = "Harrison is typing...";
        this.ShowTypingIndicator = true;
        this.CurrentUser = new Author() { Name = "Nancy", Avatar = "People_Circle16.png" };
    }

    /// <summary>
    /// Gets or sets the Chat typing indicator value.
    /// </summary>
    public ChatTypingIndicator TypingIndicator
    {
        get
        {
            return this.typingIndicator;
        }
        private set
        {
            this.typingIndicator = value;
            RaisePropertyChanged("TypingIndicator");
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
    /// Gets or sets the value indicating whether the typing indicator is visible or not.
    /// </summary>
    public bool ShowTypingIndicator
    {
        get
        {
            return this.showTypingIndicator;
        }
        set
        {
            this.showTypingIndicator = value;
            RaisePropertyChanged("ShowTypingIndicator");
        }
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
    /// Property changed handler.
    /// </summary>
    public event PropertyChangedEventHandler PropertyChanged;

    /// <summary>
    /// Occurs when property is changed.
    /// </summary>
    /// <param name="propName">changed property name</m>
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
            Author = new Author() { Name = "Andrea", Avatar = "People_Circle2.png" },
            Text = "Oh! That's great.",
        });

        this.Messages.Add(new TextMessage()
        {
            Author = new Author() { Name = "Harrison", Avatar = "People_Circle14.png" },
            Text = "That is good news.",
        });

        this.Messages.Add(new TextMessage()
        {
            Author = new Author() { Name = "Margaret", Avatar = "People_Circle7.png" },
            Text = "What kind of application is it and when are we going to launch?",
        });
    }
}

{% endhighlight %}
{% endtabs %}

![Xamarin Forms chat typing indicator with image](SfChat_images/xamarin-forms-chat-typing-Indicator-image.png)

## Customize avatar view of typing indicator

The avatar view in the typing indicator can be customized to show only starting alphabet of the user name or only image of the user as avatar by using [ChatTypingIndicator.AvatarViewType](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.ChatTypingIndicator.html#Syncfusion_XForms_Chat_ChatTypingIndicator_AvatarViewType) property.


To change the `AvatarViewType` in typing indicator, refer the below code example:

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
                       TypingIndicator="{Binding TypingIndicator}"
                       ShowTypingIndicator="{Binding ShowTypingIndicator}"
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
            this.sfChat.TypingIndicator = viewModel.TypingIndicator;
            this.sfChat.ShowTypingIndicator = viewModel.ShowTypingIndicator;
            this.Content = sfChat;
        }
    }
}

public class GettingStattedViewModel : INotifyPropertyChanged
{
    /// <summary>
    /// Indicates the typing indicator visibility. 
    /// </summary>
    private bool showTypingIndicator;

    /// <summary>
    /// Chat typing indicator.
    /// </summary>
    private ChatTypingIndicator typingIndicator;
    
    public GettingStattedViewModel()
    {
        this.TypingIndicator = new ChatTypingIndicator();
        this.TypingIndicator.Authors.Add(new Author() { Name = "Harrison", Avatar = "People_Circle14.png" }        
        
        this.TypingIndicator.AvatarViewType = AvatarViewType.Text;
        
        this.TypingIndicator.Text = "Harrison is typing...";
        this.ShowTypingIndicator = true;
    }

    /// <summary>
    /// Gets or sets the Chat typing indicator value.
    /// </summary>
    public ChatTypingIndicator TypingIndicator
    {
        get
        {
            return this.typingIndicator;
        }
        private set
        {
            this.typingIndicator = value;
            RaisePropertyChanged("TypingIndicator");
        }
    }

    /// <summary>
    /// Gets or sets the value indicating whether the typing indicator is visible or not.
    /// </summary>
    public bool ShowTypingIndicator
    {
        get
        {
            return this.showTypingIndicator;
        }
        private set
        {
            this.showTypingIndicator = value;
            RaisePropertyChanged("ShowTypingIndicator");
        }
    }
}

{% endhighlight %}
{% endtabs %}

![Xamarin Forms chat typing indicator with text](SfChat_images/xamarin-forms-chat-typing-indicator-text.png)

## Notifications when user start/stop typing
 
You can access the typing area in SfChat using [SfChat.Editor](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Chat.SfChat.html#Syncfusion_XForms_Chat_SfChat_Editor) property, listen to its focus change, text change, completed events etc to identify when the user starts/ends typing.

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
                       TypingIndicator="{Binding TypingIndicator}"
                       CurrentUser="{Binding CurrentUser}"
                       ShowOutgoingMessageAvatar="True"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}

using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            // Notifies that user has started typing.
            this.sfChat.Editor.TextChanged += Editor_TextChanged;
            // Notifies that user has stopped typing.
            this.sfChat.Editor.Unfocused += Editor_Unfocused;
        }      

        private void Editor_Unfocused(object sender, FocusEventArgs e)
        {
            // User has stopped typing
            this.sfChat.ShowTypingIndicator = false;
        }

        private void Editor_TextChanged(object sender, TextChangedEventArgs e)
        {
            // User has started typing
            this.sfChat.ShowTypingIndicator = true;
        }
    }
}

{% endhighlight %}
{% endtabs %} 
