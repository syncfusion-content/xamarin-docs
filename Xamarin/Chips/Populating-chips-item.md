---
layout: post
title: Populating Items in Xamarin Chips Control | Syncfusion
description: Learn about populating items support in Syncfusion Essential Studio® Xamarin Chips control, its elements, and more.
platform: Xamarin
control: Chips
documentation: ug
---

# Populating Items in Xamarin Chips

Chips can be populated with either business objects or SfChip instances. This section explains how to populate the Chips control with both business objects and SfChip instances.

## Populating Business Objects as Items

Business objects can be populated in Chips using the `ItemsSource` property. Refer to this [documentation](https://help.syncfusion.com/xamarin/chips/getting-started#set-layout-for-the-control) for more details about populating the Chips control with a list of employee details.

## Populating SfChip as Items

The Chips control also provides support to create and set [`SfChip`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChip.html) as an item. This can be achieved using the [`Items`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfChipGroup.html#Syncfusion_XForms_Buttons_SfChipGroup_Items) property.

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

![Collection of Items to Chip Group](images/items/chips_items.png)

## See Also

- [How to bind remote JSON data to Xamarin.Forms chip group (SfChipGroup)](https://support.syncfusion.com/kb/article/9880/how-to-bind-remote-json-data-to-xamarin-forms-chip-group-sfchipgroup)
