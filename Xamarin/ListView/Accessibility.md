---
layout: post 
title: Automation in Xamarin ListView Control | Syncfusion
description: Describes about setting automation id to ListView for automation framework to find and interact with control inner elements.
platform: Xamarin
control: ListView
documentation: ug
---
# Accessibility in Xamarin ListView (SfListView)

The ListView control has built-in [AutomationId](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~AutomationId.html) for all their inner elements. The `AutomationId` API allows the automation framework to find and interact with the inner elements of the ListView control. To keep unique `AutomationId`, these inner element's AutomationIds are updated based on ListView control AutomationId.

For example, if we set ListView’s AutomationId as “Automation” then the Automation framework will interact with items of the ListView as `AutomationItem1`.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
    <ContentPage.Content>
        <Grid>
            <listView:SfListView x:Name="listView" ItemsSource="{Binding OrderItemCollection}" AutomationId="Automation">
			</listView:SfListView>
		</Grid>
	</ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% endtabs %}