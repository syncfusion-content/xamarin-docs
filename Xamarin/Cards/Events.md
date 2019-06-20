---
layout : post
title :  Syncfusion Events in Xamarin.Forms Cards control
description : Cards Events.
platform : xamarin
control : Cards
documentation : ug
---

# Events

## CardTapped

`CardTapped` event is triggered when you tap on any card. The argument contains the following information.

* `CardView` - Used to get the particular card view details .

### Command

The `CardTappedCommand` property is used to associate a command with an instance of SfCard. This property is most often set with MVVM pattern to bind callbacks back into the ViewModel.

### CommandParameter

The `CardTappedCommandParameter` property is used to set the parameter reference to which the event  argument will display the properties associated with that reference.

>**NOTE**
The default value of `CardTappedCommandParameter` is `null`.

{% tabs %}
{% highlight xaml %}

<cards:SfCardLayout CardTappedCommand="{Binding ItemTappedCommand}">
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
            this.BindingContext = new ViewModel();
        }
    }
    public class ViewModel
    {
        void ItemTapped(object obj)
        {
            
        }

        public ICommand ItemTappedCommand { get; set; }
        public ViewModel()
        {
            ItemTappedCommand = new Command<object>(ItemTapped);
        }
    }

{% endhighlight %}
{% endtabs %}

## VisibleCardIndexChanged

`VisibleCardIndexChanged` event gets triggered when the visible card index gets changed. The argument contains the following information.

* `OldCard` - used to get the details on the card before changing.

* `NewCard` - used to get the details on the card after changed.

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
	void VisibleCardIndexChanged(object sender Syncfusion.XForms.Cards.VisibleCardIndexChangedEventArgs e)
        {
      
        }
        public MainPage()
        {
            InitializeComponent();
			SfCardLayout cardLayout = new SfCardLayout();
            cardLayout.VisibleCardIndexChanged += VisibleCardIndexChanged;

            //Add children for card layout 
            cardLayout.Children.Add(new SfCardView(){Content = new Label(){ Text="Cyan", BackgroundColor=Color.Cyan }});

            cardLayout.Children.Add(new SfCardView(){Content = new Label(){ Text="Yellow", BackgroundColor=Color.Yellow }});

            cardLayout.Children.Add(new SfCardView(){Content = new Label(){ Text="Orange", BackgroundColor=Color.Orange }});
        }
	}


{% endhighlight %}
{% endtabs %}

## VisibleCardIndexChanging

`VisibleCardIndexChanging` event gets triggered when the visible card index gets changing. The argument contains the following information.

* `OldCard` - used to get the details on the card before changing.

* `NewCard` - used to get the details of the card which is going to update in the view.

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
	void VisibleCardIndexChanging(object sender, Syncfusion.XForms.Cards.VisibleCardIndexChangingEventArgs e)
        {
            
        }
        public MainPage()
        {
            InitializeComponent();
			SfCardLayout cardLayout = new SfCardLayout();
            cardLayout.VisibleCardIndexChanging += VisibleCardIndexChanging;

            //Add children for card layout 
            cardLayout.Children.Add(new SfCardView(){Content = new Label(){ Text="Cyan", BackgroundColor=Color.Cyan }});

            cardLayout.Children.Add(new SfCardView(){Content = new Label(){ Text="Yellow", BackgroundColor=Color.Yellow }});

            cardLayout.Children.Add(new SfCardView(){Content = new Label(){ Text="Orange", BackgroundColor=Color.Orange }});
        }
	}


{% endhighlight %}
{% endtabs %}







