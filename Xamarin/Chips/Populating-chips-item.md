---
layout: post
title: Populating the chip item in Syncfusion Chips control in Xamarin.Forms.
description: This section describes how to bind the item sources to populate items in the chips and populating collection of SfChip in chips.
platform: Xamarin
control: Chips
documentation: ug
---

# Populating chips in Xamarin Charts (SfChip)

Chips can be populated with either business objects and SfChip. This section explain how to populate the chips control with business objects and SfChip.

## Populating business objects as items

Business objects can be populated in Chips using the `ItemsSource` property.
Refer to this [documentation](https://help.syncfusion.com/xamarin/chips/getting-started#set-layout-for-the-control) to know more details about populating the chips control with list of employee details.

## Populating SfChip as items

Chips control also provides support to create and set SfChip as item. It can be achieved using the `Items` property.

{% tabs %}

{% highlight xaml %}

<ContentPage
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:local="clr-namespace:Chips"
    x:Class="Chips.GettingStarted">
	<ContentPage.Content>
		<buttons:SfChipGroup Type="Action">
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
			var chipGroup = new SfChipGroup(){Type = SfChipsType.Action};
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

![Collection of items to chip group](images/items/chips_items.png)

## See also

[How to bind remote JSON data to Xamarin.Forms chip group (SfChipGroup)](https://www.syncfusion.com/kb/11370/how-to-bind-remote-json-data-to-xamarin-forms-chip-group-sfchipgroup)
