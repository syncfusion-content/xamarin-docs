---
layout: post
title: Bindable Layout in Xamarin StepProgressBar control | Syncfusion
description: Learn here all about Bindable Layout support in Syncfusion Xamarin StepProgressBar (Step Progress Bar) control and more.
platform: xamarin
control: StepProgressBar
documentation: ug
---

From version 3.5, Xamarin.Forms has introduced a new approach called BindableLayout that works with all the layouts derived from Layout&lt;T&gt;. By simply setting ItemTemplate and ItemsSource, BindableLayout will create a group of UI (for the given ItemTemplate) for every data in the ItemsSource and add them as children.

# Bindable Layout in Xamarin StepProgressBar (Step Progress Bar)

The [SfStepProgressBar](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.SfStepProgressBar.html) allows to set a collection of items by setting `BindableLayout.ItemsSource` and `BindableLayout.ItemTemplate` properties. The StepProgressBar supports Bindable Layout in Xamarin.Forms version 3.5 and above.

## Initialize view model

{% highlight c# %}

    public class ShipmentDetails 
    {
        public string Title { get; set; }
        public string Description { get; set; }
        public string Date { get; set; }
        public string Time { get; set; }
        public StepStatus Status { get; set; }
        public int ProgressValue { get; set; }
    }

{% endhighlight %} 

Next, create a view model class and initialize a model object as demonstrated in the following code sample.

{% highlight c# %}

    public class ShipmentViewModel : INotifyPropertyChanged
    {
        public ObservableCollection<ShipmentDetails> ShipmentInfoCollection { get; set; }

        public ShipmentViewModel()
        {
            ShipmentInfoCollection = new ObservableCollection<ShipmentDetails>();
            ShipmentInfoCollection.Add(CreateShipmentInfo("Ordered and Approved", "Seller has processed your order", DateTime.Now.ToString("dd MMM yyyy"), "10:10 AM", StepStatus.Completed, 100));
            ShipmentInfoCollection.Add(CreateShipmentInfo("Packed", "Your item has been picked by courier partner", DateTime.Now.AddDays(1).ToString("dd MMM yyyy"), "01:37 PM", StepStatus.Completed, 100));
            ShipmentInfoCollection.Add(CreateShipmentInfo("Shipped", "", DateTime.Now.AddDays(1).ToString("dd MMM yyyy"), "02:50 PM", StepStatus.InProgress, 50));
            ShipmentInfoCollection.Add(CreateShipmentInfo("Delivered", "", DateTime.Now.AddDays(2).ToString("dd MMM yyyy"), "10:00 AM", StepStatus.NotStarted, 0));
        }

        public ShipmentDetails CreateShipmentInfo(string title, string description, string date, string time, StepStatus status, int progress)
        {
            ShipmentDetails shipment = new ShipmentDetails()
            {
                Title = title,
                Description = description,
                Date = date,
                Time = time,
                Status = status,
                ProgressValue = progress
            };

            return shipment;
        }

        public event PropertyChangedEventHandler PropertyChanged;
    }

{% endhighlight %} 


N> Add namespace of ViewModel class in your XAML page if you prefer to set BindingContext in XAML. 

{% tabs %} 

{% highlight xaml %}

    <ContentPage.BindingContext>
        <local:ShipmentViewModel/>
    </ContentPage.BindingContext>

{% endhighlight %}

{% highlight c# %}

this.BindingContext = new ShipmentViewModel();

{% endhighlight %}

{% endtabs %}

## Populate StepProgressBar with data

{% tabs %} 

{% highlight xaml %}

<progressBar:SfStepProgressBar x:Name="stepProgress" BindableLayout.ItemsSource="{Binding ShipmentInfoCollection}" >
…
</progressBar:SfStepProgressBar>

{% endhighlight %}

{% highlight c# %}

SfStepProgressBar sfStepProgressBar = new SfStepProgressBar();
BindableLayout.SetItemsSource(sfStepProgressBar, ShipmentViewModel.ShipmentInfoCollection);

{% endhighlight %}

{% endtabs %}

## Define the appearance of StepView

{% tabs %} 

{% highlight xaml %}

               <progressBar:SfStepProgressBar BindableLayout.ItemsSource="{Binding ShipmentInfoCollection}" TitleAlignment="Start" BackgroundColor="Transparent" TitleSpace="10" Orientation="Vertical" x:Name="stepProgress">
                    <BindableLayout.ItemTemplate>
                        <DataTemplate>
                            <progressBar:StepView x:Name="stepView" ProgressValue="{Binding ProgressValue}" Status="{Binding Status}">
                                <progressBar:StepView.PrimaryFormattedText>
                                    <FormattedString>
                                        <Span Text="{Binding Title}" FontSize="Medium" FontAttributes="Bold"/>
                                        <Span Text="&#10;&#10;"/>
                                        <Span Text="{Binding Description}" FontSize="Small"/>
                                    </FormattedString>
                                </progressBar:StepView.PrimaryFormattedText>
                                <progressBar:StepView.SecondaryFormattedText>
                                    <FormattedString>
                                        <Span Text="{Binding Date}" FontSize="Small" FontAttributes="Bold"/>
                                        <Span Text="&#10;&#10;"/>
                                        <Span Text="        "/>
                                        <Span Text="{Binding Time}" FontSize="Small" TextColor="#b6b0b2"/>
                                    </FormattedString>
                                </progressBar:StepView.SecondaryFormattedText>
                            </progressBar:StepView>
                        </DataTemplate>
                    </BindableLayout.ItemTemplate>
                </progressBar:SfStepProgressBar>

{% endhighlight %}

{% highlight c# %}

ShipmentViewModel ShipmentViewModel = new ShipmentViewModel();
this.BindingContext = ShipmentViewModel;
SfStepProgressBar sfStepProgressBar = new SfStepProgressBar();
sfStepProgressBar.TitleAlignment = StepTitleAlignment.Start;
sfStepProgressBar.BackgroundColor = Color.Transparent;
sfStepProgressBar.TitleSpace = 20;
sfStepProgressBar.Orientation = StepOrientation.Vertical;

var dataTemplate = new DataTemplate(() =>
{
    StepView stepView = new StepView();
    stepView.SetBinding(StepView.ProgressValueProperty, "ProgressValue");
    stepView.SetBinding(StepView.StatusProperty, "Status");
    stepView.PrimaryFormattedText = new FormattedString();
    Span span = new Span();
    span.SetBinding(Span.TextProperty, "Title");
    span.FontSize = Device.GetNamedSize(NamedSize.Medium, typeof(Span));
    span.FontAttributes = FontAttributes.Bold;              
    Span span1 = new Span();
    span1.Text = "\n \n";
    Span span2 = new Span();
    span2.SetBinding(Span.TextProperty, "Description");
    span2.FontSize = Device.GetNamedSize(NamedSize.Small, typeof(Span));
    stepView.PrimaryFormattedText.Spans.Add(span);
    stepView.PrimaryFormattedText.Spans.Add(span1);
    stepView.PrimaryFormattedText.Spans.Add(span2);
    stepView.SecondaryFormattedText = new FormattedString();
    Span span3 = new Span();
    span3.SetBinding(Span.TextProperty, "Date");
    span3.FontSize = Device.GetNamedSize(NamedSize.Small, typeof(Span));
    span3.FontAttributes = FontAttributes.Bold;
    Span span4 = new Span();
    span4.Text = "\n \n";
    Span span5 = new Span();
    span5.Text = "        ";
    Span span6 = new Span();
    span6.SetBinding(Span.TextProperty, "Time");
    span6.FontSize = Device.GetNamedSize(NamedSize.Small, typeof(Span));
    span6.TextColor = Color.FromHex("#b6b0b2");
    stepView.SecondaryFormattedText.Spans.Add(span3);
    stepView.SecondaryFormattedText.Spans.Add(span4);
    stepView.SecondaryFormattedText.Spans.Add(span5);
    stepView.SecondaryFormattedText.Spans.Add(span6);
    return stepView;
});

BindableLayout.SetItemTemplate(sfStepProgressBar, dataTemplate);
BindableLayout.SetItemsSource(sfStepProgressBar, ShipmentViewModel.ShipmentInfoCollection);

Content = sfStepProgressBar;

{% endhighlight %}

{% endtabs %}

![Xamarin Forms StepProgressBar with Bimdable Layout](overview_images/bindable_layout.png)

You can download the entire source of this demo from here [Xaml](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Shipment_Tracking-237228452.zip) and [CS](https://www.syncfusion.com/downloads/support/directtrac/general/ze/ProgressBar-414864132)
