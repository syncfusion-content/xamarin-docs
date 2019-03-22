---
layout : post
title : Customizations in ComboBox
description : This section describes about the visual customization of entry, suggestion box and suggestion items in the ComboBox
platform : Xamarin
control : SfComboBox
documentation : ug
---

# Customizing ComboBox

The combo box control  provides user friendly customizing options for both entry part and drop-down part. In this section, customizing the entire ComboBox control is explained.

## Customizing the entry

The [`TextColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~TextColor.html), [`TextSize`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~TextSize.html), [`FontAttributes`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~FontAttributes.html), [`FontFamily`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~FontFamily.html) and [`BorderColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~BorderColor.html) properties are used to customize the foreground color, font size, font attribute, font family and border color of the entry part.

## Text color

The combo box control provides the user to customize the foreground color of the text inside the entry part.

## Text size

The combo box control provides the user to customize the text size of the text inside the entry part using [`TextSize`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~TextSize.html) property.

## Font attributes

The combo box control provides the user to customize the font attribute of the text inside the entry part using [`FontAttributes`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~FontAttributes.html) property.

## Font family

The combo box control provides the user to customize the font family of the text inside the entry part using [`FontFamily`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~FontFamily.html) property.

## Border color

The combo box control provides the user to customize the border color of the entry box using [`BorderColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~BorderColor.html) property.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="45" x:Name="comboBox" Text="Sample text" FontAttributes="Bold" TextColor="#1976d2" TextSize="20" BorderColor="#1976d2"/>
</StackLayout>

{% endhighlight %}

{% highlight c# %}

StackLayout stackLayout = new StackLayout() 
{ 
	VerticalOptions = LayoutOptions.Start, 
	HorizontalOptions = LayoutOptions.Start,
	Padding = new Thickness(30) 
};

SfComboBox comboBox = new SfComboBox() 
{ 
	HeightRequest = 45,  
	Text = "Sample text", 
	TextColor = Color.FromHex("1976d2"), 
	TextSize = 20, 
	BorderColor = Color.FromHex("1976d2")
	FontAttributes = FontAttributes.Bold
};

stackLayout.Children.Add(comboBox);
this.Content = stackLayout;

{% endhighlight %}

{% endtabs %}

![Customizing entry](images/Customizing-ComboBox/customizing-entry.png)

### Changing delete button color

The [`ClearButtonColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~ClearButtonColor.html) property is used to modify the delete button color. The following code example shows changing delete button color. 

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="True" ClearButtonColor="Red">
            <combobox:SfComboBox.ComboBoxSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Uganda</x:String>
                    <x:String>Ukraine</x:String>
                    <x:String>United Arab Emirates</x:String>
                    <x:String>United Kingdom</x:String>
                </ListCollection:List>
            </combobox:SfComboBox.ComboBoxSource>
        </combobox:SfComboBox>
 </StackLayout>

{% endhighlight %}

