---
layout: post
title: Overview | SfChat | Xamarin | Syncfusion
description: Describes about the suggestion feature and its functionalities in forms chat.
platform: xamarin
control: SfChat
documentation: ug
---

# Suggestions

The SfChat allows to show a list of options as suggestions to choose from in a message or at the bottom of the Chat control. suggestions list can be shown in all types of chat messages. [SfChat.SuggestionItemSelected](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~SuggestionItemSelected_EV.html) event and [SfChat.SuggestionItemSelectedCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~SuggestionItemSelectedCommand.html) will be raised when current user selects suggestion.

## Showing suggestions in message

Suggestions can be shown in message by setting the [ChatSuggestion](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.ChatSuggestions.html) to [MessageBase.Suggestions](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.MessageBase~Suggestions.html) property.

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
            this.Content = sfChat;
        }
    }

    public class GettingStattedViewModel : INotifyPropertyChanged
    {
        private ObservableCollection<object> messages;

        /// <summary>
        /// current user of chat.
        /// </summary>
        private Author currentUser;

        private ChatSuggestions chatSuggestions;

        private ObservableCollection<ISuggestion> suggestions;

        public GettingStattedViewModel()
        {
            this.messages = new ObservableCollection<object>();
            this.currentUser = new Author() { Name = "Nancy", Avatar = "People_Circle16.png" };
            
            chatSuggestions = new ChatSuggestions();
            
            suggestions = new ObservableCollection<ISuggestion>();
            suggestions.Add(new Suggestion() { Text = "Airways 1" });
            suggestions.Add(new Suggestion() { Text = "Airways 2" });
            suggestions.Add(new Suggestion() { Text = "Airways 3" });
            suggestions.Add(new Suggestion() { Text = "Airways 4" });
            suggestions.Add(new Suggestion() { Text = "Airways 5" });
            suggestions.Add(new Suggestion() { Text = "Airways 6" });

            chatSuggestions.Items = suggestions;

            this.GenerateMessages();
        }

        /// <summary>
        /// Gets or sets the group message conversation.
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
            this.messages.Add(new TextMessage()
            {
                Author = currentUser,
                Text = "Flight to USA",
                ShowAvatar = true,
            });

            this.messages.Add(new TextMessage()
            {
                Author = new Author() { Avatar = "Aeroplane.png", Name = "Travel Bot" },
                Text = "Here's my suggestion",
                Suggestions = chatSuggestions,
                ShowAvatar = true,
            });   
        }
    }
}

{% endhighlight %}
{% endtabs %}


### Add an image in suggestion item

suggestion allows to add image in suggestion list by setting image source to [Suggestion.Image](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.Suggestion~Image.html) property.

To add image in suggestion list in message, follow the code example:

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
                       ShowTimeBreak="True"
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
            this.Content = sfChat;
        }
    }

    public class GettingStattedViewModel : INotifyPropertyChanged
    {
        private ObservableCollection<object> messages;

        /// <summary>
        /// current user of chat.
        /// </summary>
        private Author currentUser;

        private ChatSuggestions chatSuggestions;

        private ObservableCollection<ISuggestion> suggestions;

        public GettingStattedViewModel()
        {
            this.messages = new ObservableCollection<object>();
            this.currentUser = new Author() { Name = "Nancy", Avatar = "People_Circle16.png" };
            
            chatSuggestions = new ChatSuggestions();
            
            suggestions = new ObservableCollection<ISuggestion>();
            suggestions.Add(new Suggestion("Airways 1", "Flight1.png"));
            suggestions.Add(new Suggestion("Airways 2", "Flight2.png"));
            suggestions.Add(new Suggestion("Airways 3", "Flight3.png"));
            suggestions.Add(new Suggestion("Airways 4", "Flight4.png"));
            suggestions.Add(new Suggestion("Airways 5", "Flight5.png"));
            suggestions.Add(new Suggestion("Airways 6", "Flight6.png"));

            chatSuggestions.Items = suggestions;

            this.GenerateMessages();
        }

        /// <summary>
        /// Gets or sets the group message conversation.
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
            this.messages.Add(new TextMessage()
            {
                Author = currentUser,
                Text = "Flight to USA",
                ShowAvatar = true,
            });

            this.messages.Add(new TextMessage()
            {
                Author = new Author() { Avatar = "Aeroplane.png", Name = "Travel Bot" },
                Text = "Here's my suggestion",
                Suggestions = chatSuggestions,
                ShowAvatar = true,
            });   
        }
    }
}

{% endhighlight %}
{% endtabs %}


### Change the orientation of suggestions

suggestion list orientation can be changed by setting [ChatSuggestions.Orientation](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.ChatSuggestions~Orientation.html)

