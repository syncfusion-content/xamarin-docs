---
layout: post
title: DataTemplateSelector in Xamarin ComboBox control | Syncfusion
description: Learn here all about DataTemplateSelector support in Syncfusion Xamarin ComboBox (SfComboBox) control and more.
platform: Xamarin
control: SfComboBox
documentation: ug
---

# DataTemplateSelector in Xamarin ComboBox (SfComboBox)

[`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) supports DataTemplateSelector, which is used to choose a DataTemplate based on data object.
 

{% tabs %}

{% highlight xaml %}

    <ContentPage.BindingContext>
        <local:MobileDetailViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Resources>
        <ResourceDictionary>
            <DataTemplate x:Key="default">
                <ViewCell>
                    <Grid Padding="5">
                        <Label Text="{Binding Mobile}" TextColor="Green"/>
                    </Grid>
                </ViewCell>
            </DataTemplate>
            <DataTemplate x:Key="specific">
                <ViewCell>
                    <Grid  Padding="5">
                        <Label Text="{Binding Mobile}" BackgroundColor="LightGray" TextColor="Red"/>
                    </Grid>
                </ViewCell>
            </DataTemplate>
        </ResourceDictionary>
    </ContentPage.Resources>
    <StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <comboBox:SfComboBox DataSource="{Binding MobileCollection}" DisplayMemberPath="Mobile">
            <comboBox:SfComboBox.ItemTemplate>
                <local:DataTemplateSelectorViewModel DefaultTemplate="{StaticResource default}" SpecificDataTemplate="{StaticResource specific}" />
            </comboBox:SfComboBox.ItemTemplate>
        </comboBox:SfComboBox>
    </StackLayout>
	
{% endhighlight %}

{% highlight c# %}

    public partial class MainPage : ContentPage
    {
        DataTemplate defaultTemplate;
        DataTemplate specifictempalte;
        public MainPage()
        {
            InitializeComponent();
            MobileDetailViewModel mobileDetailViewModel = new MobileDetailViewModel();
            defaultTemplate = new DataTemplate(() =>
            {
                Grid grid = new Grid();
                grid.Padding = new Thickness(5);
                Label label = new Label();
                label.SetBinding(Label.TextProperty, "Mobile");
                label.TextColor = Color.Green;
                grid.Children.Add(label);
                return new ViewCell { View = grid };
            });

            specifictempalte = new DataTemplate(() =>
            {
                Grid grid = new Grid();
                grid.Padding = new Thickness(5);
                Label label = new Label();
                label.SetBinding(Label.TextProperty, "Mobile");
                label.BackgroundColor = Color.LightGray;
                label.TextColor = Color.Red;
                grid.Children.Add(label);
                return new ViewCell { View = grid };
            });
            StackLayout layout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = new Thickness(30)
            };
            SfComboBox comboBox = new SfComboBox();
            comboBox.HeightRequest = 40;
            comboBox.DataSource = mobileDetailViewModel.MobileCollection;
            this.BindingContext = mobileDetailViewModel;
            comboBox.DisplayMemberPath = "Mobile";
            comboBox.ItemTemplate = new DataTemplateSelectorViewModel { DefaultTemplate = defaultTemplate, SpecificDataTemplate = specifictempalte };
            layout.Children.Add(comboBox);
            Content = layout;
        }
    }

{% endhighlight %}

{% endtabs %}

## Create and Initialize Business Models 

Define a simple model class MobileDetail with fields IsAvailableInStock, Mobile and populate mobile detail in ViewModel.

{% tabs %}

{% highlight C# %}

    public class MobileDetailViewModel
    {
        public ObservableCollection<MobileDetail> MobileCollection { get; set; }
        public MobileDetailViewModel()
        {
            this.MobileCollection = new ObservableCollection<MobileDetail>()
            {
                new MobileDetail () { Mobile="Samasung S8", IsAvailableInStock=false },
                new MobileDetail () { Mobile="Samasung S9", IsAvailableInStock=true },
                new MobileDetail () { Mobile="Samsung S10", IsAvailableInStock=true },
                new MobileDetail () { Mobile="Samsung S10 plus", IsAvailableInStock=true },
                new MobileDetail () { Mobile="iPhone 7", IsAvailableInStock=true },
                new MobileDetail () { Mobile="iPhone 8", IsAvailableInStock=true },
                new MobileDetail () { Mobile="iPhone X", IsAvailableInStock=false },
                new MobileDetail () { Mobile="iPhone XR", IsAvailableInStock=false },
                new MobileDetail () { Mobile="iPhone XS", IsAvailableInStock=true },
            };
        }
    }

    public class MobileDetail
    {
        public string Mobile { get; set; }

        public bool IsAvailableInStock { get; set; }
    }

{% endhighlight %}

{% endtabs %}


## OnSelectTemplate

The OnSelectTemplate is an overridden method to return a particular DataTemplate. The following code sample demonstrates how to use the OnSelectTemplate method.


{% tabs %}

{% highlight C# %}

    public class DataTemplateSelectorViewModel : DataTemplateSelector
    {
        public DataTemplate DefaultTemplate { get; set; }
        public DataTemplate SpecificDataTemplate { get; set; }

        protected override DataTemplate OnSelectTemplate(object item, BindableObject container)
        {
            var message = item as MobileDetail;
            if (message.IsAvailableInStock == null)
                return null;
            return message.IsAvailableInStock == false ? SpecificDataTemplate : DefaultTemplate;
        }

    }

{% endhighlight %}

{% endtabs %}

The following screenshot illustrates the output of above code.

![Data template selector](images/Data-Template-Selector/DataTemplateSelector.png)


We have attached sample for reference. You can download the sample from the following link.

Sample Link: [SfComboBox_DataTemplateSelector](https://github.com/SyncfusionExamples/datatemplate-selector-sfcombobox)



