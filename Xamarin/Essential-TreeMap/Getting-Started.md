---
layout: post
title: Getting-Started
description: getting started
platform: xamarin
control: Control Name undefined
documentation: ug
---

### Getting Started

This section provides a quick overview for working with EssentialTreemap for Xamarin.Forms, with a walk-through the entire process of creating a real world Treemap. The goal of this walk-through is to help you visualize population growth across continents.

You can also download the entire source code of this demo from the following link: [http://files2.syncfusion.com/Installs/v12.2.0.40/Samples/Xamarin/TreeMap_GettingStarted.zip](http://files2.syncfusion.com/Installs/v12.2.0.40/Samples/Xamarin/TreeMap_GettingStarted.zip)

Reference Essential Studio Components in your solution

When you acquire Essential Studio components through the Xamarin Component Store interface from your IDE, after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component Manager, you need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL Project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside your solution folder:  

_Components/syncfusionessentialstudio-version/lib/pcl/_

Alternatively when you download Essential Studio from Syncfusion.com or through the Xamarin Store web interface, all the assembly references need to be added manually.  

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically:

_{Syncfusion Installed location}\Essential Studio\12.2.0.40\lib_

_Example: C:\Program Files (x86)\Syncfusion\Essential Studio\12.2.0.40\lib_

Otherwise, after downloading through the Xamarin Store web interface, all the required assemblies can be found in the following folder:

_{download location}\syncfusionessentialstudio-version\lib_

You can then add the assembly references to the respective projects as follows.

PCL project

XForms\Syncfusion.SfTreeMap.XForms.dll  

Android project:

Android\Syncfusion. SfTreeMap.Andriod.dll

Android\Syncfusion. SfTreeMap. XForms.Andriod.dll 

iOS project:

iOS\Syncfusion. SfTreeMap.iOS.dll   

iOS\Syncfusion. SfTreeMap.XForms.iOS.dll

iOS\Syncfusion. SfTreeMap.XForms.dll

Windows Phone project

wp8\Syncfusion. SfTreeMap.WP8.dll

wp8\Syncfusion SfTreeMap.XForms.WinPhone.dll

> ![](Getting-Started_images/Getting-Started_img1.png)
{:.image }
_Note: Essential TreeMap for Xamarin is compatible with Xamarin Forms 1.2.3.6257_

Currently an additional step is required for Windows Phone and iOS projects. You need to create an instance of the TreeMap custom renderer as follows.

1. Create an instance of the SfTreeMapRenderer in MainPage constructor in Windows Phone project as follows.

  	 public MainPage()

       	 {

           		 new SfTreeMapRenderer ();

        		    ...    

     	}

2. Create an instance of the SfTreeMapRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as follows.

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

        	{

         		  ...

         		  new SfTreeMapRenderer ();

        		   ...

       	 }

Initializing the TreeMap

The Treemap control can be configured entirely in C# code or using XAML markup.

The first step is to create a TreeMap object. 



&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;ContentPage xmlns="http://xamarin.com/schemas/2014/forms"xmlns:local="clr-namespace:Syncfusion.SfTreeMap.XForms;assembly=Syncfusion.SfTreeMap.XForms"  xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" x:Class="TreeMapGettingStarted.Sample" BackgroundColor=”Black”&gt;

&lt;ContentPage.Content &gt;
 &lt;local:SfTreeMap x:Name="treeMap"&gt;
&lt;/local:SfTreeMap&gt;

&lt;/ContentPage.Content&gt;
&lt;/ContentPage&gt;







public static Page GetMainPage()

{

SfTreeMap treeMap = new SfTreeMap();



       return new ContentPage

       {

              BackgroundColor = Color.Black,

       	Content = treeMap,

       };

}

Populating TreeMap Items

The TreeMap accepts a collection of TreeMapItems as input.



[XAML]

// BindingContext is set for the content page class.

//DataModel model = new DataModel();

//..

//..

//this.BindingContext = model;



&lt;local:SfTreeMap x:Name="treeMap" Items = "{Binding TreeMapItems}"&gt;

&lt;/local:SfTreeMap&gt;


[C#]



public class DataModel : BindableObject

        {

public static readonly BindableProperty TreeMapItemsProperty =

            BindableProperty.Create<DataModel, ObservableCollection<TreeMapItem>>(p => p.TreeMapItems, null, BindingMode.TwoWay, null, null, null, null);



            public ObservableCollection<TreeMapItem> TreeMapItems

            {

             get { return (ObservableCollection<TreeMapItem>)GetValue(TreeMapItemsProperty); }

             set { SetValue(TreeMapItemsProperty, value); }

            }



            public DataModel()

            {

                this.TreeMapItems = new ObservableCollection<TreeMapItem>();

                TreeMapItems.Add(new TreeMapItem() { Label = "Indonesia", ColorWeight = 3, Weight = 237641326 });

                TreeMapItems.Add(new TreeMapItem() { Label = "Russia", ColorWeight = 2, Weight = 152518015 });

                TreeMapItems.Add(new TreeMapItem() { Label = "United States", ColorWeight = 4, Weight = 315645000 });

                TreeMapItems.Add(new TreeMapItem() { Label = "Mexico", ColorWeight = 2, Weight = 112336538 });

                TreeMapItems.Add(new TreeMapItem() { Label = "Nigeria", ColorWeight = 2, Weight = 170901000 });

                TreeMapItems.Add(new TreeMapItem() { Label = "Egypt", ColorWeight = 1, Weight = 83661000 });

                TreeMapItems.Add(new TreeMapItem() { Label = "Germany", ColorWeight = 1, Weight = 81993000 });

                TreeMapItems.Add(new TreeMapItem() { Label = "France", ColorWeight = 1, Weight = 65605000 });

                TreeMapItems.Add(new TreeMapItem() { Label = "UK", ColorWeight = 1, Weight = 63181775 });

            }

        }



SfTreeMap treeMap = new SfTreeMap();

DataModel model = new DataModel();

treeMap.Items = model.TreeMapItems;

Grouping of TreeMap Items using Levels

You can group TreeMapItems using two types of levels.

1.    TreeMap Flat Level
2.    TreeMap Hierarchical Level

Customize TreeMap Appearance by Range

You can differentiate the nodes based on its value and color ranges using the Range color. You can also define the color value range using the From and To properties. 



[XAML]

&lt;local:SfTreeMap x:Name="treeMap" Items = "{Binding TreeMapItems}"&gt;

  &lt;local:SfTreeMap.LeafItemColorMapping&gt;
       &lt;local:RangeColorMapping&gt;
         &lt;local:RangeColorMapping.Ranges&gt;
           &lt;local:Range LegendLabel = "1 % Growth" From = "0" To = "1" Color =  "#77D8D8"  /&gt;
            &lt;local:Range LegendLabel = "2 % Growth" From = "0" To = "2" Color =  "#AED960"  /&gt;
            &lt;local:Range LegendLabel = "3 % Growth" From = "0" To = "3" Color =  "#FFAF51"  /&gt;
            &lt;local:Range LegendLabel = "4 % Growth" From = "0" To = "4" Color =  "#F3D240"  /&gt;
           &lt;/local:RangeColorMapping.Ranges&gt;
       &lt;/local:RangeColorMapping&gt; 
    &lt;/local:SfTreeMap.LeafItemColorMapping&gt;

&lt;/local:SfTreeMap&gt;

[C#]

…

…

ObservableCollection<Range> ranges = new ObservableCollection<Range>();
ranges.Add(new Range() { LegendLabel="1 % Growth", From = 0, To = 1, Color = Color.FromHex("#77D8D8") });
ranges.Add(new Range() { LegendLabel = "2 % Growth", From = 0, To = 2, Color = Color.FromHex("#AED960") });
ranges.Add(new Range() { LegendLabel = "3 % Growth", From = 0, To = 3, Color = Color.FromHex("#FFAF51") });
ranges.Add(new Range() { LegendLabel = "4 % Growth", From = 0, To = 4, Color = Color.FromHex("#F3D240") });
treeMap.LeafItemColorMapping = new RangeColorMapping (){ Ranges = ranges };

LeafItemSetting

You can customize the Leaf level TreeMap items using LeafItem setting. 

[XAML]

&lt;local:SfTreeMap x:Name="treeMap" Items = "{Binding TreeMapItems}"&gt;

…

&lt;local:SfTreeMap.LeafItemSettings&gt;
        &lt;local: LeafItemSettings BorderWidth=“1" BorderColor=“White"  /&gt;
    &lt;/local:SfTreeMap. LeafItemSettings &gt;

&lt;/local:SfTreeMap&gt;



[C#]

…

LeafItemSettings leafSetting = new LeafItemSettings();
leafSetting.BorderWidth = 1;
leafSetting.BorderColor = Color.White;
treeMap.LeafItemSettings = leafSetting;

Enable Legend

You can set the color value of leaf nodes using the TreeMap Legend. This legend is appropriate only for the TreeMap whose leaf nodes are colored using RangeColorMapping. You can set ShowLegend property value to “True” to make the legend visible.

Label for Legends

You can customize the labels of the legend items using the LegendLabel property of RangeColorMapping. 

[XAML]

&lt;local:SfTreeMap.LegendSettings&gt;
        &lt;local:LegendSettings  ShowLegend ="true" IconSize=“15,15" Size=“350,70"  /&gt;
&lt;/local:SfTreeMap.LegendSettings&gt;



[C#]

…

LegendSettings legendSettings = new LegendSettings();
legendSettings.ShowLegend= true;
legendSettings.IconSize = new Size(15, 15);
legendSettings.Size = new Size (350, 70);
treeMap.LegendSettings= legendSettings;



![C:/Users/lingaraj/Desktop/treemap.png](Getting-Started_images/Getting-Started_img2.png)
{:.image }




