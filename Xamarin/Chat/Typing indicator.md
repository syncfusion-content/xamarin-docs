---
layout: post
title: Overview | SfChat | Xamarin | Syncfusion
description: Describes about the typing indicator feature and its customizations in Xamarin.Forms chat.
platform: xamarin
control: SfChat
documentation: ug
---

# Typing indicator

Indicates with an animation, that a user(or users) is currently typing, thereby providing an enhanced user experience. To show/hide the typing indicator set the [SfChat.ShowTypingIndicator](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~ShowTypingIndicator.html) property to `true` or `false` respectively. To show user image and text in the typing indicator create a new instance of `SfChat.TypingIndicator`, set the [TypingIndicator.Authors](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~TypingIndicator.html) and [TypingIndicator.Text]() property and assign the typing indicator instance to the [SfChat.TypingIndicator](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~TypingIndicator.html) property.


To define `TypingIndicator` in SfChat, follow the code example:

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
        this.TypingIndicator.Text = "Harrison is typing";
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
    /// Gets or sets the value indicating whether the ng indicator is visible or not.
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
    /// Gets or sets the current author.
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
    public event PropertyChangedEventHandler ertyChanged;

    /// <summary>
    /// Occurs when property is changed.
    /// </summary>
    /// <param name="propName">changed property name</m>
    public void RaisePropertyChanged(string propName)
    {
        if (this.PropertyChanged != null)
        {
            this.PropertyChanged(this, new ertyChangedEventArgs(propName));
        }
    }
}

{% endhighlight %}
{% endtabs %}


## Customize type of avatar view

Typing indicator avatar view type can be customized by using [ChatTypingIndicator.AvatarViewType](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.ChatTypingIndicator~AvatarViewType.html) property.


To define `AvatarViewType` in typing indicator, follow the code example:

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

public class GettingStattedViewModel : ifyPropertyChanged
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
    
    public GettingStattedViewModel()
    {
        this.messages = new ObservableCollection<object>();
        this.TypingIndicator = new ChatTypingIndicator();
        this.TypingIndicator = new ChatTypingIndicator();
        this.TypingIndicator.Authors.Add(new Author() {  = "Harrison", Avatar = "People_Circle14.png" }        
        **this.TypingIndicator.AvatarViewType = arViewType.Text;**
        
        this.TypingIndicator.Text = "Harrison is typing";
        this.ShowTypingIndicator = true;
        this.currentUser = new Author() { Name = "Nancy", ar = "People_Circle16.png" };
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
    /// Gets or sets the value indicating whether the ng indicator is visible or not.
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

    /// <summary>
    /// Gets or sets the current author.
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
    public event PropertyChangedEventHandler ertyChanged;

    /// <summary>
    /// Occurs when property is changed.
    /// </summary>
    /// <param name="propName">changed property name</m>
    public void RaisePropertyChanged(string propName)
    {
        if (this.PropertyChanged != null)
        {
            this.PropertyChanged(this, new ertyChangedEventArgs(propName));
        }
    }
}

{% endhighlight %}
{% endtabs %}