{% highlight c# %}

    StackLayout layout = new StackLayout() 
    { 
	     VerticalOptions = LayoutOptions.Start, 
	     HorizontalOptions = LayoutOptions.Start, 
	     Padding = new Thickness(30) 
    }; 

    List<String> countryNames = new List<String>();
    countryNames.Add("Uganda");
    countryNames.Add("Ukraine");
    countryNames.Add("United Arab Emirates");
    countryNames.Add("United Kingdom");
    countryNames.Add("United States");

    SfComboBox comboBox = new SfComboBox();
    comboBox.DataSource = countryNames;
    comboBox.ClearButtonColor = Color.Yellow;
    comboBox.IsEditableMode = true;

    layout.Children.Add(comboBox); 
    Content = layout;

{% endhighlight %}

{% endtabs %}

![Delete button color](images/Customizing-ComboBox/delete-button-color.png)

### Changing delete button visibility

The [`ShowClearButton`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~ShowClearButton.html) property is used to modify the visibility of delete button. The following code example shows changing delete button visibility.
{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="True" IsEditableMode="True" ShowClearButton="False">
            <combobox:SfComboBox.ComboBoxSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Uganda</x:String>
                    <x:String>Ukraine</x:String>
                    <x:String>United Arab Emirates</x:String>
                    <x:String>United Kingdom</x:String>
                </ListCollection:List>
            </combobox:SfComboBox.ComboBoxSource>
        </combobox:SfComboBox>
 </StackLayout>

{% endhighlight %}

{% highlight c# %}

    StackLayout layout = new StackLayout() 
    { 
	     VerticalOptions = LayoutOptions.Start, 
	     HorizontalOptions = LayoutOptions.Start, 
	     Padding = new Thickness(30) 
    }; 

    List<String> countryNames = new List<String>();
    countryNames.Add("Uganda");
    countryNames.Add("Ukraine");
    countryNames.Add("United Arab Emirates");
    countryNames.Add("United Kingdom");
    countryNames.Add("United States");

    SfComboBox comboBox = new SfComboBox();
    comboBox.DataSource = countryNames;
    comboBox.ShowClearButton = false;
    comboBox.IsEditableMode = true;

    layout.Children.Add(comboBox); 
    Content = layout;

{% endhighlight %}

{% endtabs %}

![Delete button visibility](images/Customizing-ComboBox/delete-button-visibility.png)

### Changing border visibility

The [`ShowBorder`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~ShowBorder.html) property is used to modify the visibility of border. The following code example shows changing border visibility. 

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="True" IsEditableMode="True" ShowBorder="False">
            <combobox:SfComboBox.ComboBoxSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Uganda</x:String>
                    <x:String>Ukraine</x:String>
                    <x:String>United Arab Emirates</x:String>
                    <x:String>United Kingdom</x:String>
                </ListCollection:List>
            </combobox:SfComboBox.ComboBoxSource>
        </combobox:SfComboBox>
 </StackLayout>

{% endhighlight %}

{% highlight c# %}

   StackLayout layout = new StackLayout() 
    { 
	     VerticalOptions = LayoutOptions.Start, 
	     HorizontalOptions = LayoutOptions.Start, 
	     Padding = new Thickness(30) 
    }; 

    List<String> countryNames = new List<String>();
    countryNames.Add("Uganda");
    countryNames.Add("Ukraine");
    countryNames.Add("United Arab Emirates");
    countryNames.Add("United Kingdom");
    countryNames.Add("United States");

    SfComboBox comboBox = new SfComboBox();
    comboBox.DataSource = countryNames;
    comboBox.ShowBorder = false;
    comboBox.IsEditableMode = true;

    layout.Children.Add(comboBox); 
    Content = layout;

{% endhighlight %}

{% endtabs %}

![Border visibility](images/Customizing-ComboBox/show-border.png)

## CustomView for ComboBox

CustomView property has used to provide the custom view instead of entry in ComboBox. It's default height and width has control height and width.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox">
		<combobox:SfComboBox.CustomView>
			<Label x:Name="customLabel" HeightRequest="40" Text="ComboBox"  VerticalTextAlignment="Center"/>
		</combobox:SfComboBox.CustomView>
	</combobox:SfComboBox>
</StackLayout>

{% endhighlight %}

{% highlight c# %}

StackLayout layout = new StackLayout() 
{ 
	VerticalOptions = LayoutOptions.Start, 
	HorizontalOptions = LayoutOptions.Start, 
	Padding = new Thickness(30) 
};	

Label customLabel = new Label();
customLabel.HeightRequest = 40;
customLabel.VerticalTextAlignment = TextAlignment.Center;
customLabel.Text = "ComboBox";

SfComboBox comboBox = new SfComboBox();
comboBox.HeightRequest = 40;
comboBox.DataSource = countryNames;
comboBox.SuggestionBoxPlacement = SuggestionBoxPlacement.Top;
comboBox.CustomView = customLabel; 

layout.Children.Add(comboBox); 
Content = layout;

{% endhighlight %}

{% endtabs %}

![CustomView for ComboBox](images/Customizing-ComboBox/customview.png)

## Custom template for suggestion items

The `ItemTemplate` property helps to decorate suggestion items with custom templates. The following code explains the steps to add an image to the suggestion list item.

{% tabs %}

{% highlight c# %}
public class Person
{
	private int age;
	public int Age
	{
		get { return age; }
		set { age = value; }
	}

	private string name;
	public string Name
	{
		get { return name; }
		set { name = value; }
	}
}

public class PersonViewModel
{
	private ObservableCollection<Person> personCollection;
	public ObservableCollection<Person> PersonCollection
	{
		get { return personCollection; }
		set { personCollection = value; }
	}

	public PersonViewModel()
	{
		personCollection = new ObservableCollection<Person>();
		personCollection.Add(new Person() { Age = 21, Name = "Aldan" });
		personCollection.Add(new Person() { Age = 25, Name = "Clara" });
		personCollection.Add(new Person() { Age = 23, Name = "Aldrin" });            
		personCollection.Add(new Person() { Age = 25, Name = "Mark" });
		personCollection.Add(new Person() { Age = 25, Name = "Lucas" });
		personCollection.Add(new Person() { Age = 24, Name = "Alan" });
		personCollection.Add(new Person() { Age = 25, Name = "James" });
		personCollection.Add(new Person() { Age = 22, Name = "Aaron" });
	}
}
{% endhighlight %}

{% endtabs %}

Now populate this PersonViewModel data in SfComboBox control by binding with [`DataSource`] property. 

{% tabs %}
{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:combobox="clr-namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             xmlns:local="clr-namespace:NamespaceName"            
             x:Class="NamespaceName.ClassName">
	<ContentPage.BindingContext>
    	    <local:PersonViewModel/>
 	</ContentPage.BindingContext>
     
	<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
		<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" DisplayMemberPath="Name" DataSource="{Binding PersonCollection}">
			<combobox:SfComboBox.ItemTemplate>
				<DataTemplate>
					<StackLayout Orientation="Horizontal">
						<Image Source="User.png" WidthRequest="12"/>
						<Label Text="{Binding Name}" />
					</StackLayout>
				</DataTemplate>
			</combobox:SfComboBox.ItemTemplate>
		</combobox:SfComboBox>
	</StackLayout> 
</ContentPage>

{% endhighlight %}

{% highlight c# %}

DataTemplate itemTemplate = new DataTemplate(() =>
{
	StackLayout stack;
	Image image;
	Label label;
	stack = new StackLayout();
	stack.Orientation = StackOrientation.Horizontal;
	image = new Image();
	image.Source = (FileImageSource)ImageSource.FromFile("User.png");
	label = new Label();
	label.SetBinding(Label.TextProperty, "Name");
	stack.Children.Add(image);
	stack.Children.Add(label);
	return new ViewCell { View = stack };
});

StackLayout layout = new StackLayout() 
{ 
	VerticalOptions = LayoutOptions.Start, 
	HorizontalOptions = LayoutOptions.Start, 
	Padding = new Thickness(30) 
}; 

SfComboBox comboBox = new ComboBox();
comboBox.HeightRequest = 40;
comboBox.BindingContext = new PersonViewModel();
Binding binding = new Binding("PersonCollection");
binding.Source = this;
binding.Mode = BindingMode.TwoWay;
comboBox.SetBinding(Label.DataSourceProperty,binding);
comboBox.ItemTemplate = itemTemplate;

layout.Children.Add(comboBox); 
Content = layout;

{% endhighlight %}

{% endtabs %}

![Item template for ComboBox](images/Customizing-ComboBox/item-template.png)

## Customizing the suggestion box

### Changing suggestion item height

The [`DropDownItemHeight`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~DropDownItemHeight.html) property is used to modify the height of suggestion items in drop-down list. The following code example shows changing suggestion item height.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
    <combobox:SfComboBox HeightRequest="40" x:Name="comboBox" DropDownItemHeight="50">
        <combobox:SfComboBox.ComboBoxSource>
            <ListCollection:List x:TypeArguments="x:String">
                <x:String> Uganda </x:String>
                <x:String> Ukraine </x:String>
                <x:String> United Arab Emirates </x:String>
                <x:String> United Kingdom </x:String>
            </ListCollection:List>
        </combobox:SfComboBox.ComboBoxSource>
    </combobox:SfComboBox>                
</StackLayout>

{% endhighlight %}

{% highlight c# %}

    StackLayout layout = new StackLayout() 
    { 
	     VerticalOptions = LayoutOptions.Start, 
	     HorizontalOptions = LayoutOptions.Start, 
	     Padding = new Thickness(30) 
    }; 

    List<String> countryNames = new List<String>();
    countryNames.Add("Uganda");
    countryNames.Add("Ukraine");
    countryNames.Add("United Arab Emirates");
    countryNames.Add("United Kingdom");

    SfComboBox comboBox = new SfComboBox();
    comboBox.DataSource = countryNames;
    comboBox.DropDownItemHeight = 50;

    layout.Children.Add(comboBox); 
    Content = layout;

{% endhighlight %}

{% endtabs %}

![Dropdown item height](images/Customizing-ComboBox/dropdown-item-height.png)

### Changing suggestion box width

The [`DropDownWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~DropDownWidth.html) property is used to modify the width of suggestion box. The following code example shows changing suggestion box width.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <combobox:SfComboBox HeightRequest="40" x:Name="comboBox" DropDownWidth="300">
            <combobox:SfComboBox.ComboBoxSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Uganda</x:String>
                    <x:String>Ukraine</x:String>
                    <x:String>United Arab Emirates</x:String>
                    <x:String>United Kingdom</x:String>
                </ListCollection:List>
            </combobox:SfComboBox.ComboBoxSource>
        </combobox:SfComboBox>
 </StackLayout>

{% endhighlight %}

{% highlight c# %}

    StackLayout layout = new StackLayout() 
    { 
	     VerticalOptions = LayoutOptions.Start, 
	     HorizontalOptions = LayoutOptions.Start, 
	     Padding = new Thickness(30) 
    }; 

    List<String> countryNames = new List<String>();
    countryNames.Add("Uganda");
    countryNames.Add("Ukraine");
    countryNames.Add("United Arab Emirates");
    countryNames.Add("United Kingdom");
    countryNames.Add("United States");

    SfComboBox comboBox = new SfComboBox();
    comboBox.DataSource = countryNames;
    comboBox.DropDownWidth = 300;

    layout.Children.Add(comboBox); 
    Content = layout;

{% endhighlight %}

{% endtabs %}

![Dropdown width](images/Customizing-ComboBox/dropdown-width.png)

### Changing suggestion box corner radius

The [`DropDownCornerRadius`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~DropDownCornerRadius.html) property is used to modify the corner radius of suggestion box. The following code example shows changing suggestion box corner radius. 

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <combobox:SfComboBox HeightRequest="40" x:Name="comboBox" DropDownCornerRadius="3">
            <combobox:SfComboBox.ComboBoxSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Uganda</x:String>
                    <x:String>Ukraine</x:String>
                    <x:String>United Arab Emirates</x:String>
                    <x:String>United Kingdom</x:String>
                </ListCollection:List>
            </combobox:SfComboBox.ComboBoxSource>
        </combobox:SfComboBox>
 </StackLayout>

{% endhighlight %}

{% highlight c# %}

    StackLayout layout = new StackLayout() 
    { 
        VerticalOptions = LayoutOptions.Start, 
        HorizontalOptions = LayoutOptions.Start, 
        Padding = new Thickness(30) 
    }; 

    List<String> countryNames = new List<String>();
    countryNames.Add("Uganda");
    countryNames.Add("Ukraine");
    countryNames.Add("United Arab Emirates");
    countryNames.Add("United Kingdom");
    countryNames.Add("United States");

    SfComboBox comboBox = new SfComboBox();
    comboBox.DataSource = countryNames;
    comboBox.DropDownCornerRadius = 3;

    layout.Children.Add(comboBox); 
    Content = layout;

{% endhighlight %}

{% endtabs %}

![Dropdown corner radius](images/Customizing-ComboBox/dropdown-corner-radius.png)

### Changing suggestion box background color

The [`DropDownBackgroundColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~DropDownBackgroundColor.html) property is used to modify the background color of suggestion box. The following code example shows changing suggestion box background color. 

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <combobox:SfComboBox HeightRequest="40" x:Name="comboBox" DropDownBackgroundColor="Yellow">
            <combobox:SfComboBox.ComboBoxSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Uganda</x:String>
                    <x:String>Ukraine</x:String>
                    <x:String>United Arab Emirates</x:String>
                    <x:String>United Kingdom</x:String>
                </ListCollection:List>
            </combobox:SfComboBox.ComboBoxSource>
        </combobox:SfComboBox>
 </StackLayout>

{% endhighlight %}

{% highlight c# %}

    StackLayout layout = new StackLayout() 
    { 
	     VerticalOptions = LayoutOptions.Start, 
	     HorizontalOptions = LayoutOptions.Start, 
	     Padding = new Thickness(30) 
    }; 

    List<String> countryNames = new List<String>();
    countryNames.Add("Uganda");
    countryNames.Add("Ukraine");
    countryNames.Add("United Arab Emirates");
    countryNames.Add("United Kingdom");
    countryNames.Add("United States");

    SfComboBox comboBox = new SfComboBox();
    comboBox.DataSource = countryNames;
    comboBox.DropDownBackgroundColor = Color.Yellow;

    layout.Children.Add(comboBox); 
    Content = layout;

{% endhighlight %}

{% endtabs %}

![Dropdown background color](images/Customizing-ComboBox/dropdown-background-color.png)

### Customizing suggestion items

Suggestion box items can be customized using the [`DropDownItemFontAttributes`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~DropDownItemFontAttributes.html), [`DropDownItemFontFamily`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~DropDownItemFontFamily.html), [`DropDownTextSize`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~DropDownTextSize.html) and [`DropDownTextColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~DropDownTextColor.html) properties.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
    <combobox:SfComboBox HeightRequest="40" x:Name="comboBox" DropDownTextSize="16" DropDownTextColor="#1976d2">
            <combobox:SfComboBox.ComboBoxSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String> Uganda </x:String>
                    <x:String> Ukraine </x:String>
                    <x:String> United Arab Emirates </x:String>
                    <x:String> United Kingdom </x:String>
                    <x:String> United States </x:String>
                </ListCollection:List>
            </combobox:SfComboBox.ComboBoxSource>
    </combobox:SfComboBox>                
</StackLayout>

{% endhighlight %}

{% highlight c# %}

    StackLayout layout = new StackLayout() 
    { 
        VerticalOptions = LayoutOptions.Start, 
        HorizontalOptions = LayoutOptions.Start, 
        Padding = new Thickness(30) 
    }; 

    List<String> countryNames = new List<String>();
    countryNames.Add("Uganda");
    countryNames.Add("Ukraine");
    countryNames.Add("United Arab Emirates");
    countryNames.Add("United Kingdom");
    countryNames.Add("United States");

    SfComboBox comboBox = new SfComboBox();
    comboBox.DataSource = countryNames;
    comboBox.DropDownTextColor = Color.FromHex("#1976d2");
    comboBox.DropDownTextSize = 16;

    layout.Children.Add(comboBox); 
    Content = layout;

{% endhighlight %}

{% endtabs %}

![Customizing dropdown](images/Customizing-ComboBox/customizing-dropdown.png)

### Changing selected item color in suggestion box 

The [`SelectedDropDownItemColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~SelectedDropDownItemColor.html) property is used to modify text color of selected item in drop down. The following code example shows changing the selected item text color in drop down.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <combobox:SfComboBox HeightRequest="40" x:Name="comboBox" SelectedDropDownItemColor="Blue">
            <combobox:SfComboBox.ComboBoxSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Uganda</x:String>
                    <x:String>Ukraine</x:String>
                    <x:String>United Arab Emirates</x:String>
                    <x:String>United Kingdom</x:String>
                </ListCollection:List>
            </combobox:SfComboBox.ComboBoxSource>
        </combobox:SfComboBox>
 </StackLayout>

{% endhighlight %}

{% highlight c# %}

    StackLayout layout = new StackLayout() 
    { 
	     VerticalOptions = LayoutOptions.Start, 
	     HorizontalOptions = LayoutOptions.Start, 
	     Padding = new Thickness(30) 
    }; 

    List<String> countryNames = new List<String>();
    countryNames.Add("Uganda");
    countryNames.Add("Ukraine");
    countryNames.Add("United Arab Emirates");
    countryNames.Add("United Kingdom");
    countryNames.Add("United States");

    SfComboBox comboBox = new SfComboBox();
    comboBox.DataSource = countryNames;
    comboBox.SelectedDropDownItemColor = Color.Blue;

    layout.Children.Add(comboBox); 
    Content = layout;

{% endhighlight %}

{% endtabs %}

![Selected dropdown item color](images/Customizing-ComboBox/selected-dropdown-item-color.png)

## DropDown button customization

This section explains various DropDown button settings available in SfComboBox control.
{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
    <combobox:SfComboBox HeightRequest="40" x:Name="comboBox">
        <combobox:SfComboBox.ComboBoxSource>
            <ListCollection:List x:TypeArguments="x:String">
                <x:String> Uganda </x:String>
                <x:String> Ukraine </x:String>
                <x:String> United Arab Emirates </x:String>
                <x:String> United Kingdom </x:String>
                <x:String> United States </x:String>
            </ListCollection:List>
        </combobox:SfComboBox.ComboBoxSource>
        <combobox:SfComboBox.DropDownButtonSettings>
     		<combobox:DropDownButtonSettings Width="40" Height="40" FontIcon="" FontSize="16" FontColor="Blue" HighlightedBackgroundColor="Green" BackgroundColor="Red" HighlightFontColor="Red"/>
     	</combobox:SfComboBox.DropDownButtonSettings>
    </combobox:SfComboBox>
</StackLayout>

{% endhighlight %}

{% highlight c# %}

    StackLayout layout = new StackLayout() 
    { 
	     VerticalOptions = LayoutOptions.Start, 
	     HorizontalOptions = LayoutOptions.Start, 
	     Padding = new Thickness(30) 
    }; 

    List<String> countryNames = new List<String>();
    countryNames.Add("Uganda");
    countryNames.Add("Ukraine");
    countryNames.Add("United Arab Emirates");
    countryNames.Add("United Kingdom");
    countryNames.Add("United States");

    SfComboBox comboBox = new SfComboBox();
    comboBox.DataSource = countryNames;
    DropDownButtonSettings dropDownButtonSettings = new DropDownButtonSettings();
    dropDownButtonSettings.Height = 40;
    dropDownButtonSettings.Width = 40;
    dropDownButtonSettings.FontIcon = "";
    dropDownButtonSettings.FontSize = 16;
    dropDownButtonSettings.FontColor = Color.Blue;
    dropDownButtonSettings.HighlightedBackgroundColor = Color.Green;
    dropDownButtonSettings.BackgroundColor = Color.Red;
    dropDownButtonSettings.HighlightFontColor = Color.Red;

    comboBox.DropDownButtonSettings = dropDownButtonSettings;

    layout.Children.Add(comboBox); 
    Content = layout;

{% endhighlight %}

{% endtabs %}

![Customizing dropdown](images/Customizing-ComboBox/customizing-dropdown.png)

## Watermark

Watermark provides a short note about the type of input to enter in the editor control. Watermarks are visible only if the text is empty. It will reappear if the text is cleared. The following example, explains the usability of watermark that hints users to start with the character “U”.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" Watermark="Enter 'U' to filter suggestions" x:Name="comboBox" />
</StackLayout>

{% endhighlight %}

{% highlight c# %}

    StackLayout layout = new StackLayout() 
    { 
	     VerticalOptions = LayoutOptions.Start, 
	     HorizontalOptions = LayoutOptions.Start, 
	     Padding = new Thickness(30) 
    }; 

    SfComboBox comboBox = new SfComboBox();
    comboBox.Watermark = "Enter 'U' to filter suggestions"; 

    layout.Children.Add(comboBox); 
    Content = layout;

{% endhighlight %}

{% endtabs %}

![Watermark text](images/Customizing-ComboBox/watermark.png)

## Changing Watermark Text Color

Text color of watermark can be customized using [`WatermarkColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfComboBox.XForms~Syncfusion.XForms.ComboBox.SfComboBox~WatermarkColor.html) property.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" Watermark="Enter some text" WatermarkColor="#1976d2" x:Name="comboBox" />
</StackLayout>

{% endhighlight %}

{% highlight c# %}

    StackLayout layout = new StackLayout() 
    { 
	     VerticalOptions = LayoutOptions.Start, 
	     HorizontalOptions = LayoutOptions.Start, 
	     Padding = new Thickness(30) 
    }; 

    SfComboBox comboBox = new SfComboBox();
    comboBox.Watermark = "Enter some text"; 
    comboBox.WatermarkColor = Color.FromHex("1976d2");

    layout.Children.Add(comboBox); 
    Content = layout;

{% endhighlight %}

{% endtabs %}

![Watermark color](images/Customizing-ComboBox/watermark-color.png)
