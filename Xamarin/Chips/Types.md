---
layout: post
title: Types of Syncfusion ChipGroup control for Xamarin.Forms
description: This section describes about the available types of chips and its behavior in Syncfusion Xamarin.Forms SfChipGroup.
platform: Xamarin.Forms
control: Chips
documentation: ug
---

# Set the type for chip group

The functionality of chips control differ based on its `Type` property.No operation can be performed in a chip group unless the Type property is set. The chips control provides four different types, and each has its own functionality. The types are,

* Action
* Choice
* Filter 
* Input

## Input

Arranges the chips in a layout and enables the close button for each chip. Using the close button, a chip can be removed from children and layout as well. It additionally has support to add an optional `InputView` at the end of the layout, from which users can obtain the chip text for creating a chip at run time.

## Choice

Allows users to select a single chip from a group of items. Selecting a chip will automatically deselect the previously selected chips. The selected chip color can be customized using the `SelectedChipBackgroundColor` and `SelectedChipTextColor` properties. The `SelectedItem` property holds the instance of recently selected chip.

### ChoiceMode

The `ChoiceMode` property allows user to set the selection mode for Choice type `SfChipGroup`. The default value of ChoiceMode property is `Single`. `ChoiceMode` supports the following types of selection mode:

`Single` - At least, one item must be in selected state and the selected item cannot be deselected, if `ChoiceMode` is Single.

`SingleOrNone` - Unlike `Single`, it is possible to deselect the selected item and keep all the items in deselected state.

{% tabs %}

{% highlight xaml %}

<ContentPage
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:local="clr-namespace:Chips"
    x:Class="Chips.GettingStarted">
	<ContentPage.Content>
		<buttons:SfChipGroup Type="Choice" ChoiceMode="SingleOrNone">
			<buttons:SfChipGroup.Items>
				<buttons:SfChip Text="Extra Small"/>
				<buttons:SfChip Text="Small"/>
				<buttons:SfChip Text="Medium"/>
				<buttons:SfChip Text="Large"/>
				<buttons:SfChip Text="Extra Large"/>
			</buttons:SfChipGroup.Items>
		</buttons:SfChipGroup>
	</ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Buttons;
using Xamarin.Forms;

namespace Chips
{
	public partial class GettingStarted: ContentPage
	{
		public GettingStarted()
		{
			InitializeComponent();
			Grid grid = new Grid();
			var chipGroup = new SfChipGroup(){Type = SfChipsType.Choice, ChoiceMode = ChoiceMode.SingleOrNone};
			grid.Children.Add(chipGroup);
			chipGroup.Items.Add(new SfChip(){Text="Extra Small"});
			chipGroup.Items.Add(new SfChip(){Text="Small"});
			chipGroup.Items.Add(new SfChip(){Text="Medium"});
			chipGroup.Items.Add(new SfChip(){Text="Large"});
			chipGroup.Items.Add(new SfChip(){Text="Extra Large"});
			this.Content = grid;
		}
	}
}

{% endhighlight %}

{% endtabs %}

## Filter

Allows users to select more than one chip in a group of chips. The selected chips are indicated by selection indicator in this type. The selection indicator can be customized using the `SelectionIndicatorColor` property. Use the `SelectedItems` property to get the list of selected chips.

## Action

Executes the `Command` of ChipGroup and raises the Clicked event when a chip is clicked.

In this example, the Input chip is used to add an employee at run time. To get the employee name as input, an entry is added as `InputView`.

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

{% endtabs %}

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

## See also

[How to remove the indicator icon from Xamarin.Forms chip group (SfChipGroup)](https://www.syncfusion.com/kb/11270/how-to-remove-the-indicator-icon-from-xamarin-forms-chip-group-sfchipgroup)

[How to restrict chip selection in Xamarin](https://www.syncfusion.com/kb/11205/how-to-restrict-chip-selection-in-xamarin)

[How to select a multiple chips from the Xamarin ChipGroup [SfChipGroup]](https://www.syncfusion.com/kb/11155/how-to-select-a-multiple-chips-from-the-xamarin-chipgroup-sfchipgroup)

