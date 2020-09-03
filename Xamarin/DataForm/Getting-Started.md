---
layout: post
title: Getting started | SfDataForm | Xamarin | Syncfusion
description: Learn here about getting started with Syncfusion Xamarin DataForm (SfDataForm) control and more details..
platform: xamarin
control: SfDataForm
documentation: ug
---

**SfDataForm**

The SfDataForm control helps editing the data fields of any data object. It can be used to develop various forms such as login, reservation, data entry, etc. Key features includes the following:

* Layout and grouping: Supports to linear, grid layout and floating label layout with grouping support. Supports customizing the layout with different heights for each item.
* Caption customization: Supports loading the image as caption for the editor.
* Editors: Built-in support for text, numeric, numeric up-down, picker, date picker, time picker, switch,drop-down,autoComplete and checkbox editors. 
* Custom editor: Supports loading the custom editors.
* Validation: Built-in support to validate the data based on the [INotifyDataErrorInfo](https://msdn.microsoft.com/en-us/library/system.componentmodel.inotifydataerrorinfo.aspx) and data annotations. It also programmatically supports validation handling.

# Getting Started with Xamarin DataForm (SfDataForm)

This section explains the quick overview to use the [SfDataForm](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html) for Xamarin.Forms in your application.

## Assembly deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, {Syncfusion Essential Studio Installed location} \Essential Studio\16.x.x.x\Xamarin\lib

Eg: C:\Program Files (x86) \Syncfusion\Essential Studio\16.1.0.24\Xamarin\lib

N> Assemblies can be found in unzipped package location in Mac.

## Adding SfDataForm reference

You can add SfDataForm reference using one of the following methods:

**Method 1: Adding SfDataForm reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfDataForm to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfDataForm](https://www.nuget.org/packages/Syncfusion.Xamarin.SfDataForm), and then install it.

![Adding SfDataForm reference from NuGet](SfDataForm_images/Adding SfDataForm reference.png)

N> Install the same version of SfDataForm NuGet in all the projects.

**Method 2: Adding SfDataForm reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfDataForm control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfDataForm assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfDataForm.XForms.dll<br/>Syncfusion.SfNumericTextBox.XForms.dll<br/>Syncfusion.SfNumericUpDown.XForms.dll<br/>Syncfusion.SfComboBox.XForms.dll<br/>Syncfusion.SfAutoComplete.XForms.dll<br/>Syncfusion.Buttons.XForms.dll<br/>Syncfusion.SfMaskedEdit.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/>System.ComponentModel.Annotations<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfDataForm.XForms.dll<br/>Syncfusion.SfDataForm.XForms.Android.dll<br/>Syncfusion.SfNumericTextBox.Android.dll<br/>Syncfusion.SfNumericTextBox.XForms.dll<br/>Syncfusion.SfNumericTextBox.XForms.Android.dll<br/>Syncfusion.SfNumericUpDown.XForms.dll<br/>Syncfusion.SfNumericUpDown.XForms.Android.dll<br/>Syncfusion.SfComboBox.XForms.dll<br/>Syncfusion.SfComboBox.XForms.Android.dll<br/>Syncfusion.SfAutoComplete.XForms.dll<br/>Syncfusion.SfAutoComplete.XForms.Android.dll<br/>Syncfusion.Buttons.XForms.dll<br/>Syncfusion.Buttons.XForms.Android.dll<br/>Syncfusion.SfMaskedEdit.XForms.dll<br/>Syncfusion.SfMaskedEdit.XForms.Android.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfDataForm.XForms.dll<br/>Syncfusion.SfDataForm.XForms.iOS.dll<br/>Syncfusion.SfNumericTextBox.XForms.dll<br/>Syncfusion.SfNumericTextBox.XForms.iOS.dll<br/>Syncfusion.SfNumericUpDown.XForms.dll<br/>Syncfusion.SfNumericUpDown.XForms.iOS.dll<br/>Syncfusion.SfComboBox.XForms.dll<br/>Syncfusion.SfComboBox.XForms.iOS.dll<br/>Syncfusion.SfAutoComplete.XForms.dll<br/>Syncfusion.SfAutoComplete.XForms.iOS.dll<br/>Syncfusion.Buttons.XForms.dll<br/>Syncfusion.Buttons.XForms.iOS.dll<br/>Syncfusion.SfMaskedEdit.XForms.dll<br/>Syncfusion.SfMaskedEdit.XForms.iOS.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/>
</td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfDataForm.XForms.dll<br/>Syncfusion.SfDataForm.XForms.UWP.dll<br/>Syncfusion.SfInput.UWP.dll<br/>Syncfusion.SfShared.UWP.dll<br/>Syncfusion.SfNumericTextBox.XForms.UWP.dll<br/>Syncfusion.SfNumericTextBox.XForms.dll<br/>Syncfusion.SfNumericUpDown.XForms.UWP.dll<br/>Syncfusion.SfNumericUpDown.XForms.dll <br/>Syncfusion.SfComboBox.XForms.dll<br/>Syncfusion.SfComboBox.XForms.UWP.dll<br/>Syncfusion.SfAutoComplete.XForms.dll<br/>Syncfusion.SfAutoComplete.XForms.UWP.dll<br/>Syncfusion.Buttons.XForms.dll<br/>Syncfusion.Buttons.XForms.UWP.dll<br/>Syncfusion.SfMaskedEdit.XForms.dll<br/>Syncfusion.SfMaskedEdit.XForms.UWP.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/>
</td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Launching the data form on each platform

To use the data form inside an application, each platform application must initialize the data form renderer. This initialization step varies from platform to platform and is discussed in the following sections:

### Android

The Android launches the data form without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application.

N> If you are adding the references from toolbox, this step is not needed.

### iOS

To launch the data form in iOS, call the `SfDataFormRenderer.Init()` in the `FinishedLaunching` overridden method of the AppDelegate class after the Xamarin.Forms Framework initialization and before the LoadApplication is called, as demonstrated in the following code example:

{% tabs %}
{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    …
    global::Xamarin.Forms.Forms.Init ();
    SfDataFormRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %} 
{% endtabs %}

### Universal Windows Platform (UWP)

The UWP launches the data form without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application.

### ReleaseMode issue in UWP platform

The known Framework issue in UWP platform is that the custom controls will not render when deployed the application in `Release Mode`.

The above problem can be resolved by initializing the data form assemblies in `App.xaml.cs` file in UWP project as in the following code snippet:

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
    assembliesToInclude.Add(typeof(SfDataFormRenderer).GetTypeInfo().Assembly);
    assembliesToInclude.Add(typeof(SfNumericTextBoxRenderer).GetTypeInfo().Assembly);
    assembliesToInclude.Add(typeof(SfNumericUpDownRenderer).GetTypeInfo().Assembly);
    assembliesToInclude.Add(typeof(SfSegmentedControlRenderer).GetTypeInfo().Assembly);
    assembliesToInclude.Add(typeof(SfComboBoxRenderer).GetTypeInfo().Assembly);
    assembliesToInclude.Add(typeof(SfCheckBoxRenderer).GetTypeInfo().Assembly);
    assembliesToInclude.Add(typeof(SfRadioButtonRenderer).GetTypeInfo().Assembly);
    assembliesToInclude.Add(typeof(SfMaskedEditRenderer).GetTypeInfo().Assembly);
    assembliesToInclude.Add(typeof(SfTextInputLayoutRenderer).GetTypeInfo().Assembly);
    assembliesToInclude.Add(typeof(SfAutoCompleteRenderer).GetTypeInfo().Assembly);
    
    // replaces Xamarin.Forms.Forms.Init(e);        
    Xamarin.Forms.Forms.Init(e, assembliesToInclude);
        
    …     
}
{% endhighlight %}
{% endtabs %}

