---
layout: post
title: Automation Id | SfDataGrid | Xamarin | Syncfusion
description: Set Automation Id to control inner elements for automation framework to find and interact.
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Automation Id

SfDataGrid control has built in AutomationId for inner elements. These automation id values allows the automation framework to find and interact with those inner elements. To keep unique automation id, inner element automation id's will get updated based on the control's automation id. Please find following code snippet and image to know about the inner element automation id's format.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                           ItemsSource="{Binding OrdersInfo,Mode=TwoWay}"
                           AutomationId="SyncfusionGrid"
                           AllowEditing="True"
                           AllowSorting="True"
                           NavigationMode="Cell"
                           SelectionMode="Single">
    </syncfusion:SfDataGrid>
{% endhighlight %}

{% highlight c# %}
OrderInfoRepository viewModel = new OrderInfoRepository ();
dataGrid.ItemsSource = viewModel.OrderInfoCollection;
dataGrid.AutomationId = "SyncfusionGrid";
dataGrid.AllowEditing = true;
dataGrid.AllowSorting = true;
dataGrid.NavigationMode = NavigationMode.Cell;
dataGrid.SelectionMode = Syncfusion.SfDataGrid.XForms.SelectionMode.Single;
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
// UI Script Automation Codes to interact with second header cell element 

App.DoubleTap("SyncfusionGrid R2C1");

{% endhighlight %}
{% endtabs %}



