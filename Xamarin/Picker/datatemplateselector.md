---
layout: post
title: DataTemplateSelector of Syncfusion Xamarin.Forms SfPicker
description: Learn about DataTemplateSelector support in Syncfusion Xamarin Picker (SfPicker) control and more details.
platform: Xamarin
control: Picker
documentation: ug
---


# DataTemplateSelector in Xamarin Picker (SfPicker)

SfPicker supports DataTemplateSelector which you can choose a DataTemplate based on the data object.

{% tabs %}

{% highlight xaml %}

    <ContentPage.Resources>
        <ResourceDictionary>
            <DataTemplate x:Key="DefaultTemplate">
                <Grid >
                    <Label Text="{Binding LanguageName}" FontSize="Medium" HorizontalOptions="Center" VerticalOptions="Center"/>
                </Grid>
            </DataTemplate>
            <DataTemplate x:Key="SepcificTemplate">
                <Grid BackgroundColor="Green">
                    <Label HorizontalOptions="CenterAndExpand" FontSize="Medium"  VerticalOptions="CenterAndExpand" Text="{Binding LanguageName}"/>
                </Grid>
            </DataTemplate>
        </ResourceDictionary>
    </ContentPage.Resources>

    <ContentPage.Content>
        <Grid>
            <syncfusion:SfPicker                  
                             ItemsSource="{Binding LanguageCollection }" >
                <syncfusion:SfPicker.ItemTemplate>            <local:DataTemplateSelectorViewModel DefaultTemplate="{StaticResource DefaultTemplate}" SpecificTemplate="{StaticResource SepcificTemplate}"/>
                </syncfusion:SfPicker.ItemTemplate>   
              </syncfusion:SfPicker>
                </Grid>
            </Grid>
        </Grid>
    </ContentPage.Content>

{% endhighlight %}

{% highlight C# %}

    public partial class MainPage : ContentPage
     {
        SfPicker picker = new SfPicker();
        DataTemplate defaultTemplate;
        DataTemplate specifictempalte;
        public MainPage()
        {
            InitializeComponent();
            this.BindingContext = new ViewModel();
            ViewModel view = new ViewModel();

            defaultTemplate = new DataTemplate(() =>
            {
                Grid grid = new Grid();
                Label label = new Label();
                label.SetBinding(Label.TextProperty, "LanguageName");
                label.HorizontalOptions = LayoutOptions.Center;
                label.VerticalOptions = LayoutOptions.Center;
                label.FontSize = 20;
                grid.Children.Add(label);
                return grid;
            });

            specifictempalte = new DataTemplate(() =>
            {
                Grid maingrid = new Grid();
                Grid labelgrid = new Grid();
                Grid imagegrid = new Grid();
                Label label = new Label();
                Image image = new Image();
                label.SetBinding(Label.TextProperty, "LanguageName");
                label.FontSize = 20;
                label.HorizontalOptions = LayoutOptions.Center;
                label.VerticalOptions = LayoutOptions.Center;
                image.Source = "Crown.png";
                image.HeightRequest = 15;
                image.WidthRequest = 15;
                image.HorizontalOptions = LayoutOptions.Center;
                image.VerticalOptions = LayoutOptions.Center;
                labelgrid.Children.Add(label);
                imagegrid.Children.Add(image);
                imagegrid.Padding = new Thickness(-80, 0, 0, 0);
                maingrid.Children.Add(labelgrid);
                maingrid.Children.Add(imagegrid);
                return maingrid;
            });

            Grid mainGrid = new Grid();
            RowDefinition firstrow = new RowDefinition();
            RowDefinition secondrow = new RowDefinition();

            Button button = new Button();
            button.Clicked += Button_Clicked;
            button.HorizontalOptions = LayoutOptions.Center;
            button.VerticalOptions = LayoutOptions.Center;
            button.Text = "Pick a Language";
            Grid.SetRow(button, 0);

            picker.ShowHeader = true;
            picker.ShowFooter = true;
            picker.HeaderText = "Select a Language";
            picker.PickerMode = PickerMode.Dialog;
            picker.ItemsSource = view.LanguageCollection;
            picker.ItemTemplate = new DataTemplateSelectorViewModel { DefaultTemplate = defaultTemplate, SpecificTemplate = specifictempalte };
            Grid.SetRow(picker, 1);
            

            mainGrid.RowDefinitions.Add(firstrow);
            mainGrid.RowDefinitions.Add(secondrow);
            mainGrid.Children.Add(button);
            mainGrid.Children.Add(picker);
            firstrow.Height = new GridLength(80);
            secondrow.Height = new GridLength(500);

            this.Content = mainGrid;
        }

{% endhighlight %}

{% endtabs %}

### OnSelectTemplate

 The OnSelectTemplate is a overridden method  to return a particular DataTemplate, which shown in the following code:

{% highlight C# %}
	
    public class DataTemplateSelectorViewModel :   DataTemplateSelector

    {
        private DataTemplate defaulttemplate;

        public DataTemplate DefaultTemplate
        {
            get { return defaulttemplate; }
            set { defaulttemplate = value; }
        }

        private DataTemplate specifictemplate;

        public DataTemplate SpecificTemplate
        {
            get { return specifictemplate; }
            set { specifictemplate = value; }
        }

        protected override DataTemplate OnSelectTemplate(object item, BindableObject container)
        {
            var message = item as Model;
            if (message == null)
                return null;
            return message.IsPremium ? SpecificTemplate : DefaultTemplate; 
        }

    }
  
{% endhighlight %}

The following screenshot illustrates the output of above code.

![DataTemplateSelector](images/DataTemplateSelector.png)

We have attached sample for reference. You can download the sample from the following link.

Sample link:[DataTemplateSelectorSample](http://www.syncfusion.com/downloads/support/directtrac/general/ze/DataTemplateSelectorSample1687574118)