To change suggestion `ChatSuggestions.Orientation`, follow the code example:

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
            this.Content = sfChat;
        }
    }

    public class GettingStattedViewModel : INotifyPropertyChanged
    {
        private ObservableCollection<object> messages;

        /// <summary>
        /// current user of chat.
        /// </summary>
        private Author currentUser;

        private ChatSuggestions chatSuggestions;

        private ObservableCollection<ISuggestion> suggestions;

        public GettingStattedViewModel()
        {
            this.messages = new ObservableCollection<object>();
            this.currentUser = new Author() { Name = "Nancy", Avatar = "People_Circle16.png" };
            
            chatSuggestions = new ChatSuggestions();
            
            suggestions = new ObservableCollection<ISuggestion>();
            suggestions.Add(new Suggestion("Airways 1", "Flight1.png"));
            suggestions.Add(new Suggestion("Airways 2", "Flight2.png"));
            suggestions.Add(new Suggestion("Airways 3", "Flight3.png"));
            suggestions.Add(new Suggestion("Airways 4", "Flight4.png"));
            suggestions.Add(new Suggestion("Airways 5", "Flight5.png"));
            suggestions.Add(new Suggestion("Airways 6", "Flight6.png"));

            **chatSuggestions.Orientation = SuggestionsOrientation.Vertical;**

            chatSuggestions.Items = suggestions;

            this.GenerateMessages();
        }

        /// <summary>
        /// Gets or sets the group message conversation.
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
            this.messages.Add(new TextMessage()
            {
                Author = currentUser,
                Text = "Flight to USA",
                ShowAvatar = true,
            });

            this.messages.Add(new TextMessage()
            {
                Author = new Author() { Avatar = "Aeroplane.png", Name = "Travel Bot" },
                Text = "Here's my suggestion",
                Suggestions = chatSuggestions,
                ShowAvatar = true,
            });   
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Showing suggestions at bottom of chat control

The SfChat allows to show a list of options as suggestions at bottom of chat control by defining [SfChat.Suggestions](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~Suggestions.html) property.


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

            chatSuggestions = new ChatSuggestions();
            suggestions = new ObservableCollection<ISuggestion>();
            suggestions.Add(new Suggestion("Airways 1", "Flight1.png"));
            suggestions.Add(new Suggestion("Airways 2", "Flight2.png"));
            suggestions.Add(new Suggestion("Airways 3", "Flight3.png"));
            suggestions.Add(new Suggestion("Airways 4", "Flight4.png"));
            suggestions.Add(new Suggestion("Airways 5", "Flight5.png"));
            suggestions.Add(new Suggestion("Airways 6", "Flight6.png"));

            chatSuggestions.Items = suggestions;

            this.sfChat.Suggestions = chatSuggestions;

            this.Content = sfChat;
        }
    }

    public class GettingStattedViewModel : INotifyPropertyChanged
    {
        private ObservableCollection<object> messages;

        /// <summary>
        /// current user of chat.
        /// </summary>
        private Author currentUser;

        public GettingStattedViewModel()
        {
            this.messages = new ObservableCollection<object>();
            this.currentUser = new Author() { Name = "Nancy", Avatar = "People_Circle16.png" };
            
            this.GenerateMessages();
        }

        /// <summary>
        /// Gets or sets the group message conversation.
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
            this.messages.Add(new TextMessage()
            {
                Author = currentUser,
                Text = "Flight to USA",
                ShowAvatar = true,
            });
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Cancel the suggestions from closing

The list of suggestions will be closed by default after the current user has selected the option. suggestion list closing can be cacelled using `SfChat.SuggestionItemSelected` event or `SfChat.SuggestionItemSelectedCommand` command.

### SuggestionItemSelected event

{% tabs %}
{% highlight c# %}
 
this.sfChat.SuggestionItemSelected += this.SfChat_SuggestionItemSelected;

/// <summary>
/// Raised when current user has selected the suggestion option from suggestion list.
/// </summary>
/// <param name="sender"><see cref="SfChat"/> as sender</param>
/// <param name="e"><see cref="SuggestionItemSelectedEventArgs"/> as parameter</param>
private void SfChat_SuggestionItemSelected(object sender, SuggestionItemSelectedEventArgs e)
{
    // Suggestion list not closed after selection.
    e.HideAfterSelection = false;
}

{% endhighlight %}
{% endtabs %}

#### SuggestionItemSelectedCommand command

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
                       
                       CurrentUser="{Binding CurrentUser}" />
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight C# %}
/// <summary>
/// View model class for chat view.
/// </summary>
public class GettingStattedViewModel : INotifyPropertyChanged
{
    /// <summary>
    /// current user of chat.
    /// </summary>
    private Author currentUser;
    
    private ICommand suggestionItemSelectedCommand;

    public GettingStattedViewModel()
    {
        SuggestionItemSelectedCommand = new SuggestionItemSelectedCommandExt();
    }

    /// <summary>
    /// Gets or sets the suggestion item selected command.
    /// </summary>
    public ICommand SuggestionItemSelectedCommand
    {
        get
        {
            return this.suggestionItemSelectedCommand;
        }
        set
        {
            this.suggestionItemSelectedCommand = value;
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

public class SuggestionItemSelectedCommandExt : ICommand
{
    public event EventHandler CanExecuteChanged;

    public bool CanExecute(object parameter)
    {
        return true;
    }

    public void Execute(object parameter)
    {
        var args = parameter as SuggestionItemSelectedEventArgs;
        args.HideAfterSelection = false;
    }
}

{% endhighlight %}
{% endtabs %}
