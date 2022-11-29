---
layout: post
title: DataTemplateSelector in Xamarin Chips control | Syncfusion
description: Learn about DataTemplateSelector support in Syncfusion Xamarin Chips control, its elements and more.
platform: xamarin
control: Chips
documentation: ug
---

# DataTemplateSelector in Xamarin Chips
You can customize the appearance of each chip with different templates based on specific constraints using the [`DataTemplateSelector`](https://docs.microsoft.com/en-us/dotnet/api/Xamarin.Forms.DataTemplateSelector/).

## Create and initialize business models 

Define a simple model class ChipModel with fields Text, CanSelect, ImageSource, and populate chip model in ViewModel.

{% tabs %}

{% highlight C# %}

    public class ChipViewModel
    {
        public ObservableCollection<ChipModel> Data { get; set; }

        public ChipViewModel()
        {
                Data = new ObservableCollection<ChipModel>()
               {
                new ChipModel(){Text ="Happy", CanSelect = true, ImageSource="Happy.png"},
                new ChipModel(){Text ="Sad", CanSelect = false,ImageSource = "Sad.png"},
                new ChipModel(){Text ="Love", CanSelect = true,ImageSource = "Love.png"},
                new ChipModel(){Text ="Sick", CanSelect = false,ImageSource="Sick.png"},
                new ChipModel(){Text ="Angry", CanSelect = false, ImageSource ="Angry.png"},
                new ChipModel(){Text ="Think", CanSelect = true,ImageSource="Thinking.png"},
                new ChipModel(){Text ="Wink", CanSelect = true,ImageSource="Wink.png"},
                new ChipModel(){Text ="Freeze", CanSelect = false,ImageSource="Freezing.png"},
               };
        }

    }

    public class ChipModel
    {
        public bool CanSelect { get; set; }
        public string Text { get; set; }
        public ImageSource ImageSource { get; set; }
    }

{% endhighlight %}

{% endtabs %}

### Create a data template selector

Create a custom class by inheriting `DataTemplateSelector`, and override the `OnSelectTemplate` method to return the `DataTemplate` for that item. At runtime, the SfChipGroup invokes the `OnSelectTemplate` method for each item and passes the data object as parameter.

{% tabs %}
{% highlight c# %}

public class ChipDataTemplateSelector : DataTemplateSelector
{
        public DataTemplate HappyEmojiTemplate { get; set; }
        public DataTemplate SadEmojiTemplate { get; set; }

        protected override DataTemplate OnSelectTemplate(object item, BindableObject container)
        {
            return (item as ChipModel).CanSelect ? HappyEmojiTemplate : SadEmojiTemplate;
        }
}

{% endhighlight %}
{% endtabs %}

### Applying the data template selector

Assign the already defined `DataTemplateSelector` to the [`ItemTemplate`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_ItemTemplate) of the SfChipGroup in either XAML or C#.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             x:Class="SimpleSample.MainPage"
             xmlns:button="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             xmlns:local="clr-namespace:SimpleSample;assembly=SimpleSample">
             
  <ContentPage.Resources>
        <ResourceDictionary>
            <DataTemplate x:Key="happyTemplate">
                <StackLayout>
                    <button:SfChip HeightRequest="40" WidthRequest="120" Text="{Binding Text}" BackgroundColor="#00bdae" ShowIcon="True" ImageSource="{Binding ImageSource}"  ShowCloseButton="True" ShowSelectionIndicator="False" ImageAlignment="Left" CloseButtonColor="White"/>
            </StackLayout>
            </DataTemplate>
            <DataTemplate x:Key="sadTemplate">
                <StackLayout>
                    <button:SfChip HeightRequest="40" WidthRequest="120" Text="{Binding Text}" BackgroundColor="#e56590" ShowIcon="True" ImageSource="{Binding ImageSource}"  ShowCloseButton="True" ShowSelectionIndicator="False" ImageAlignment="Left" CloseButtonColor="White"/>
                </StackLayout>
            </DataTemplate>
            <local:ChipDataTemplateSelector x:Key="selector" 
                                            HappyEmojiTemplate="{StaticResource happyTemplate}" 
                                            SadEmojiTemplate="{StaticResource sadTemplate}"/>
        </ResourceDictionary>
    </ContentPage.Resources>

    <ContentPage.BindingContext>
        <local:ChipViewModel/>
    </ContentPage.BindingContext>

	<button:SfChipGroup x:Name="chipgroup" ChipBackgroundColor="Transparent"                                    
                                         ItemsSource="{Binding Data}" ItemTemplate="{StaticResource selector}">
        ...
    </button:SfChipGroup>
      
</ContentPage>
{% endhighlight %}
{% highlight c# %}

SfChipGroup chipGroup = new SfChipGroup();
chipGroup.ItemsSource = chipViewModel.Data;
chipGroup.ItemTemplate = this.Resources["selector"] as DataTemplate;
this.Content = chipGroup;
      
{% endhighlight %}
{% endtabs %}

![DataTemplateSelector support for SfChipGroup in Xamarin.Forms](images\customization-images/xamarin-forms-datatemplateselector.png)

