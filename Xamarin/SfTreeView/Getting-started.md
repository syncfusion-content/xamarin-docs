---
layout: post
title: Getting Started with TreeView for Xamarin.Forms | Syncfusion
description: User guide explains needed references, adding control to app, binding data etc. with demo app.
platform: xamarin
control: SfTreeView
documentation: ug
---

# Getting Started

This section provides a quick overview for getting started with the TreeView for Xamarin.Forms. Walk through the entire process of creating an app with TreeView.

## Assembly Deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the {Syncfusion Essential Studio Installed location}\Essential Studio\{{ site.releaseversion }}\Xamarin\lib installation folder.

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Xamarin\lib

Refer [control dependencies](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sftreeview) section to get the list of assemblies or NuGet package needs to be added as reference to use the TreeView control in any application.

N> Assemblies can be found in an unzipped package location in Mac.

### Adding TreeView Reference

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add TreeView to your project, open the NuGet package manager in Visual Studio, and search for [Syncfusion.Xamarin.SfTreeView](https://www.nuget.org/packages/Syncfusion.Xamarin.SfTreeView/), and then install it. 

![Xamarin Forms TreeView Add](TreeView_images/TreeView_AddTreeView.png)

To know more about obtaining our components, refer to these links: [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows). Also, if you prefer to manually refer the assemblies instead of NuGet, refer to this [link](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sftreeview) to know about the dependent assemblies for TreeView. 

N>Install the same version of the TreeView NUGET in all the projects.

I> After adding the reference, an additionally need to initialize the renderer for [iOS](https://help.syncfusion.com/xamarin/treeview/getting-started#ios) and [UWP](https://help.syncfusion.com/xamarin/treeview/getting-started#universal-windows-platform-uwp) projects.  

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also must include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Launching the TreeView on Each Platform

To use this control inside an application, each platform application must initialize the TreeView renderer. This initialization step varies from platform to platform, and is discussed in the following sections:

### Android

The Android launches the TreeView without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application.

### iOS

To launch the TreeView in iOS, call the `SfTreeViewRenderer.Init()` in the `FinishedLaunching` overridden method of the AppDelegate class after the Xamarin.Forms Framework initialization, and before the LoadApplication is called as demonstrated in the following code example:

{% tabs %}
{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    …
    global::Xamarin.Forms.Forms.Init ();
    SfTreeViewRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %} 
{% endtabs %}

### Universal Windows Platform (UWP)

To launch the TreeView in UWP, call the `SfTreeViewRenderer.Init()` in the `MainPage` constructor before the LoadApplication is called as demonstrated in the following code example:

{% tabs %}
{% highlight c# %}
public MainPage()
{
    …
    SfTreeViewRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %} 
{% endtabs %}

### ReleaseMode Issue in UWP Platform

The known Framework issue in UWP platform is the custom controls will not render when deployed the application in `Release Mode`.

The above problem can be resolved by initializing the TreeView assemblies in `App.xaml.cs` in UWP project as in the following code snippet:

{% tabs %}
{% highlight c# %}
// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
{
    …

    rootFrame.NavigationFailed += OnNavigationFailed;
        
    // you'll need to add `using System.Reflection;`
    List<Assembly> assembliesToInclude = new List<Assembly>();

    //Now, add all the assemblies your app uses
    assembliesToInclude.Add(typeof(SfTreeViewRenderer).GetTypeInfo().Assembly);

    // replaces Xamarin.Forms.Forms.Init(e);        
    Xamarin.Forms.Forms.Init(e, assembliesToInclude);
        
    …     
}
{% endhighlight %}
{% endtabs %}

## Create a tree view

This section explains how to create a TreeView and configure it. The TreeView control can be configured entirely in C# code, or by using XAML markup. This is how the control will look like on iOS, Android, and Windows devices.

![Xamarin Forms TreeView Create](TreeView_images/TreeView_TreeView.png)

In this walk through, you will create a new application with the TreeView that includes the following topics:

* [Creating the project](#creating-the-project)
* [Adding tree view in Xamarin.Forms](#adding-the-tree-view-in-xamarin.forms)     
* [Populating Nodes without data source - Unbound Mode](#populating-nodes-without-data-source---unbound-mode) 
* [Creating Data Model](#creating-data-model-for-the-tree-view)  
* [Bind to a hierarchical data source - Bound Mode](#bind-to-a-hierarchical-data-source---bound-mode)
* [Defining a template to expander and content view](#defining-a-template-to-expander-and-content-view)
* [Interacting with a tree view](#interacting-with-a-tree-view)
* [Selection](#selection)

## Creating the Project

Create a new [blank (Xamarin.Forms.NET Standard) application](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/get-started/first-app/?pivots=windows) in Xamarin Studio or Visual Studio for Xamarin.Forms.

## Adding the tree view in Xamarin.Forms 

 1. Add the required assembly references to the corresponding projects as discussed in the [Assembly deployment](#assembly-deployment) section.
 2. Import the SfTreeView control namespace Syncfusion.XForms.TreeView.
 3. Set the TreeView control to the ContentPage.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.TreeView;assembly=Syncfusion.SfTreeView.XForms"
             xmlns:local="clr-namespace:GettingStarted;assembly=GettingStarted"
             x:Class="GettingStarted.MainPage">
  <syncfusion:SfTreeView x:Name="treeView" />
</ContentPage>
{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.TreeView;
using Xamarin.Forms;

namespace GettingStarted
{
    public class App : Application
    {
        SfTreeView treeView;
        public App()
        {
            treeView = new SfTreeView();
            MainPage = new ContentPage { Content = treeView};
        }
    }
} 
{% endhighlight %}
{% endtabs %}

## Populating Nodes without data source - Unbound Mode

You can create and manage the [TreeViewNode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.TreeView.Engine.TreeViewNode.html) objects by yourself to display the data in a hierarchical view. To create a tree view, you use a `TreeView` control and a hierarchy of `TreeViewNode` objects. You create the node hierarchy by adding one or more root nodes to the TreeView control’s [Nodes](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~Nodes.html) collection. Each `TreeViewNode` can then have more nodes added to its Children collection. You can nest tree view nodes to whatever depth you require.

>**Important** 
[ItemsSource](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ItemsSource.html) is an alternative mechanism to `Nodes` for putting content into the TreeView control. You cannot set both `ItemsSource` and `Nodes` at the same time. When you use `ItemsSource`, nodes created for you internally, but you cannot access them from `Nodes` property.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.TreeView;assembly=Syncfusion.SfTreeView.XForms"
             xmlns:treeviewengine="clr-namespace:Syncfusion.TreeView.Engine;assembly=Syncfusion.SfTreeView.XForms"
             xmlns:local="clr-namespace:GettingStarted;assembly=GettingStarted"
             x:Class="GettingStarted.MainPage">
    <ContentPage.Content>
       <syncfusion:SfTreeView x:Name="treeView">
            <syncfusion:SfTreeView.Nodes>
                <treeviewengine:TreeViewNode Content="Australia">
                    <treeviewengine:TreeViewNode.ChildNodes>
                        <treeviewengine:TreeViewNode Content="New South Wales">
                            <treeviewengine:TreeViewNode.ChildNodes>
                                <treeviewengine:TreeViewNode Content="Sydney"/>
                            </treeviewengine:TreeViewNode.ChildNodes>
                        </treeviewengine:TreeViewNode>
                    </treeviewengine:TreeViewNode.ChildNodes>
                </treeviewengine:TreeViewNode>
                <treeviewengine:TreeViewNode Content="United States of America">
                    <treeviewengine:TreeViewNode.ChildNodes>
                        <treeviewengine:TreeViewNode Content="New York"/>
                        <treeviewengine:TreeViewNode Content="California">
                            <treeviewengine:TreeViewNode.ChildNodes>
                                <treeviewengine:TreeViewNode Content="San Francisco"/>
                            </treeviewengine:TreeViewNode.ChildNodes>
                        </treeviewengine:TreeViewNode>
                    </treeviewengine:TreeViewNode.ChildNodes>
                </treeviewengine:TreeViewNode>
            </syncfusion:SfTreeView.Nodes>
        </syncfusion:SfTreeView>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
using Syncfusion.TreeView.Engine;
using Syncfusion.XForms.TreeView;
using Xamarin.Forms;

namespace GettingStarted
{
    public class App : Application
    {
        SfTreeView treeView;
        public App()
        {
            treeView = new SfTreeView();

            var australia = new TreeViewNode() { Content = "Australia" };
            var _NSW = new TreeViewNode() { Content = "New South Wales" };
            var Sydney = new TreeViewNode() { Content = "Sydney" };
            australia.ChildNodes.Add(_NSW);
            _NSW.ChildNodes.Add(Sydney);
 
            var usa = new TreeViewNode() { Content = "United States of America" };
            var newYork = new TreeViewNode() { Content = "New York," };
            var California = new TreeViewNode() { Content = "California" };
            var SanFrancisco = new TreeViewNode() { Content = "San Francisco" };
            usa.ChildNodes.Add(newYork);
            usa.ChildNodes.Add(California);
            California.ChildNodes.Add(SanFrancisco);
            treeView.Nodes.Add(australia);
            treeView.Nodes.Add(usa);

            MainPage = new ContentPage { Content = treeView};
        }
    }
} 
{% endhighlight %}
{% endtabs %}

Now, run the application to render the below output:

You can also download the entire source code of this demo from [here](https://github.com/SyncfusionExamples/xamarin-treeview-unbound-mode).

![Xamarin Forms TreeView Unbound](TreeView_images/TreeView_UnBound.png)

## Creating Data Model for the tree view

Create a data model to bind it to the control. 

Create a simple data source as shown in the following code example in a new class file, and save it as FileManager.cs file: 

{% tabs %}
{% highlight c# %}
public class FileManager : INotifyPropertyChanged
{
   private string fileName;
   private ImageSource imageIcon;
   private ObservableCollection<FileManager> subFiles;

   public ObservableCollection<FileManager> SubFiles
   {
      get { return subFiles; }
      set
      {
         subFiles = value;
         RaisedOnPropertyChanged("SubFiles");
      }
   }

   public string ItemName
   {
      get { return fileName; }
      set
      {
         fileName = value;
         RaisedOnPropertyChanged("FolderName");
      }
   }
   
   public ImageSource ImageIcon
   {
       get { return imageIcon; }
       set
       {
          imageIcon = value;
          RaisedOnPropertyChanged("ImageIcon");
       }
   }

   public event PropertyChangedEventHandler PropertyChanged;

   public void RaisedOnPropertyChanged(string _PropertyName)
   {
      if (PropertyChanged != null)
      {
         PropertyChanged(this, new PropertyChangedEventArgs(_PropertyName));
      }
   }
}
{% endhighlight %}
{% endtabs %}

N> If you want your data model to respond to property changes, then implement `INotifyPropertyChanged` interface in your model class.

Create a model repository class with ImageNodeInfo collection property initialized with required number of data objects in a new class file as shown in the following code example, and save it as FileManagerViewModel.cs file:

{% tabs %}
{% highlight c# %}
public class FileManagerViewModel
{
   private ObservableCollection<FileManager> imageNodeInfo;

   public FileManagerViewModel()
   {
      GenerateSource();
   }

   public ObservableCollection<FileManager> ImageNodeInfo
   {
      get { return imageNodeInfo; }
      set { this.imageNodeInfo = value; }
   }

   private void GenerateSource()
   {
      var nodeImageInfo = new ObservableCollection<FileManager>();
      Assembly assembly = typeof(GettingStated).GetTypeInfo().Assembly;
      var doc = new FileManager() { ItemName = "Documents", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_folder.png", assembly) };
      var download = new FileManager() { ItemName = "Downloads", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_folder.png", assembly) };
      var mp3 = new FileManager() { ItemName = "Music", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_folder.png", assembly) };
      var pictures = new FileManager() { ItemName = "Pictures", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_folder.png", assembly) };
      var video = new FileManager() { ItemName = "Videos", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_folder.png", assembly) };

      var pollution = new FileManager() { ItemName = "Environmental Pollution.docx", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_word.png", assembly) };
      var globalWarming = new FileManager() { ItemName = "Global Warming.ppt", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_ppt.png", assembly) };
      var sanitation = new FileManager() { ItemName = "Sanitation.docx", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_word.png", assembly) };
      var socialNetwork = new FileManager() { ItemName = "Social Network.pdf", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_pdf.png", assembly) };
      var youthEmpower = new FileManager() { ItemName = "Youth Empowerment.pdf", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_pdf.png", assembly) };

      var games = new FileManager() { ItemName = "Game.exe", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_exe.png", assembly) };
      var tutorials = new FileManager() { ItemName = "Tutorials.zip", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_zip.png", assembly) };
      var TypeScript = new FileManager() { ItemName = "TypeScript.7z", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_zip.png", assembly) };
      var uiGuide = new FileManager() { ItemName = "UI-Guide.pdf", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_pdf.png", assembly) };

      var song = new FileManager() { ItemName = "Goutiest", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_mp3.png", assembly) };

      var camera = new FileManager() { ItemName = "Camera Roll", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_folder.png", assembly) };
      var stone = new FileManager() { ItemName = "Stone.jpg", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_png.png", assembly) };
      var wind = new FileManager() { ItemName = "Wind.jpg", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_png.png", assembly) };

      var img0 = new FileManager() { ItemName = "WIN_20160726_094117.JPG", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_img0.png", assembly) };
      var img1 = new FileManager() { ItemName = "WIN_20160726_094118.JPG", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_img1.png", assembly) };

      var video1 = new FileManager() { ItemName = "Naturals.mp4", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_video.png", assembly) };
      var video2 = new FileManager() { ItemName = "Wild.mpg", ImageIcon = ImageSource.FromResource("GettingStartedBound.Icons.treeview_video.png", assembly) };

      doc.SubFiles = new ObservableCollection<FileManager>
      {
         pollution,
         globalWarming,
         sanitation,
         socialNetwork,
         youthEmpower
      };

      download.SubFiles = new ObservableCollection<FileManager>
      {
         games,
         tutorials,
         TypeScript,
         uiGuide
      };

      mp3.SubFiles = new ObservableCollection<FileManager>
      {
         song
      };

      pictures.SubFiles = new ObservableCollection<FileManager>
      {
         camera,
         stone,
         wind
      };
      
      camera.SubFiles = new ObservableCollection<FileManager>
      {
         img0,
         img1
      };

      video.SubFiles = new ObservableCollection<FileManager>
      {
         video1,
         video2
      };

      nodeImageInfo.Add(doc);
      nodeImageInfo.Add(download);
      nodeImageInfo.Add(mp3);
      nodeImageInfo.Add(pictures);
      nodeImageInfo.Add(video);
      imageNodeInfo = nodeImageInfo;
  }
}
{% endhighlight %}
{% endtabs %}

## Bind to a hierarchical data source - Bound Mode

You can create a tree view by binding the [ItemsSource](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ItemsSource.html) to a hierarchical data source. To create a tree view using data binding, set a hierarchical collection to the `ItemsSource` property. Then in the [ItemTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ItemTemplate.html) and [ExpanderTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ExpanderTemplate.html), set the child items collection to the `ItemsSource` property.

>**Important** 
`ItemsSource` is an alternative mechanism to [Nodes](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~Nodes.html) for putting content into the TreeView control. You cannot set both `ItemsSource` and `Nodes` at the same time. When you use `ItemsSource`, nodes created for you internally, but you cannot access them from `Nodes` property.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.TreeView;assembly=Syncfusion.SfTreeView.XForms"
             xmlns:treeviewengine="clr-namespace:Syncfusion.TreeView.Engine;assembly=Syncfusion.SfTreeView.XForms"
             xmlns:local="clr-namespace:GettingStarted;assembly=GettingStarted"
             x:Class="GettingStarted.MainPage">
    <ContentPage.BindingContext>
       <local:FileManagerViewModel x:Name="viewModel"></local:FileManagerViewModel>
    </ContentPage.BindingContext>
    <ContentPage.Content>
       <syncfusion:SfTreeView x:Name="treeView" ChildPropertyName="SubFiles" ItemsSource="{Binding ImageNodeInfo}">
       </syncfusion:SfTreeView>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
SfTreeView treeView = new SfTreeView();
FileManagerViewModel viewModel = new FileManagerViewModel ();
treeView.ItemsSource = viewModel.ImageNodeInfo; 
MainPage = new ContentPage { Content = treeView };
{% endhighlight %}
{% endtabs %}

## Defining a template to expander and content view

 By defining the [ExpanderTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ExpanderTemplate.html) and [ItemTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ItemTemplate.html) properties, a custom user interface(UI) can be achieved to display the data items for both expander and content view. It is applicable for both Unbound Mode and Bound Mode data items. 

 N> By default, the binding context for each treeview item will be the data model object for Bound Mode and [TreeViewNode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.TreeView.Engine.TreeViewNode.html) for Unbound Mode. However, you can change the binding context for treeview items in Bound Mode as `TreeViewNode` by defining the [ItemTemplateContextType](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ItemTemplateContextTypeProperty.html) enumeration to `Node` which is applicable for both `ExpanderTemplate` and `ItemTemplate` properties.

The following code example will illustrate you to customize your content view by using `ItemTemplate` and `ExpanderTemplate` property in both XAML and C#.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.TreeView;assembly=Syncfusion.SfTreeView.XForms"
             xmlns:treeviewengine="clr-namespace:Syncfusion.TreeView.Engine;assembly=Syncfusion.SfTreeView.XForms"
             xmlns:local="clr-namespace:GettingStarted;assembly=GettingStarted"
             x:Class="GettingStarted.MainPage">
    <ContentPage.BindingContext>
       <local:FileManagerViewModel x:Name="viewModel"></local:FileManagerViewModel>
    </ContentPage.BindingContext>
    <ContentPage.Content>
       <syncfusion:SfTreeView x:Name="treeView" ItemsSource="{Binding ImageNodeInfo}">
            <syncfusion:SfTreeView.ItemTemplate>
                <DataTemplate>
                    <ViewCell>
                        <ViewCell.View>
                           <Grid x:Name="grid" RowSpacing="0" BackgroundColor="Transparent">
                              <Grid Padding="5,5,5,5">
                                  <Image Source="{Binding ImageIcon}" VerticalOptions="Center"
                                         HorizontalOptions="Center" HeightRequest="35" 
                                         WidthRequest="35"/>
                              </Grid>
                              <Grid Grid.Column="1" RowSpacing="1" Padding="1,0,0,0" VerticalOptions="Center">
                                <Label LineBreakMode="NoWrap" Text="{Binding ItemName}" VerticalTextAlignment="Center"/>
                              </Grid>
                           </Grid>
                        </ViewCell.View>
                    </ViewCell>
                </DataTemplate>
            </syncfusion:SfTreeView.ItemTemplate>
            <syncfusion:SfTreeView.ExpanderTemplate>
                <DataTemplate>
                    <ViewCell>
                        <ViewCell.View>
                            <Image IsVisible="{Binding HasChildNodes,Converter={StaticResource IconVisibleConverter}}" 
                                   Source="{ Binding IsExpanded,Converter={StaticResource ExpanderIconConverter}}"
                                   VerticalOptions="Center" HorizontalOptions="Center"/>
                        </ViewCell.View>
                    </ViewCell>
                </DataTemplate>
            </syncfusion:SfTreeView.ExpanderTemplate>
       </syncfusion:SfTreeView>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
SfTreeView treeView = new SfTreeView();
FileManagerViewModel viewModel = new FileManagerViewModel ();
treeView.ItemsSource = viewModel.ImageNodeInfo; 
treeView.ItemTemplateContextType = ItemTemplateContextType.Node;
treeView.ItemTemplate = new DataTemplate(() => 
{
    var grid = new Grid();
    var imageIcon = new Image();
    imageIcon.SetBinding(Image.SourceProperty, new Binding("Content.ImageIcon"));
    var itemName = new Label { FontSize = 15 };
    itemName.SetBinding(Label.TextProperty, new Binding("Content.ItemName"));

    grid.Children.Add(imageIcon);
    grid.Children.Add(itemName, 1, 0);

    return grid;
});
treeView.ExpanderTemplate = new DataTemplate(()=>
{
    var grid = new Grid();
    var expanderIcon = new Image();
    imageIcon.SetBinding(Image.SourceProperty, new Binding("IsExpanded"));
})
MainPage = new ContentPage { Content = treeView };
{% endhighlight %}
{% endtabs %}

Now, run the application to render the similar output:

You can also download the entire source code of this demo from [here](https://github.com/SyncfusionExamples/xamarin-treeview-databinding).

![Xamarin Forms TreeView Bound](TreeView_images/TreeView_Templating.png)

## Interacting with a tree view

The `TreeView` allows you to expand and collapse the nodes either by user interaction on the nodes or by programmatically. The expanding and collapsing interactions can be handled with the help of [NodeCollapsing](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~NodeCollapsing_EV.html) and [NodeExpanding](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~NodeExpanding_EV.html) events.

 You can define how the nodes to be expanded while loading the `TreeView` by using [AutoExpandMode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~AutoExpandModeProperty.html) property. Also, the `TreeView` allows you to set the restrictions whether expanding and collapsing of nodes can be performed only by tapping in expander view or in both expander view and content view by using [ExpandActionTarget](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~ExpandActionTargetProperty.html) property.

 N> `AutoExpandMode` property is only applicable for bound mode. For Unbound mode you need to set `IsExpanded` property to `true` while creating the nodes, to be in expanded state while loading the TreeView.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.TreeView;assembly=Syncfusion.SfTreeView.XForms"
             xmlns:local="clr-namespace:GettingStarted;assembly=GettingStarted"
             x:Class="GettingStarted.MainPage">
  <syncfusion:SfTreeView x:Name="treeView" AutoExpandMode="AllNodesExpanded"
                         ExpandActionTarget="Node"/>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.TreeView;
using Xamarin.Forms;

namespace GettingStarted
{
    public class App : Application
    {
        SfTreeView treeView;
        public App()
        {
            treeView = new SfTreeView();
            treeView.AutoExpandMode = AutoExpandMode.AllNodesExpanded;
            treeView.ExpandActionTarget = ExpandActionTarget.Node;
            MainPage = new ContentPage { Content = treeView};
        }
    }
} 
{% endhighlight %}
{% endtabs %}

## Selection

The `TreeView` allows selecting the item by setting the [SelectionMode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~SelectionModeProperty.html) property. Set the `SelectionMode` property to single, single-deselect, multiple, extended and none based on the requirements. Informations about the selected item can be tracked using the [SelectedItem](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~SelectedItemProperty.html), [CurrentItem](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~CurrentItemProperty.html) and [SelectedItems](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~SelectedItemsProperty.html) properties. Also, `TreeView` provides key board navigation support in UWP platform.

It also allows changing the selection highlight color by using the [SelectionBackgroundColor](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~SelectionBackgroundColorProperty.html) property. Additionally, for unbound mode, you can change the selection fore ground color of the text by using the [SelectionForegroundColor](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~SelectionForegroundColorProperty.html) property.

The selection operations can be handled with the help of [SelectionChanging](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~SelectionChanging_EV.html) and [SelectionChanged](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeView.XForms~Syncfusion.XForms.TreeView.SfTreeView~SelectionChanged_EV.html).

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.TreeView;assembly=Syncfusion.SfTreeView.XForms"
             xmlns:local="clr-namespace:GettingStarted;assembly=GettingStarted"
             x:Class="GettingStarted.MainPage">
  <syncfusion:SfTreeView x:Name="treeView" SelectionMode="Single"
                         SelectionBackgroundColor="#E4E4E4" SelectionForegroundColor="#D3D3D3"/>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.TreeView;
using Xamarin.Forms;

namespace GettingStarted
{
    public class App : Application
    {
        SfTreeView treeView;
        public App()
        {
            treeView = new SfTreeView();
            treeView.SelectionMode = SelectionMode.Single;
            treeView.SelectionBackgroundColor = Color.FromHex("#E4E4E4");
            treeView.SelectionForegroundColor = Color.FromHex("#D3D3D3");
            MainPage = new ContentPage { Content = treeView};
        }
    }
} 
{% endhighlight %}
{% endtabs %}