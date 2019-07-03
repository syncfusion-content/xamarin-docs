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

The [`CardTapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.SfCardLayout~CardTapped_EV.html) event occurs when any card view is tapped. The argument contains the following information:

* [`CardView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.SfCardView.html) - Gets the details of a particular card view.

### Command

The `CardTappedCommand` property is used to associate a command with an instance of SfCardLayout. This property is most often set with MVVM pattern to bind callbacks back into the ViewModel.

### CommandParameter

The `CardTappedCommandParameter` property is used to set the parameter reference, based on which the event argument is shown.

>**NOTE**
The default value of the `CardTappedCommandParameter` is `null`.

{% tabs %}
{% highlight xaml %}

<cards:SfCardLayout CardTappedCommand="{Binding CardTappedCommand}" CardTappedCommandParameter= "1">
             <!--Add children for card layout-->
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
            // handle event action.
        }

    }

{% endhighlight %}
{% endtabs %}

## VisibleCardIndexChanging

The `VisibleCardIndexChanging` event occurs when the visible card index is changing. The argument contains the following information:

* `OldCard` - Gets the details of the previous index card.

* `NewCard` - Gets the details of the next possible index card.

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
           // handle event action.
        }
	}


{% endhighlight %}
{% endtabs %}

## VisibleCardIndexChanged

The `VisibleCardIndexChanged` event occurs when the visible card index is changed. The argument contains the following information:

* `OldCard` - Gets the details of the previous card.

* `NewCard` - Gets the details of the current card.

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
              // handle event action.
        }
	}


{% endhighlight %}
{% endtabs %}