## Supported platforms

* Android
* iOS
* Windows (UWP)

## Creating the data form

In this section, you will create Xamarin.Forms application with `SfDataForm`. The control should be configured entirely in C# code.

* Creating the project.
* Adding data form in Xamarin.Forms.
* Creating data object.
* Setting data object.

### Creating the project

Create a new BlankApp (.Net Standard) application in Xamarin Studio or Visual Studio for Xamarin.Forms.

### Adding data form in Xamarin.Forms

To add the data form to your application, follow the steps:

1. Add required assemblies as discussed in assembly deployment section.
2. Import the control namespace as `xmlns:dataForm="clr-namespace:Syncfusion.XForms.DataForm;assembly=Syncfusion.SfDataForm.XForms` in XAML Page.
3. Create an instance of data form control and add as a view to the linear layout.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             xmlns:dataForm="clr-namespace:Syncfusion.XForms.DataForm;assembly=Syncfusion.SfDataForm.XForms"
             x:Class="GettingStarted.MainPage">
        <dataForm:SfDataForm x:Name="dataForm"/>    
</ContentPage>

{% endhighlight %}
{% highlight c# %}

using Syncfusion.XForms.DataForm;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfDataForm dataForm;
        public MainPage()
        {            
            InitializeComponent();
            dataForm = new SfDataForm();
        }
    }
}

