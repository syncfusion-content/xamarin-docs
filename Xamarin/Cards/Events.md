---
layout: post
title: Syncfusion events in Xamarin.Forms Cards control
description: Learn how to get the notification of CardTapped, VisibleCardIndexChanging, VisibleCardIndexChanged, Dismissing, and Dismissed event in Xamarin.Cards 
platform: xamarin
control: Cards
documentation: ug
---

# Events in Xamarin Cards (SfCards)

## CardTapped

The [`CardTapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.SfCardLayout~CardTapped_EV.html) event occurs when any card view is tapped. The argument contains the following information:

* [`CardView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.SfCardView.html) - Gets the details of a particular card view.

### Command

The [`CardTappedCommand`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.SfCardLayout~CardTappedCommand.html) property is used to associate a command with an instance of `SfCardLayout`. This property is most often set with MVVM pattern to bind callbacks back into the ViewModel.

### CommandParameter

The [`CardTappedCommandParameter`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.SfCardLayout~CardTappedCommandParameter.html) property is used to set the parameter reference, based on which the event argument is shown.

>**NOTE**
The default value of the [`CardTappedCommandParameter`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.SfCardLayout~CardTappedCommandParameter.html) is `null`.

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

The [`VisibleCardIndexChanging`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.SfCardLayout~VisibleCardIndexChanging_EV.html) event occurs when the visible card index is changing. The argument contains the following information:

* [`OldCard`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.VisibleCardIndexChangingEventArgs~OldCard.html) - Gets the details of the previous index card.

* [`NewCard`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.VisibleCardIndexChangingEventArgs~NewCard.html) - Gets the details of the next possible index card.

* [`Cancel`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.Core.CancelEventArgs~Cancel.html) - Gets or sets a value indicating whether the event should be canceled.

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

...
InitializeComponent();
SfCardLayout cardLayout = new SfCardLayout();
cardLayout.VisibleCardIndexChanging += VisibleCardIndexChanging;

//Add children for card layout. 
cardLayout.Children.Add(new SfCardView() { Content = new Label() { Text = "Cyan", BackgroundColor = Color.Cyan }});
cardLayout.Children.Add(new SfCardView() { Content = new Label() { Text = "Yellow", BackgroundColor = Color.Yellow }});
cardLayout.Children.Add(new SfCardView() { Content = new Label() { Text="Orange", BackgroundColor = Color.Orange }});
...

private void VisibleCardIndexChanging(object sender, Syncfusion.XForms.Cards.VisibleCardIndexChangingEventArgs e)
{
// handle event action.
}
...


{% endhighlight %}
{% endtabs %}

## VisibleCardIndexChanged

The [`VisibleCardIndexChanged`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.SfCardLayout~VisibleCardIndexChanged_EV.html) event occurs when the visible card index is changed. The argument contains the following information:

* [`OldCard`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.VisibleCardIndexChangedEventArgs~OldCard.html) - Gets the details of the previous card.

* [`NewCard`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.VisibleCardIndexChangedEventArgs~NewCard.html) - Gets the details of the current card.

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

...
InitializeComponent();
SfCardLayout cardLayout = new SfCardLayout();
cardLayout.VisibleCardIndexChanged += VisibleCardIndexChanged;
...

private void VisibleCardIndexChanged(object sender Syncfusion.XForms.Cards.VisibleCardIndexChangedEventArgs e)
{
    // handle event action.
}
...


{% endhighlight %}
{% endtabs %}

## Dismissing event

The [`Dismissing`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.SfCardView~Dismissing_EV.html) event fires when dismissing the card by swiping with enables `SwipeToDismiss` property. The argument contains the following information:

* [`DismissDirection`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.DismissingEventArgs~DismissDirection.html) - Gets a dismissing direction of the card view.

* [`Cancel`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.Core.CancelEventArgs~Cancel.html) - Gets or sets a value indicating whether the event should be canceled.

{% tabs %}
{% highlight xaml %}

<cards:SfCardView Dismissing="SfCardView_Dismissing" SwipeToDismiss="True">
    <Label Text="SfCardView" />
</cards:SfCardView>

{% endhighlight %}

{% highlight c# %}

...
InitializeComponent();
SfCardView cardView = new SfCardView() { SwipeToDismiss = true };
cardView.Dismissing += SfCardView_Dismissing;
cardView.Content = new Label() { Text = "SfCardView" };
...

private void SfCardView_Dismissing(object sender, Syncfusion.XForms.Cards.DismissingEventArgs e)
{
    e.Cancel = true;
}
...

{% endhighlight %}
{% endtabs %}

N> This event will not work when adding the `SfCardView` as a child of `SfCardLayout`.

## Dismissed event

The [`Dismissed`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.SfCardView~Dismissed_EV.html) event fires when dismisses the card by swiping with enables `SwipeToDismiss` property. The argument contains the following information.

* [`DismissDirection`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.XForms.Cards.DismissedEventArgs~DismissDirection.html) - Gets a dismissed direction of the card view.

{% tabs %}
{% highlight xaml %}

 <cards:SfCardView Dismissed="SfCardView_Dismissed" SwipeToDismiss="True">
    <Label Text="SfCardView" />
</cards:SfCardView>

{% endhighlight %}

{% highlight c# %}

...
InitializeComponent();
SfCardView cardView = new SfCardView() { SwipeToDismiss = true };
cardView.Dismissed += SfCardView_Dismissed;

...
private void SfCardView_Dismissed(object sender, Syncfusion.XForms.Cards.DismissedEventArgs e)
{
   // handle event action.
}
...

{% endhighlight %}
{% endtabs %}

N> This event will not work when adding the `SfCardView` as a child of `SfCardLayout`.