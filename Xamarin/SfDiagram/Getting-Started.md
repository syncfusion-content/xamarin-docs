---
title: Getting Started for Essential Xamarin.Forms Diagram | Syncfusion
description: Getting started with Xamarin.Forms diagram and walk through to create a demo application from the scratch.
platform: Xamarin
control: SfDiagram
documentation: UG
keywords: 

---

# Getting started

This section provides a quick overview for working with Diagram for Xamarin.Forms. This walkthrough demonstrates that, how to create a simple flow chart and an organization chart.

## Adding SfDiagram reference

You can add SfDiagram reference using one of the following methods:

**Method 1: Adding SfDiagram reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfDiagram to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfDiagram](https://www.nuget.org/packages/Syncfusion.Xamarin.SfDiagram), and then install it.

![Adding SfDiagram reference from NuGet](Getting-Started_images/Adding SfDiagram reference.png)

N> Install the same version of SfDiagram NuGet in all the projects.

**Method 2: Adding SfDiagram reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfDiagram control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfDiagram assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>.NET Standard</td>
<td>Syncfusion.SfDiagram.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfDiagram.XForms.Android.dll<br/>Syncfusion.SfDiagram.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfDiagram.XForms.iOS.dll<br/>Syncfusion.SfDiagram.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfDiagram.UWP.dll<br/>Syncfusion.SfDiagram.XForms.UWP.dll<br/>Syncfusion.SfDiagram.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

N> If you are adding the references from toolbox, this step is not needed.

### Additional step for iOS

To launch SfDiagram in iOS, call the `SfDiagramRenderer.Init()` in `FinishedLaunching` overridden method of `AppDelegate` class in iOS Project, as demonstrated in the following code example.

{% tabs %}
{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    global::Xamarin.Forms.Forms.Init();
    LoadApplication(new App());
    SfDiagramRenderer.Init();
    return base.FinishedLaunching(app, options);
}
{% endhighlight %}
{% endtabs %}

I>We need to create an instance of the `SfDiagramRenderer` in iOS and UWP projects as shown in this [KB article](https://www.syncfusion.com/kb/8618).

### Additional step for UWP

This step is required only if the application is deployed in Release mode with .NET native tool chain enabled and it is for resolving the known Framework issue “Custom controls not rendering in Release mode” in UWP platform. Initializing the SfDiagram assembly at `OnLaunched` overridden method of the `App` class in UWP project is the suggested work around, as demonstrated in the following code example.

{% tabs %}
{% highlight c# %}
protected override void OnLaunched(LaunchActivatedEventArgs e)
{

    ..... 

    rootFrame.NavigationFailed += OnNavigationFailed;
    // you'll need to add `using System.Reflection;` 
    List<Assembly> assembliesToInclude = new List<Assembly>();
    //Now, add all the assemblies your app uses 
    assembliesToInclude.Add(typeof(SfDiagramRenderer).GetTypeInfo().Assembly);
    // replaces Xamarin.Forms.Forms.Init(e);
    Xamarin.Forms.Forms.Init(e, assembliesToInclude);

    ..... 

}
{% endhighlight %}
{% endtabs %}

I> You can refer to the [KB article](https://www.syncfusion.com/kb/8617) for more details.

## Basic building blocks of Diagram
* **Diagram**- It represents the drawing surface where all the graphical elements like nodes and connectors resides, can be used to display various types of diagrams and it is the root instance of the diagram control. A Diagram instance contains a collection of nodes and  connectors to represent the  graphical diagram.
* **Nodes**- This represents the geometric shapes such as flowchart elements, network diagram elements, use case elements, etc.
* **Connectors-**These are the objects used to create link between two nodes, to represent the relationships between them in the diagram.
* **Ports-**It represents a point in the node, where the connectors can be connected. A Node can contain any number of ports.
* **Annotation-**It is a block of the text that can be displayed over a Node or Connector. Annotation is used to textually represent an object with a string that can be edited at run time.

## Creating a simple flow chart
Create a new cross platform app (Xamarin.Forms) with portable class library in the Visual Studio and name the project as “GettingStarted” and refer to the above mentioned assemblies to the respective projects.
An additional step is required to render the SfDiagram control in iOS project. You need to create an instance of the SfDiagramRenderer class within FinishedLaunching method of AppDelegate class in iOS project as shown as follows
{% tabs %}
{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    global::Xamarin.Forms.Forms.Init();
    LoadApplication(new App());
    new SfDiagramRenderer();
    return base.FinishedLaunching(app, options);
}
{% endhighlight %}
{% endtabs %}

**Adding SfDiagram in Xamarin.Forms**
1. Import SfDiagram control namespace as xmlns:syncfusion="clr-namespace:Syncfusion.SfDiagram.XForms;assembly=Syncfusion.SfDiagram.XForms in XAML Page.
2. Set the SfDiagram control as content to the ContentPage.
{% tabs %}
{% highlight xml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted;assembly=GettingStarted"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfDiagram.XForms;assembly=Syncfusion.SfDiagram.XForms" 
             x:Class="GettingStarted.Sample">
  <ContentPage.Content>
<!--Initializes the SfDiagram-->
       <syncfusion:SfDiagram x:Name="diagram" />
  </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
using Syncfusion.SfDiagram.XForms;
using Xamarin.Forms;
namespace GettingStarted
{
    public class App : Application
    {
        SfDiagram diagram;
        public App()
        {
            //Initializes the SfDiagram
            diagram= new SfDiagram();
            MainPage = new ContentPage { Content = diagram};
        }
    }
}
{% endhighlight %}
{% endtabs %}
The following code snippet illustrates the creation of Nodes and Connectors in the diagram.
{% tabs %}
{% highlight c# %}
public GettingStarted()
        {
           InitializeComponent();
           //Initializes the SfDiagram
           SfDiagram diagram = new SfDiagram();
           Node Begin = AddNode("Begin", 150, 60, 120, 40, "Begin", ShapeType.Ellipse);
           Node Process = AddNode("Process", 150, 140, 120, 60, "Process", ShapeType.Rectangle);
           Node End = AddNode("End", 190, 225, 40, 40, "End", ShapeType.Ellipse);
//Add nodes to the SfDiagram
diagram.AddNode(Begin);
diagram.AddNode(Process);
diagram.AddNode(End);
Connector connector1 = new Connector()
{
SourceNode = Begin,
TargetNode = Process,
};
Connector connector2 = new Connector()
{
SourceNode = Process,
TargetNode = End,
};
//Add connectors to the SfDiagram
diagram.AddConnector(connector1);
diagram.AddConnector(connector2);
this.Content = diagram;
                          }
///<summary>
///create the node
///</summary>
public Node AddNode(string id, float offsetX, float offsetY, float width, float height, string text, ShapeType shape)
{
Node node = new Node();
node.OffsetX = offsetX;
node.OffsetY = offsetY;
node.Height = height;
node.Width = width;
node.ShapeType = shape;
node.Style.Brush = new SolidBrush(Color.FromRgb(100, 149, 237));
node.Annotations.Add(new Annotation() { Content = text});
return node;
}
{% endhighlight %}
{% endtabs %}
The flow chart will get displayed in the SfDiagram as follows

![Getting started demo in Xamarin.Forms diagram](Getting-Started_images/Getting-Started_img2.jpeg)

This demo project can be downloaded from the following link [GettingStarted_Demo.](http://files2.syncfusion.com/Xamarin.Forms/Samples/Gettingstarted_SfDiagram.zip)

## Create a simple organizational chart
SfDiagram provides support to auto-arrange the nodes based on hierarchical relation. Organization chart is an example of displaying hierarchical information.
Now, you have to create a class named “Employee” to store the employee’s information like name, designation, ID, reporting person ID, etc. Also, create a collection class that stores a collection of the employees.
{% tabs %}
{% highlight c# %}
//Employee Business Object
public class Employee
{
    public string ParentId { get; set; }
    public string Name { get; set; }
    public string Designation { get; set; }
    public int EmpId { get; set; }
}
//Employee Collection
public class Employees : ObservableCollection<Employee>  
{
}
{% endhighlight %}
{% endtabs %}

**Initialize Employee data**
Define Employee Information as a Collection. The below code example shows an employee array whose,
* Name is used as a unique identifier and
* ParentId is used to identify the person to whom an employee report to, in the organization.
{% tabs %}
{% highlight xml %}
<!-- Initializes the employee collection--> 
<local:Employees x:Key="employees"> 
<local:Employee Name="Elizabeth" Employee_Id="1" ParentId="" Designation="CEO"/> 
<local:Employee Name="Christina" Employee_Id="2" ParentId="1" Designation="Manager"/> 
<local:Employee Name="Yang" Employee_Id="3" ParentId="1" Designation="Manager"/> 
<local:Employee Name="Yoshi" Employee_Id="4" ParentId="2" Designation="Team Lead"/> 
<local:Employee Name="Philip" Employee_Id="5" ParentId="2" Designation="S/w Developer"/> 
<local:Employee Name="Roland" Employee_Id="6" ParentId="3" Designation="TeamLead"/> 
<local:Employee Name="Yuonne" Employee_Id="7" ParentId="3" Designation="Testing Engineer"/> 
</local:Employees> 
<!--Initializes the DataSourceSettings --> 
<syncfusion:DataSourceSettings x:Key="DataSourceSettings" DataSource="{StaticResource employees}" ParentId="ParentId" Id="Employee_Id" Root="1"/> 
<!--Initializes the Layout--> 
<syncfusion:DirectedTreeLayout x:Key="treeLayout" HorizontalSpacing="80" VerticalSpacing="50" SpaceBetweenSubTrees="20" Orientation="TopToBottom"/> 
<syncfusion:LayoutManager x:Key="layoutManager" Layout="{StaticResource treeLayout}"/> 
<!--Initializes the SfDiagram--> 
<syncfusion:SfDiagram x:Name="diagram" LayoutManager="{StaticResource layoutManager}" DataSourceSettings="{StaticResource DataSourceSettings}">
{% endhighlight %}
{% highlight c# %}
//Initializes the employee collection
ObservableCollection<Employee> employees = new ObservableCollection<Employee>();            
employees.Add(new Employee() { Name = "Elizabeth", Employee_Id = "1", ParentId = "", Designation = "CEO" });
employees.Add(new Employee() { Name = "Christina", Employee_Id = "2", ParentId = "1", Designation = "Manager" });
employees.Add(new Employee() { Name = "Yang", Employee_Id = "3", ParentId = "1", Designation = "Manager" });
employees.Add(new Employee() { Name = "Yoshi", Employee_Id = "4", ParentId = "2", Designation = "Team Lead" });
employees.Add(new Employee() { Name = "Philip", Employee_Id = "5", ParentId = "2", Designation = "S/w Developer" });
employees.Add(new Employee() { Name = "Roland", Employee_Id = "6", ParentId = "3", Designation = "TeamLead" });
employees.Add(new Employee() { Name = "Yvonne", Employee_Id = "7", ParentId = "3", Designation = "Testing Engineer" });
//Initializes the DataSourceSettings
diagram.DataSourceSettings = new DataSourceSettings() { DataSource = employees, Id = "Employee_Id", ParentId = "ParentId" };
//Initializes the Layout
DirectedTreeLayout treeLayout = new DirectedTreeLayout() { HorizontalSpacing = 80, VerticalSpacing = 50, TreeOrientation = TreeOrientation.TopToBottom };
diagram.LayoutManager = new LayoutManager() { Layout = treeLayout };
{% endhighlight %}
{% endtabs %}
The Employee data is displayed in the SfDiagram as follows

![Organizational chart demo in Xamarin.Forms diagram](Getting-Started_images/Getting-Started_img3.jpeg)

This demo project can be downloaded from the following link [OrganizationalChart_Demo.](http://files2.syncfusion.com/Xamarin.Forms/Samples/OrganizationalChart_SfDiagram.zip)
