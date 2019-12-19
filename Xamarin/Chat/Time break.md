---
layout: post
title: Overview | SfChat | Xamarin | Syncfusion
description: Describes about the time break view and its functionalities and customizaation in forms chat.
platform: xamarin
control: SfChat
documentation: ug
---

# Time break

The chat control provides a convenient way to group messages based on the date and time the messages were created. So, users can easily identify the messages in the order they were created. Time break template is defined by setting true to [SfChat.ShowTimeBreak](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~ShowTimeBreak.html)

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
                       ShowTimeBreak="True"
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
            this.sfChat.ShowTimeBreak="True"
            this.Content = sfChat;
        }
    }
}

## Stick time break view

To stick the time break view, enable the property [SfChat.StickyTimeBreak](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~StickyTimeBreak.html). If `StickyTimeBreak` is true, the corresponding time break view will be displayd until the last time break view goes out of view, and time break will move when another time break leads while scrolling.


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
                       ShowTimeBreak="True"
                       StickyTimeBreak="True"
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
            this.sfChat.ShowTimeBreak="True"
            this.sfChat.StickyTimeBreak = true;
            this.Content = sfChat;
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Template for time break view

Sfchat allows to craete custom template for time break view using [SfChat.TimeBreakTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChat.XForms~Syncfusion.XForms.Chat.SfChat~TimeBreakTemplate.html). 

To apply custom `TimeBreakTemplate` in the SfChat, follow the code example:

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
            this.sfChat.ShowTimeBreak="True"
            this.sfChat.TimeBreakTemplate = new TimeBreakTemplateSelector();
            this.Content = sfChat;
        }
    }
}

internal class TimeBreakTemplateSelector : DataTemplateSelector
{
    /// <summary>
    /// Returns the template based on the message's date time.
    /// </summary>
    /// <param name="item">The <see cref="GroupResult"/> of the grouped row.</param>
    /// <param name="container">The <see cref="ChatListView"/> as <see cref="BindableObject"/>.</param>
    /// <returns>The <see cref="SfBorder"/> control which contains templates for the grouped row.</returns>
    protected override DataTemplate OnSelectTemplate(object item, BindableObject container)
    {
        string dateString = (item as GroupResult).Key.ToString();
        DateTime groupedDate = DateTime.ParseExact(dateString, "d/M/yyyy", CultureInfo.InvariantCulture);
        string formatDate = string.Format("{0:dd MMMM yyyy}", groupedDate);
        
        Grid grid = new Grid();
        grid.Padding = new Thickness(3, 4, 2, 0);
        
        grid.RowDefinitions = new RowDefinitionCollection()
        {
            new RowDefinition(){Height = 20},
        };

        grid.ColumnDefinitions = new ColumnDefinitionCollection()
        {
            new ColumnDefinition(){ Width = GridLength.Star},
            new ColumnDefinition(){ Width = GridLength.Auto},
            new ColumnDefinition(){ Width = GridLength.Star},
        };

        SfBorder border = new SfBorder();
        border.VerticalOptions = LayoutOptions.Center;
        border.HorizontalOptions = LayoutOptions.Center;
        border.BorderColor = Color.FromHex("#FDE490");
        border.CornerRadius = 13;
        border.BorderWidth = 1.5;

        Label label = new Label();
        label.FontSize = 11;
        label.VerticalOptions = LayoutOptions.Center;
        label.HorizontalOptions = LayoutOptions.Center;
        label.HorizontalTextAlignment = TextAlignment.Center;
        label.TextColor = Color.FromHex("#98770E");
        label.FontAttributes = FontAttributes.Bold;
        label.BackgroundColor = Color.FromHex("#FDF4D6");

        border.Content = label;
        
        grid.Children.Add(new BoxView() { HeightRequest = 2, BackgroundColor = Color.Black, HorizontalOptions =LayoutOptions.FillAndExpand, VerticalOptions = LayoutOptions.CenterAndExpand },0,0);
        grid.Children.Add(new BoxView() { HeightRequest = 2, BackgroundColor = Color.Black, HorizontalOptions =LayoutOptions.FillAndExpand, VerticalOptions = LayoutOptions.CenterAndExpand },2,0);

        if (groupedDate.Date == DateTime.Now.Date)
        {
            label.WidthRequest = 60;
            label.Text = "TODAY";
            grid.Children.Add(border, 1, 0);
            return new DataTemplate(() =>
            {
                return grid;
            });
        }
        else
        {
            label.WidthRequest = 120;
            label.Text = formatDate;
            grid.Children.Add(border, 1, 0);
            return new DataTemplate(() =>
            {
                return grid;
            });
        }
    }
}

{% endhighlight %}
{% endtabs %}