{% endhighlight %}
{% endtabs %}

### Creating data object

The `SfDataForm` is a data edit control so, create a data object to edit the data object.

Here, the data object named **ContactsInfo** created with some properties.

{% tabs %}
{% highlight c# %}

public class ContactsInfo
{
    private string firstName;
    private string middleName;
    private string lastName;
    private string contactNo;
    private string email;
    private string address;
    private DateTime? birthDate;
    private string groupName;

    public ContactsInfo()
    {

    }

    public string FirstName
    {
        get { return this.firstName; }
        set
        {
            this.firstName = value;
        }
    }

    public string MiddleName
    {
        get { return this.middleName; }
        set
        {
            this.middleName = value;
        }
    }
    public string LastName
    {
        get { return this.lastName; }
        set
        {
            this.lastName = value;
        }
    }

    public string ContactNumber
    {
        get { return contactNo; }
        set
        {
            this.contactNo = value;
        }
    }

    public string Email
    {
        get { return email; }
        set
        {
            email = value;
        }
    }

    public string Address
    {
        get { return address; }
        set
        {
            address = value;
        }
    }

    public DateTime? BirthDate
    {
        get { return birthDate; }
        set
        {
            birthDate = value;
        }
    }

    public string GroupName
    {
        get { return groupName; }
        set
        {
            groupName = value;
        }
    }
}

{% endhighlight %}
{% endtabs %}

N> If you want your data model to respond to property changes, then implement `INotifyPropertyChanged` interface in your model class.

Create a model repository class with ContactsInfo property initialized with required data in a new class file as shown in the following code example and save it ViewModel.cs file:

{% tabs %}
{% highlight c# %}

public class ViewModel
{
    private ContactsInfo contactsInfo;
    public ContactsInfo ContactsInfo
    {
        get { return this.contactsInfo; }
        set { this.contactsInfo = value; }
    }
    public ViewModel()
    {
        this.contactsInfo = new ContactsInfo();
    }
}

{% endhighlight %}
{% endtabs %}

## Setting data object

To populate the labels and editors in the data form, set the [DataObject](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_DataObject) property.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             xmlns:dataForm="clr-namespace:Syncfusion.XForms.DataForm;assembly=Syncfusion.SfDataForm.XForms"
             x:Class="GettingStarted.MainPage">
    <ContentPage.BindingContext>
        <local:ViewModel/>
    </ContentPage.BindingContext>    
	<dataForm:SfDataForm x:Name="dataForm" 
						 DataObject="{Binding ContactsInfo}"/>    
</ContentPage>

{% endhighlight %}
{% highlight c# %}

dataForm.DataObject = new ContactsInfo();

{% endhighlight %}
{% endtabs %}

Now, run the application to render the `data form` to edit the data object as in the following screenshot:

![Setting data object to data form in Xamarin.Forms DataForm](SfDataForm_images/Overview.png)

You can download the entire source code of this demo for Xamarin.Forms from here [DataFormGettingStarted](https://github.com/SyncfusionExamples/xamarin.forms-DataForm-getting-started/).

## Defining editors

The data form control automatically generates [DataFormItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItemManager.html#Syncfusion_XForms_DataForm_DataFormItemManager_DataFormItems) (which has UI settings of data field) when the data object set to the `SfDataForm.DataObject` property. The [DataFormItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html) encapsulates the layout and editor setting for the data field appearing in the data form. When the `DataFormItems` are generated, you can handle the SfDataForm.AutoGeneratingDataFormItem event to customize or cancel the `DataFormItem`. 

The type of input editor generated for the data field depends on the type and attribute settings of the property. The following table lists the `DataFormItem` and its constraints for generation:

<table>
<tr>
<th>Generated DataFormItem Type</th>
<th>Data Type / Attribute</th>
</tr>
<tr>
<td>
{{'[DataFormTextItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormTextItem.html)'| markdownify }}
</td>
<td>
Default DataFormItem generated for the String type and the properties with [DataType(DataType.Text)], [DataType(DataType.MultilineText)] and [DataType(DataType.Password)] attributes.
</td>
</tr>
<tr>
<td>
{{'[DataFormNumericItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormNumericItem.html)'| markdownify }}
</td>
<td>
Generated for the Int or Double type property.
[DataType(DataType.Currency)].
[DataType("Percent")]
</td>
</tr>
<tr>
<td>
{{'[DataFormDateItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormDateItem.html)'| markdownify }}
</td>
<td>
Generated for the DateTime type property.
[DataType(DataType.Date)].
[DataType(DataType.DateTime)].
</td>
</tr>
<tr>
<td>
{{'[DataFormTimeItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormTimeItem.html)'| markdownify }}
</td>
<td>
Generated for the DataTime type property.
[DataType(DataType.Time)].
</td>
</tr>
<tr>
<td>
{{'[DataFormPickerItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormPickerItem.html)'| markdownify }}
</td>
<td>
Generated for the Enum type property.
[EnumDataTypeAttribute]
</td>
</tr>
<tr>
<td>
{{'[DataFormSegmentItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormSegmentItem.html)'| markdownify }}
</td>
<td>
Generated for the Enum type property.
[EnumDataTypeAttribute]
</td>
</tr>
<tr>
<td>
{{'[DataFormCheckBoxItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormCheckBoxItem.html)'| markdownify }}
</td>
<td>
Generated for the Bool type property.
[BoolDataTypeAttribute]
</td>
</tr>
<tr>
<td>
{{'[DataFormMaskedEditTextItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormMaskedEditTextItem.html)'| markdownify }}
</td>
<td>
Generated for the PhoneNumber type property.
[DataType(DataType.PhoneNumber)]
</td>
</tr>
<tr>
<td>
{{'[DataFormAutoCompleteItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormAutoCompleteItem.html)'| markdownify }}
</td>
<td>
Generated for the Enum type property.
[EnumDataTypeAttribute]
</td>
</tr>
<tr>
<td>
{{'[DataFormDropDowneItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormDropDownItem.html)'| markdownify }}
</td>
<td>
Generated for the Enum type property.
[EnumDataTypeAttribute]
</td>
</tr>
</table>

The following list of editors are supported:

<table>
<tr>
<th>Editor</th>
<th>Data Type/Attribute</th>
<th>Input control loaded</th>
</tr>
<tr>
<td>
Text
</td>
<td>
The String type property and any other type apart from the following specified cases.
</td>
<td>
{{'[Entry](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.entry?view=xamarin-forms)'| markdownify }}
</td>
</tr>
<tr>
<td>
MultilineText
</td>
<td>
The String type property with multi line text.
[DataType(DataType.Multiline)] 
</td>
<td>
{{'[Editor](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.editor?view=xamarin-forms)'| markdownify }}
</td>
</tr>
<tr>
<td>
Numeric
</td>
<td>
Int or Double type property.
</td>
<td>
{{'[SfNumericTextBox](https://help.syncfusion.com/xamarin/sfnumerictextbox/overview)'| markdownify }}
</td>
</tr>
<tr>
<td>
Percent
</td>
<td>
The Int or Double type Property with percent value.
[DataType("Percent")]].
</td>
<td>
{{'[SfNumericTextBox](https://help.syncfusion.com/xamarin/sfnumerictextbox/overview)'| markdownify }}
</td>
</tr>
<tr>
<td>
Currency
</td>
<td>
The Int or Double type property with currency value.
[DataType(DataType.Currency)].
</td>
<td>
{{'[SfNumericTextBox](https://help.syncfusion.com/xamarin/sfnumerictextbox/overview)'| markdownify }}
</td>
</tr>
<tr>
<td>
Date
</td>
<td>
The DateTime type property with date value.
[DataType(DataType.Date)]
[DataType(DataType.DateTime)]
</td>
<td>
{{'[DatePicker](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.datepicker?view=xamarin-forms)'| markdownify }}
</td>
</tr>
<tr>
<td>
Time
</td>
<td>
Property with [DataType(DataType.Time)] attribute.
</td>
<td>
{{'[TimePicker](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.timepicker?view=xamarin-forms)'| markdownify }}
</td>
</tr>
<tr>
<td>
NumericUpDown
</td>
<td>
Int or Double type property.
</td>
<td>
{{'[SfNumericUpDown](https://help.syncfusion.com/xamarin/sfnumericupdown/overview)'| markdownify }}
</td>
</tr>
<tr>
<td>
Segment
</td>
<td>
Enum type property.
</td>
<td>
{{'[SfSegmentedControl](https://help.syncfusion.com/xamarin/sfsegmentedcontrol/overview)'| markdownify }}
</td>
</tr>
<tr>
<td>
Bool
</td>
<td>
Bool type property.
</td>
<td>
{{'[SfCheckBox](https://help.syncfusion.com/xamarin/sfcheckbox/overview)'| markdownify }}
</td>
</tr>
<tr>
<td>
Switch
</td>
<td>
Bool type property.
</td>
<td>
{{'[Switch](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.switch?view=xamarin-forms)'| markdownify }}
</td>
</tr>
<tr>
<td>
Picker
</td>
<td>
Enum and List type property. 
[EnumDataTypeAttribute]
</td>
<td>
{{'[Picker](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.picker?view=xamarin-forms)'| markdownify }}
</td>
</tr>
<tr>
<td>
DropDown
</td>
<td>
Enum and List type property.
[EnumDataTypeAttribute]
</td>
<td>
{{'[SfComboBox](https://help.syncfusion.com/xamarin/sfcombobox/overview)'| markdownify }}
</td>
</tr>
<tr>
<td>
AutoComplete
</td>
<td>
Enum and List type property.
[EnumDataTypeAttribute]
</td>
<td>
{{'[SfAutoComplete](https://help.syncfusion.com/xamarin/sfautocomplete/overview)'| markdownify }}
</td>
</tr>
<tr>
<td>
Password
</td>
<td>
The String type property with [DataType(DataType.Password)] attribute.
</td>
<td>
{{'[Entry](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.entry?view=xamarin-forms)'| markdownify }}
</td>
</tr>
<tr>
<td>
RadioGroup
</td>
<td>
Enum and List type property.
[EnumDataTypeAttribute]
</td>
<td>
{{'[SfRadioGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfRadioGroup.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
MaskedEditText
</td>
<td>
Property with [DataType(DataType.PhoneNumber)] attribute.
</td>
<td>
{{'[SfMaskedEdit](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.MaskedEdit.html)'| markdownify }}
</td>
</tr>
</table>

## Layout options

### Label position

By default, the data form arranges the label at left side and input control at the right side. You can change the label position by setting the [SfDataForm.LabelPosition](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_LabelPosition) property. You can position the label from left to top of the input control by setting the `LabelPosition` as Top.

{% tabs %}
{% highlight xaml %}

<dataForm:SfDataForm LabelPosition="Top"/>

{% endhighlight %}
{% highlight c# %}

dataForm.LabelPosition = LabelPosition.Top;

{% endhighlight %}
{% endtabs %}

![Setting label position to data form item in Xamarin.Forms DataForm](SfDataForm_images/LabelPosition.png)

### Grid layout

By default, the data form arranges one data field per row. It is possible to have more than one date field per row by setting the [ColumnCount](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_ColumnCount) property which provides grid like layout for the data form.

{% tabs %}
{% highlight xaml %}

<dataForm:SfDataForm ColumnCount="2"/>

{% endhighlight %}
{% highlight c# %}

dataForm.ColumnCount = 2;

{% endhighlight %}
{% endtabs %}

![Setting column count to data form in Xamarin.Forms DataForm](SfDataForm_images/ColumnCount.png)

## Loading DataForm inside StackLayout

StackLayout positions the child elements one after another either horizontally or vertically. Space of the [StackLayout](https://docs.microsoft.com/en-us/dotnet/api/Xamarin.Forms.StackLayout?view=xamarin-forms) depends on the HorizontalOptions and VerticalOptions properties. Views in a stack layout can be sized based on space in the layout using layout options.

The DataForm control can be loaded inside any layout such as [Grid](https://docs.microsoft.com/en-us/dotnet/api/Xamarin.Forms.Grid?view=xamarin-forms), [StackLayout](https://docs.microsoft.com/en-us/dotnet/api/Xamarin.Forms.StackLayout?view=xamarin-forms), etc. When loading DataForm inside a `StackLayout`, set the [HorizontalOptions](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html) and [VerticalOptions](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html) properties of DataForm, and set parent(StackLayout) of DataForm to `LayoutOptions.FillAndExpand`.

Refer to the following code example to load the DataForm control inside a `StackLayout`. Set the VerticalOptions and HorizontalOptions of the `StackLayout` and DataForm to `FillAndExpand`.

{% tabs %}
{% highlight xaml %}

<StackLayout x:Name="stackLayout" VerticalOptions="FillAndExpand" HorizontalOptions="FillAndExpand">
    <dataForm:SfDataForm x:Name="dataForm" VerticalOptions="FillAndExpand" HorizontalOptions="FillAndExpand"/>
</StackLayout>

{% endhighlight %}
{% highlight c# %}

public partial class MainPage : ContentPage
{
    StackLayout StackLayout;
    SfDataForm dataForm;
    public MainPage()
    {
		InitializeComponent();
		stackLayout = new StackLayout();         
		stackLayout.VerticalOptions = LayoutOptions.FillAndExpand;
		stackLayout.HorizontalOptions = LayoutOptions.FillAndExpand;
		dataForm = new SfDataForm();
		dataForm.DataObject = new ContactInfo();
		dataForm.VerticalOptions = LayoutOptions.FillAndExpand;
		dataForm.HorizontalOptions = LayoutOptions.FillAndExpand;
		stackLayout.Children.Add(dataform);
		this.Content = stackLayout;
	}
}
 
{% endhighlight %}
{% endtabs %}

![Launching data form inside a StackLayout Xamarin.Forms DataForm](SfDataForm_images/LayoutOptions.jpg)

## Loading DataForm with customized height and width

The DataForm can be loaded with specific height and width inside different layouts using the [SfDataForm.HeightRequest](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html) and [SfDataForm.WidthRequest](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html) properties.

{% tabs %}
{% highlight xaml %}

<dataForm:SfDataForm x:Name="dataForm" WidthRequest="300"
        HeightRequest="300" 
        VerticalOptions="CenterAndExpand"
        HorizontalOptions="Center"/>

{% endhighlight %}
{% highlight c# %}

dataForm.HeightRequest = 300;
dataForm.WidthRequest = 300;
dataForm.VerticalOptions = LayoutOptions.CenterAndExpand;
dataForm.HorizontalOptions = LayoutOptions.Center;

{% endhighlight %}
{% endtabs %}

![Loading data form with customized height and width Xamarin.Forms DataForm](SfDataForm_images/CustomHeightWidth.jpg)

## Editing

By default, the data form enables editing of the data field. You can disable editing by setting the [IsReadOnly](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_IsReadOnly) property of the data form. You can enable or disable editing for a particular data field by setting the [IsReadOnly](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html#Syncfusion_XForms_DataForm_DataFormItem_IsReadOnly) property of [DataFormItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html) in the `AutoGeneratingDataFormItem` event. The data field editing behavior can also be defined by using [EditableAttribute](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.editableattribute?view=netframework-4.8Dip)

## See also

[How to render DataForm using MVVMCross in Xamarin.Forms](https://www.syncfusion.com/kb/10321/)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     
[How to render DataForm using RealmObject in Xamarin.Forms](https://www.syncfusion.com/kb/10313/)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  
[How to render DataForm using ReactiveUI in Xamarin.Forms](https://www.syncfusion.com/kb/10310/)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                
[How to bind data object in Xamarin.Forms DataForm (SfDataForm) using Fresh MVVM framework](https://www.syncfusion.com/kb/11241/)                                                                                                                                                                                                                                                                                   
[How to bind data object in Xamarin.Forms DataForm(SfDataForm) using Prism framework](https://www.syncfusion.com/kb/11033/)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     
[How to import and export data objects from SQLite Offline database into Dataform (SfDataForm)](https://www.syncfusion.com/kb/11028/)                                                                                                                                                                                           
[How to render DataForm using FSharp application in Xamarin.Forms](https://www.syncfusion.com/kb/10326/)                                                                                                                                                                                    
[How to bind JSON data to Xamarin.Forms DataForm (SfDataForm)](https://www.syncfusion.com/kb/11310/)