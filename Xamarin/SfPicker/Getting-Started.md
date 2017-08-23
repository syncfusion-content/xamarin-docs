---

layout: post
title: Getting Started with Syncfusion Picker control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion Picker control for Xamarin.Forms platform.
platform: Xamarin
control: Picker
documentation: ug

---


# Getting Started

This section explains you the steps to configure a SfPicker control in a real-time scenario and also provides a walk-through on some of the customization features available in SfPicker control.

## Adding SfPicker reference 

Refer this [article](https://help.syncfusion.com/xamarin/introduction/download-and-installation) to know how to obtain and reference Essential Studio components in your solution; then refer [this](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfpicker) link to know about the assemblies required for adding SfPicker to your project.

## Initialize SfPicker on each platform

To use SfPicker inside an application, each platform application must initialize the SfPicker renderer. This initialization step varies from platform to platform and is discussed in the following sections.

### Android

The Android launches the SfPicker without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application.

### iOS

To launch the SfPicker in iOS, you need to call the `new SfPickerRenderer ()` in the `FinishedLaunching` overridden method of the AppDelegate class after the Xamarin.Forms Framework initialization and before the LoadApplication is called, as demonstrated in the following code example:

{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
…
global::Xamarin.Forms.Forms.Init ();
new SfPickerRenderer ();
LoadApplication (new App ());
…
}
{% endhighlight %} 


The SfPicker control is configured entirely in C# code or by using XAML markup. The following steps explains how to create a SfPicker and configure its elements.

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight xaml %}

<xmlns:picker="clr-namespace:Syncfusion.SfPicker.XForms;assembly=Syncfusion.SfPicker.XForms"/>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfPicker.XForms;

{% endhighlight %}

{% endtabs %}


## Create your first Picker in Xamarin.Forms

The Picker control can be configured entirely in C# code or by using XAML markup.

1) Create new BlankApp (Xamarin.Forms.Portable) application in Xamarin Studio or Visual Studio.

2) Now, create a simple data source as shown in the following code example. Add the following code example in a newly created class file and save it PickerGettingStartedViewModel.cs file.

{% highlight C# %}

public class PickerGettingStartedViewModel : INotifyPropertyChanged
{
		private ObservableCollection<object> source;

		private bool isShowHeader = false;

		private bool isShowColumnHeader = true;

		private bool isShowFooter = false;

		private int selectedIndex = 2;

		private string headerText = "SELECT A COLOR";

		public event PropertyChangedEventHandler PropertyChanged;

		public PickerGettingStartedViewModel()
		{
			source = new ObservableCollection<object>();
			source.Add("Yellow");
			source.Add("Green");
			source.Add("Navy");
			source.Add("Orange");
			source.Add("Lime");
			source.Add("Purple");
			source.Add("Pink");
			source.Add("Red");
			source.Add("Gray");

		}

		public ObservableCollection<object> Source
		{
			get
			{
				return source;
			}

			set
			{
				source = value;
			}
		}

		public bool IsShowHeader
		{
			get
			{
				return isShowHeader;
			}

			set
			{
				isShowHeader = value;
				OnPropertyChanged("IsShowHeader");
			}
		}
		public bool IsShowFooter
		{
			get
			{
				return isShowFooter;
			}

			set
			{
				isShowFooter = value;
				OnPropertyChanged("IsShowFooter");
			}
		}
		public bool IsShowColumnHeader
		{
			get
			{
				return isShowColumnHeader;
			}

			set
			{
				isShowColumnHeader = value;
				OnPropertyChanged("IsShowColumnHeader");
			}
		}

		public string HeaderText
		{
			get
			{
				return headerText;
			}

			set
			{
				headerText = value;
				OnPropertyChanged("HeaderText");
			}
		}

		public int SelectedIndex
		{
			get
			{
				return selectedIndex;
			}

			set
			{
				selectedIndex = value;
				OnPropertyChanged("SelectedIndex");
			}
		}

		void OnPropertyChanged(string propertyName)
		{
			if (PropertyChanged != null)
			PropertyChanged.Invoke(this, new PropertyChangedEventArgs(propertyName));
		}
}

{% endhighlight %}


3)You can set the data source of the Picker by using the SfPicker.ItemsSource property as follows.

{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
xmlns:local="clr-namespace:Picker_GettingStarted"
xmlns:Syncfusion="clr-namespace:Syncfusion.SfPicker.XForms;assembly=Syncfusion.SfPicker.XForms"
x:Class="Picker_GettingStarted.Picker_GettingStartedPage">
	<ContentPage.Content>
		<Syncfusion:SfPicker 
		x:Name="sfPicker"  
		SelectedIndex="{Binding SelectedIndex}"
		ItemsSource="{Binding Source}" 
		ShowHeader="{Binding IsShowHeader}"  
		ShowColumnHeader="{Binding IsShowColumnHeader}" 
		HeaderText="{Binding HeaderText}"
		ShowFooter="{Binding isShowFooter}"
		ColumnHeaderText="{Binding ColumnHeaderTextCollection}"/>
	</ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

public partial class Picker_GettingStartedPage : ContentPage
{
	public Picker_GettingStartedPage()
	{
		InitializeComponent();
		var viewModel = new PickerGettingStartedViewModel();
		this.BindingContext =  viewModel;
	}
}

{% endhighlight %}

4.	Essential Picker for Xamarin.Forms allows you to apply the header and footer on it. The following code illustrates this.

{% highlight xaml %}

<ContentPage.Content>
	<Syncfusion:SfPicker 
	x:Name="sfPicker"  
	SelectedIndex="{Binding SelectedIndex}"
	ItemsSource="{Binding Source}" 
	ShowHeader="true"  
	ShowFooter="true"
	ShowColumnHeader="true" 
	HeaderText="{Binding HeaderText}"
	ColumnHeaderText="{Binding ColumnHeaderTextCollection}"/>
</ContentPage.Content>
	
{% endhighlight %}

![](images/gettingstarted.png)








