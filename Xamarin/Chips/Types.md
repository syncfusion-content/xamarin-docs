---
layout : post
title : Types of Syncfusion ChipGroup control for Xamarin.Forms
description : A quick go through to learn about available types of chips.
platform : xamarin
control : Chips
documentation : ug
---

# Set type for the chip group

No operations can be performed in a chip group unless Type property is set. The chips control provides four different types, and each has its own functionality. The types are 

* Action
* Choice
* Filter 
* Input chips.

## Input:

Arrange the chips in layout and enables close button for each chip. Using the close button, a chip can be removed from children and layout as well. It additionally has support to add an optional `InputView` at the end of the layout, from that user can obtain chip text for creating a chip at runtime.

## Choice:

Allows user select a single chip from a group of items. Selecting a chip will automatically, unselect the previously selected chips. Selected chip color can be customized by `SelectedChipBackgroundColor` and `SelectedChipTextColor` properties. The `SelectedItem`property holds the instance of recently selected chip.

## Filter:

Allows user to select more than one chip in a group of chips. Selected chips are indicated by selection indicator in this type. Selection indicator can be customized using `SelectionIndicatorColor` property. Use the `SelectedItems` property to get the list of selected chips.

## Action:

Executes the `Command` of ChipGroup and raises the Clicked event when a chip is clicked.

In this example, the Input chip is used to add employee at run time. To get the employee name as input, an entry is added as `InputView`: 

{% tabs %}

{% highlight xaml %}

<ContentPage
xmlns="http://xamarin.com/schemas/2014/forms"
xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
xmlns:local="clr-namespace:Chips"
x:Class="Chips.GettingStarted">
	<ContentPage.BindingContext>
		<local:ViewModel x:Name="viewModel"/>
	</ContentPage.BindingContext>
	<ContentPage.Content>
		<buttons:SfChipGroup 
			x:Name="chipGroup" 
			ItemsSource="{Binding Employees}"
			ChipPadding="8,8,0,0" 
			DisplayMemberPath="Name">
				<buttons:SfChipGroup.ChipLayout>
						<FlexLayout 
						HorizontalOptions="Start" 
						VerticalOptions="Center"
						Direction="Row"
						Wrap="Wrap" 
						JustifyContent="Start" 
						AlignContent="Start" 
						AlignItems="Start"/>
				</buttons:SfChipGroup.ChipLayout>
			<buttons:SfChipGroup.InputView>
				<Entry 
					Margin="10,10,0,0" 
					WidthRequest="110"
					Completed="Entry_Completed"/>
			</buttons:SfChipGroup.InputView>
		</buttons:SfChipGroup>
	</ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Buttons;
using System.Collections.ObjectModel;
using System.ComponentModel;
namespace Chips
{
	public partial class GettingStarted: ContentPage
	{
		public GettingStarted()
		{
			InitializeComponent();
			Grid grid = new Grid();
			SfChipGroup chipGroup = new SfChipGroup();
			grid.Children.Add(chipGroup);
			FlexLayout layout = new FlexLayout()
			{
				Direction = FlexDirection.Row,
				Wrap = FlexWrap.Wrap,
				HorizontalOptions = LayoutOptions.Start,
				VerticalOptions = LayoutOptions.Center,
				AlignContent = FlexAlignContent.Start,
				JustifyContent = FlexJustify.Start,
				AlignItems = FlexAlignItems.Start,
			};
			var entry= new Entry { Margin = new Thickness(10, 10, 0, 0), WidthRequest = 110 };
			entry.Completed += Entry_Completed;
			chipGroup.InputView = entry;
			chipGroup.ChipLayout = layout;
			this.BindingContext = new ViewModel();
			chipGroup.SetBinding(SfChipGroup.ItemsSourceProperty, "Employees");
			chipGroup.DisplayMemberPath = "Name";
			chipGroup.ChipPadding = new Thickness(8, 8, 0, 0);
			this.Content = grid;
		}
	}
}
{% endhighlight %}

{% tabs %}

The following code example demonstrates the dynamic addition of chips into a chip group with the completed event in entry.

{% highlight c# %}
using Xamarin.Forms;
using Syncfusion.XForms.Buttons;

namespace Chips
{
	public partial class GettingStarted : ContentPage
	{ 
		public GettingStarted()
		{
			InitializeComponent();
		}
		private void Entry_Completed(object sender, System.EventArgs e)
		{
			Entry entry = sender as Entry;
			if (entry != null && !string.IsNullOrEmpty(entry.Text))
			{
				viewModel.Employees.Add(new Person() { Name = entry.Text });
			}
		}
	}
}

{% endhighlight %}

N> The `InputView` is visible only in Input type.

