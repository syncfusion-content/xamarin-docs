---
layout : post
title :  Syncfusion events in Xamarin.Forms Cards control
description : Cards Events.
platform : xamarin
control : Cards
documentation : ug
---

# Events

## CardTapped

[`CardTapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.SfCardLayout~CardTapped_EV.html) event is triggered when you tap on any card view. The argument contains the following information.

* [`CardView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.SfCardView.html) - Used to get the particular card view details .

### Command

The `CardTappedCommand` property is used to associate a command with an instance of SfCardLayout. This property is most often set with MVVM pattern to bind callbacks back into the ViewModel.

### CommandParameter

The `CardTappedCommandParameter` property is used to set the parameter reference to which the event argument must contains.

>**NOTE**
The default value of `CardTappedCommandParameter` is `null`.

{% tabs %}
{% highlight xaml %}

<cards:SfCardLayout CardTappedCommand="{Binding CardTappedCommand}">

		<cards:SfCardView>
			<Label Text="Cyan" BackgroundColor="Cyan" />
		</cards:SfCardView>

		<cards:SfCardView>
			<Label Text="Yellow" BackgroundColor="Yellow" />
		</cards:SfCardView>

		<cards:SfCardView>
			<Label Text="Orange" BackgroundColor="Orange" />
		</cards:SfCardView>

</cards:SfCardLayout>
{% endhighlight %}

{% highlight c# %}

    public class ViewModel
    {
        public ViewModel()
        {
            ItemTappedCommand = new Command<object>(CardTapped);
        }

        public ICommand CardTappedCommand { get; set; }

        private void CardTapped(object obj)
        {
            // TODO: handle event action.
        }

    }

{% endhighlight %}
{% endtabs %}

## VisibleCardIndexChanging

`VisibleCardIndexChanging` event gets triggered when the visible card index gets changing. The argument contains the following information.

* `OldCard` - used to get the details on the previous index card.

* `NewCard` - used to get the details of the next possible index card.

{% tabs %}
{% highlight xaml %}

<cards:SfCardLayout VisibleCardIndexChanging="VisibleCardIndexChanging" >

		<cards:SfCardView>
			<Label Text="Cyan" BackgroundColor="Cyan" />
		</cards:SfCardView>

		<cards:SfCardView>
			<Label Text="Yellow" BackgroundColor="Yellow" />
		</cards:SfCardView>

		<cards:SfCardView>
			<Label Text="Orange" BackgroundColor="Orange" />
		</cards:SfCardView>

</cards:SfCardLayout>
{% endhighlight %}

{% highlight c# %}

public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
			SfCardLayout cardLayout = new SfCardLayout();
            cardLayout.VisibleCardIndexChanging += VisibleCardIndexChanging;

            //Add children for card layout. 
            cardLayout.Children.Add(new SfCardView() { Content = new Label() { Text = "Cyan", BackgroundColor = Color.Cyan }});

            cardLayout.Children.Add(new SfCardView() { Content = new Label() { Text = "Yellow", BackgroundColor = Color.Yellow }});

            cardLayout.Children.Add(new SfCardView() { Content = new Label() { Text="Orange", BackgroundColor = Color.Orange }});
        }

        private void VisibleCardIndexChanging(object sender, Syncfusion.XForms.Cards.VisibleCardIndexChangingEventArgs e)
        {
            // TODO: handle event action.
        }
	}


{% endhighlight %}
{% endtabs %}

## VisibleCardIndexChanged

`VisibleCardIndexChanged` event gets triggered when the visible card index gets changed. The argument contains the following information.

* `OldCard` - used to get the details on the previous card.

* `NewCard` - used to get the details on the current card.

{% tabs %}
{% highlight xaml %}

<cards:SfCardLayout VisibleCardIndexChanged="VisibleCardIndexChanged" >

		<cards:SfCardView>
			<Label Text="Cyan" BackgroundColor="Cyan" />
		</cards:SfCardView>

		<cards:SfCardView>
			<Label Text="Yellow" BackgroundColor="Yellow" />
		</cards:SfCardView>

		<cards:SfCardView>
			<Label Text="Orange" BackgroundColor="Orange" />
		</cards:SfCardView>

</cards:SfCardLayout>
{% endhighlight %}

{% highlight c# %}

public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
			SfCardLayout cardLayout = new SfCardLayout();
            cardLayout.VisibleCardIndexChanged += VisibleCardIndexChanged;

            //Add children for card layout 
            cardLayout.Children.Add( new SfCardView() { Content = new Label() { Text = "Cyan", BackgroundColor = Color.Cyan }});

            cardLayout.Children.Add(new SfCardView() {Content = new Label() { Text="Yellow", BackgroundColor = Color.Yellow }});

            cardLayout.Children.Add(new SfCardView() {Content = new Label() { Text="Orange", BackgroundColor  = Color.Orange }});
        }

        private void VisibleCardIndexChanged(object sender Syncfusion.XForms.Cards.VisibleCardIndexChangedEventArgs e)
        {
              // TODO: handle event action.
        }
	}


{% endhighlight %}
{% endtabs %}