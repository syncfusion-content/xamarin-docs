---
layout : post
title : Types of Syncfusion ChipGroup control for Xamarin.Forms
description : A quick go through to learn about available types of chips.
platform : xamarin
control : Chips
documentation : ug
---

# Set type for the chip group

No operations can be performed in this group. To do any action in this stage,set the `Type` property for SfChipGroup. The chips control provides four different types, and each has its own functionality. The types are 

* Action
* Choice
* Filter and 
* Input chips. 

## Input:

Arrange the chips with its any of customer provided editors. By enabling user input, you can convert that input into chip. 

## Choice:

Allows you select a single chip from a group of items. By selecting a single chip automatically, deselect the other chips. The `SelectedItem` property holds the currently selected chip.

## Filter:

Allows you select more than one chips from a group of chips. You can select more than one chip by setting the filter type to ChipGroup. To keep the track of selected chips, use the `SelectedItems` property

## Action:

Allows you to execute the command of ChipGroup when tapping the chip.

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

