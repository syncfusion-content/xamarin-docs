---
layout: post
title: Layout | SfDataForm | Xamarin.Forms | Syncfusion
description: This section explains layouts and its customization and other functionalities in SfDataForm for Xamarin.Forms platform.
platform: xamarin
control: SfDataForm
documentation: UG
---

# Layout in Xamarin.Forms DataForm (SfDataForm)

## Overview

The data form supports linear and grid layouts. The DataFormLayoutManager creates the [DataFormItemView](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItemView.html), [DataFormGroupItemView](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormGroupItemView.html), and manages layout of label, editor, and validation label.

## Linear layout support

By default, the data form arranges the fields one-by-one. It is applicable for both label positions: left and top.

When the label position is Left, the linear layout is shown as follows:

![Arranging data form field in linear layout when label position as left in Xamarin.Forms DataForm](SfDataForm_images/Linear_LabelLeft.jpg)

When the label position is Top, the linear layout is shown as follows:

![Arranging data form field in linear layout when label position as top in Xamarin.Forms DataForm](SfDataForm_images/Linear_LabelTop.jpg)

## Grid layout support

By default, the data form arranges one data field per row. It is possible to have more than one date fields per row by setting the [ColumnCount](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_ColumnCount) property which provides grid like layout for the data form.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             xmlns:dataForm ="clr-namespace:Syncfusion.XForms.DataForm;assembly=Syncfusion.SfDataForm.XForms"
             x:Class="GettingStarted.MainPage">
    <ContentPage.Content>        
            <dataForm:SfDataForm x:Name="dataForm" ColumnCount="2"/>                    
    </ContentPage.Content>    
</ContentPage>
{% endhighlight %}
{% highlight c# %}
dataForm.ColumnCount = 2;
{% endhighlight %}
{% endtabs %}

N> Setting the `ColumnCount` property to SfDataForm does not arrange the data field in a group according to the column count. To set the column count for data fields in the data form group, refer to [loading different layout for data form group](https://help.syncfusion.com/xamarin/sfdataform/layout?cs-save-lang=1&cs-lang=csharp#loading-different-layout-for-group)

When the label position is Left, the grid layout is shown as follows:

![Arranging data form field in grid layout when label position as left in Xamarin.Forms DataForm](SfDataForm_images/Layout_LabelLeft.png)

When the label position is Top, the grid layout is shown as follows:

![Arranging data form field in grid layout when label position as top in Xamarin.Forms DataForm](SfDataForm_images/Layout_LabelTop.png)

## Label visibility

You can hide the label by defining the [DisplayOptions](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DisplayOptionsAttribute.html) attribute or by handling `AutoGeneratingDataFormItem` event. In this case, only the editor will be loaded.

### Using attributes

{% tabs %}
{% highlight c# %}
private double? percentage;

[DisplayOptions(ShowLabel = false)]
[Display(Prompt = "Enter percentage")]
public double? Percentage
{
    get
    {
        return percentage;
    }
    set
    {
        percentage = value;
        RaisePropertyChanged("Percentage");
    }
}
{% endhighlight %}
{% endtabs %}

### Using event

{% tabs %}
{% highlight c# %}
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Percentage")
    {
        e.DataFormItem.PlaceHolderText = "Enter percentage";
        e.DataFormItem.ShowLabel = false;
    }
}
{% endhighlight %}
{% endtabs %}

![Hiding label of data form field in Xamarin.Forms DataForm](SfDataForm_images/Layout_HideLabel.png)

## Label position

Labels can be positioned either top or left side of the editor. By using the [LabelPosition](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_LabelPosition) property, you can layout the label associated with editor.

By default, the label will be positioned at left side of the editor.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             xmlns:dataForm ="clr-namespace:Syncfusion.XForms.DataForm;assembly=Syncfusion.SfDataForm.XForms"
             x:Class="GettingStarted.MainPage">
    <ContentPage.Content>        
            <dataForm:SfDataForm x:Name="dataForm" LabelPosition="Top"/>                    
    </ContentPage.Content>    
</ContentPage>
{% endhighlight %}
{% highlight c# %}
dataForm.LabelPosition = LabelPosition.Top;
{% endhighlight %}
{% endtabs %}

![Arranging data form field when label position as top in Xamarin.Forms DataForm](SfDataForm_images/Layout_LabelPosition.png)

### Changing label position of the DataFormItem

You can change the label position using the [LabelPosition](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html#Syncfusion_XForms_DataForm_DataFormItem_LabelPosition) property in `DataFormItem`, and it will be handled in the `AutoGeneratingDataFormItem` event.

{% tabs %}
{% highlight xaml %}
<dataForm:SfDataForm x:Name="dataForm" DataObject="{Binding ContactsInfo}"  AutoGeneratingDataFormItem="DataForm_AutoGeneratingDataFormItem">
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.RegisterEditor("Gender", "Segment");
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "Gender")
        {
            e.DataFormItem.LabelPosition = LabelPosition.Top;
        }
        if (e.DataFormItem.Name == "Address")
        {
            e.DataFormItem.LabelPosition = LabelPosition.Top;
        }
    }
}

{% endhighlight %}
{% endtabs %}

![Arranging data form fields when label position mention for each in Xamarin.Forms DataForm](SfDataForm_images/DataFormItem_LabelPosition.png)

## Loading images for label

You can load image instead of label by defining attribute or by handling the `AutoGeneratingDataFormItem` event.

### Using attributes

To show the image as label, use the [ImageName](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DisplayOptionsAttribute.html#Syncfusion_XForms_DataForm_DisplayOptionsAttribute_ImageName) property in [DisplayOptions](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DisplayOptionsAttribute.html) attribute. Images will be taken from …\Resources\drawable folder in Xamarin.Forms.Android, …\Resources folder in Xamarin.Forms.iOS.

{% tabs %}
{% highlight c# %}
private string firstName;
[DisplayOptions(ImageName = "ContactInfo.png")]
public string FirstName
{
    get { return this.firstName; }
    set
    {
        this.firstName = value;
    }
}
{% endhighlight %}
{% endtabs %}

### Using event

By using the [ImageSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html#Syncfusion_XForms_DataForm_DataFormItem_ImageSource) property in the `DataFormItem`, you can load the image as label.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {        
        if (e.DataFormItem.Name == "FirstName")
            e.DataFormItem.ImageSource = ImageSource.FromFile("ContactInfo.png");
    }
}
{% endhighlight %}
{% endtabs %}

![Setting image to data form field in Xamarin.Forms DataForm](SfDataForm_images/LabelCustomized.png)

## Changing order of the DataFormItem

You can change the order of the `DataFormItem` by using attributes or by handling `AutoGeneratingDataFormItem` event.

### Using attributes

You can set the order by using the `Order` property in display attribute.

{% tabs %}
{% highlight c# %}
public class ContactsInfo
{
    private string lastName;
    private string contactNo;       
    public ContactsInfo()
    {

    }

    [Display(Order = 2)]
    public string ContactNumber
    {
        get { return contactNo; }
        set
        {
            this.contactNo = value;
        }
    }

    private string firstName;
    [Display(Order = 0)]
    public string FirstName
    {
        get { return this.firstName; }
        set
        {
            this.firstName = value;
        }
    }

    [Display(Order = 1)]
    public string LastName
    {
        get { return this.lastName; }
        set
        {
            this.lastName = value;
        }
    }
}
{% endhighlight %}
{% endtabs %}

![Ordering label of data form fields in Xamarin.Forms DataForm](SfDataForm_images/LabelOrder.png)

### Using event

You can change the fields order by using the [Order](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html#Syncfusion_XForms_DataForm_DataFormItem_Order) property in the `DataFormItem`.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "FirstName")
            e.DataFormItem.Order = 0;
    }
}
{% endhighlight %}
{% endtabs %}

## Grouping data fields

It is possible to group some fields and set group name in the data form. You can expand or collapse the group by tapping the group item.

Grouping can be achieved by defining attributes or by handling the `AutoGeneratingDataFormItem` event.

### Using attributes

{% tabs %}
{% highlight c# %}
public class ContactsInfo
{
    private string lastName;
    private string contactNo;
    private string email;   
    private DateTime? birthDate;

    public ContactsInfo()
    {

    }

    private string firstName;
    [Display(GroupName = "Name")]
    public string FirstName
    {
        get { return this.firstName; }
        set
        {
            this.firstName = value;
        }
    }
        
    private string middleName;
    [Display(GroupName = "Name")]
    public string MiddleName
    {
        get { return this.middleName; }
        set
        {
            this.middleName = value;
        }
    }
    [Display(GroupName = "Name")]
    public string LastName
    {
        get { return this.lastName; }
        set
        {
            this.lastName = value;
        }
    }
    [Display(GroupName ="Details", ShortName = "ContactNo.")]
    public string ContactNumber
    {
        get { return contactNo; }
        set
        {
            this.contactNo = value;
        }
    }

    [Display(GroupName = "Details")]
    public string Email
    {
        get { return email; }
        set
        {
            email = value;
        }
    }

    [Display(GroupName = "Details")]
    public DateTime? BirthDate
    {
        get { return birthDate; }
        set
        {
            birthDate = value;
        }
    }
}
{% endhighlight %}
{% endtabs %}

### Using event

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "FirstName" || e.DataFormItem.Name == "MiddleName" || e.DataFormItem.Name == "LastName")
            e.DataFormItem.GroupName = "Name";
        else
            e.DataFormItem.GroupName = "Details";
    }
}
{% endhighlight %}
{% endtabs %}

![Assigning group to the data form fields through attribute in Xamarin.Forms DataForm](SfDataForm_images/DataFormGroup_Attributes.png)

![Assigning group to the data form fields through event in Xamarin.Forms DataForm](SfDataForm_images/DataFormGroup_Events.png)

### Changing order of the DataFormGroupItem

You can change the order of the `DataFormGroupItem` by using attributes. You can set the order of data form items in group by using the `Order` property along with `GroupName` property in display attribute.

{% tabs %}
{% highlight c# %}
public class ContactInfo
{
    private string lastName;
    private string contactNo;
    public ContactInfo()
    {

    }

    private string firstName;
    [Display(Order = 0, GroupName = "Name")]
    public string FirstName
    {
        get { return this.firstName; }
        set
        {
            this.firstName = value;
        }
    }

    [Display(Order = 2, GroupName = "Name")]
    public string LastName
    {
        get { return this.lastName; }
        set
        {
            this.lastName = value;
        }
    }

    private string middleName;
    [Display(Order =1, GroupName = "Name")]
    public string MiddleName
    {
        get { return this.middleName; }
        set
        {
            this.middleName = value;
        }
    }

    private string email;
    [Display(Order = 1, GroupName = "Details")]
    public string Email
    {
        get { return email; }
        set
        {
            this.email = value;
        }
    }

    [Display(Order = 0, GroupName = "Details")]
    public string ContactNumber
    {
        get { return contactNo; }
        set
        {
            this.contactNo = value;
        }
    }
}
{% endhighlight %}
{% endtabs %}

![Setting order to the grouped data form fields in Xamarin.Forms DataForm](SfDataForm_images/GroupItemOrder.png)

### Changing group name for group

You can change the `GroupName` for the group in the `AutoGeneratingDataFormItem` event.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormGroupItem != null && e.DataFormGroupItem.GroupName == "Name")
        e.DataFormGroupItem.GroupName = "Name Group";
}
{% endhighlight %}
{% endtabs %}

### Loading different layout for group

You can load linear or grid layout for the particular group by handling the `AutoGeneratingDataFormItem` event.
By setting the `ColumnCount` property in the data form, non-grouped items only will be arranged in the grid layout. To load the grid layout, set the [ColumnCount](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_ColumnCount) for the [DataFormGroupItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormGroupItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormGroupItem != null && e.DataFormGroupItem.GroupName == "Name")
        e.DataFormGroupItem.ColumnCount = 2;
}
{% endhighlight %}
{% endtabs %}

![Setting ColumnCount to the data form group fields in Xamarin.Forms DataForm](SfDataForm_images/DataFormGroupwithLayout.png)

#### Loading linear and grid layout for the group

{% tabs %}
{% highlight c# %}
public class ContactsInfo
{
    private string lastName;
    private string contactNo;
    private string email;   
    private DateTime? birthDate;

    public ContactsInfo()
    {

    }

    private string firstName;
    [Display(GroupName = "Name")]
    public string FirstName
    {
        get { return this.firstName; }
        set
        {
            this.firstName = value;
        }
    }
        
    [Display(GroupName = "Name")]
    public string LastName
    {
        get { return this.lastName; }
        set
        {
            this.lastName = value;
        }
    }
    [Display(GroupName ="Details", ShortName = "ContactNo.")]
    public string ContactNumber
    {
        get { return contactNo; }
        set
        {
            this.contactNo = value;
        }
    }

    [Display(GroupName = "Details")]
    public string Email
    {
        get { return email; }
        set
        {
            email = value;
        }
    }

    [Display(GroupName = "Details")]
    public DateTime? BirthDate
    {
        get { return birthDate; }
        set
        {
            birthDate = value;
        }
    }
}
{% endhighlight %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormGroupItem != null && e.DataFormGroupItem.GroupName == "Name")
        e.DataFormGroupItem.ColumnCount = 2;
}
{% endhighlight %}
{% endtabs %}

In the following image, for the `Name` group, the grid layout is loaded and for the `Details` group, linear layout is loaded:

![etting ColumnCount to the data form fields in Xamarin.Forms DataForm](SfDataForm_images/DataFormGroupwithLayout.png)

#### Setting different column count

You can also set different `ColumnCount` for each group.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormGroupItem != null)
    {
        if (e.DataFormGroupItem.GroupName == "Name")
            e.DataFormGroupItem.ColumnCount = 2;
        else if (e.DataFormGroupItem.GroupName == "Details")
            e.DataFormGroupItem.ColumnCount = 3;
    }
}

{% endhighlight %}
{% endtabs %}

![Setting ColumnCount to different data form fields in Xamarin.Forms DataForm](SfDataForm_images/DataFormGroup_Layout.png)

### Loading group in collapsed state

By default, the group will be loaded in expanded state. You can collapse the group by setting the [IsExpanded](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormGroupItem.html#Syncfusion_XForms_DataForm_DataFormGroupItem_IsExpanded) property to false in the [DataFormGroupItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormGroupItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormGroupItem != null && e.DataFormGroupItem.GroupName == "Name")
        e.DataFormGroupItem.IsExpanded = false;
}
{% endhighlight %}
{% endtabs %}

### Restricting the group expanding and collapsing

You can restrict the group being expanded or collapsed by setting the [AllowExpandCollapse](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormGroupItem.html#Syncfusion_XForms_DataForm_DataFormGroupItem_AllowExpandCollapse) to `false` in the [DataFormGroupItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormGroupItem.html).

In this case, the group will be shown without expander.

![Expand and collapse the data form fields in Xamarin.Forms DataForm](SfDataForm_images/AllowExpandCollapse.png)

### Restricting the group expanding and collapsing using events

You can restrict the group being collapsed by the [GroupItemCollapsing](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html) event. The event occurs when a user tries to collapse a group. You can cancel the user action using the `Cancel` property of [GroupItemCollapsingEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.GroupItemCollapsingEventArgs.html).

{% tabs %}
{% highlight xaml %}
<dataForm:SfDataForm x:Name="dataForm" GroupItemCollapsing="DataForm_GroupItemCollapsing"/>
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.GroupItemCollapsing += DataForm_GroupItemCollapsing;
private void DataForm_GroupItemCollapsing(object sender, GroupItemCollapsingEventArgs e)
        {
            e.Cancel = true;
        }
{% endhighlight %}
{% endtabs %}

You can restrict the group being expanded by the [GroupItemExpanding](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html) event. The event occurs when a user tries to expand a group. You can cancel the user action using the `Cancel` property of [GroupItemExpandingEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.GroupItemExpandingEventArgs.html).

{% tabs %}
{% highlight xaml %}
<dataForm:SfDataForm x:Name="dataForm" GroupItemExpanding="DataForm_GroupItemExpanding"/>
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.GroupItemExpanding += DataForm_GroupItemExpanding;
private void DataForm_GroupItemExpanding(object sender, GroupItemExpandingEventArgs e)
        {
            e.Cancel = true;
        }
{% endhighlight %}
{% endtabs %}

### Customize the group name when collapsing/expanding the group

You can customize the group name when you collapse the group using the [GroupItemCollapsed](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html) event. It will be triggered when a group gets collapsed by the user. It will provide information about the collapsed group by using the [GroupItemCollapsedEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.GroupItemCollapsedEventArgs.html) of the `GroupItemCollapsed` event.

{% tabs %}
{% highlight xaml %}
<dataForm:SfDataForm x:Name="dataForm" GroupItemCollapsed="DataForm_GroupItemCollapsed"/>
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.GroupItemCollapsed += DataForm_GroupItemCollapsed;
private void DataForm_GroupItemCollapsed(object sender, GroupItemCollapsedEventArgs e)
        {
            e.DataFormGroupItem.GroupName = "City";
        }
{% endhighlight %}
{% endtabs %}

You can customize the group name when expanding the group using the [GroupItemExpanded](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html) event. It will be triggered when a group gets expanded by the user. It will provide information about the expanded group by using the [GroupItemExpandedEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.GroupItemExpandedEventArgs.html) of the `GroupItemExpanded` event.

{% tabs %}
{% highlight xaml %}
<dataForm:SfDataForm x:Name="dataForm" GroupItemCollapsed="DataForm_GroupItemExpanded"/>
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.GroupItemExpanded += DataForm_GroupItemExpanded;
private void DataForm_GroupItemExpanded(object sender, GroupItemExpandedEventArgs e)
        {
            e.DataFormGroupItem.GroupName = "Country";
        }
{% endhighlight %}
{% endtabs %}

### Programmatically expand or collapse group

You can expand or collapse the group programmatically by using [ExpandGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_ExpandGroup_System_String_) and [CollapseGroup](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_CollapseGroup_System_String_) methods respectively.

{% tabs %}
{% highlight c# %}
dataForm.ExpandGroup("Group1");

dataForm.CollapseGroup("Group1");
{% endhighlight %}
{% endtabs %}

### Changing DataFormGroupItem visibility
You can change the [DataFormGroupItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormGroupItem.html) visibility by using the [IsVisible](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItemBase.html#Syncfusion_XForms_DataForm_DataFormItemBase_IsVisible) property in the `DataFormGroupItem`.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
	if(e.DataFormGroupItem != null )
	{
        if (e.DataFormGroupItem.GroupName == "Details")
            e.DataFormGroupItem.IsVisible = false;
	}
}
{% endhighlight %}
{% endtabs %}

Here, the `Details` group will be hidden.

## Customizing DataFormLayoutManager

To customize the layout, override the [DataFormLayoutManager](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormLayoutManager.html) and assign to the [SfDataForm.LayoutManager](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_LayoutManager) property.

{% tabs %}
{% highlight c# %}
public class DataFormLayoutManagerExt : DataFormLayoutManager
{
    public DataFormLayoutManagerExt(SfDataForm dataForm) : base(dataForm)
    {

    }
}
dataForm.LayoutManager = new DataFormLayoutManagerExt(dataForm);
{% endhighlight %}
{% endtabs %}

### Customize group collapse icon

You can customize the group collapse icon using the [GetGroupCollapseIcon](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormLayoutManager.html#Syncfusion_XForms_DataForm_DataFormLayoutManager_GetGroupCollapseIcon_Syncfusion_XForms_DataForm_DataFormGroupItem_) method.

{% tabs %}
{% highlight c# %}
dataForm.LayoutManager = new DataFormLayoutManagerExt(dataForm);
 public class DataFormLayoutManagerExt : DataFormLayoutManager
    {
        public DataFormLayoutManagerExt(SfDataForm dataForm) : base(dataForm)
        {
             
        }
        protected internal ImageSource  GetGroupCollapseIcon()
        {
          return null;
        }
    }
{% endhighlight %}
{% endtabs %}

### Customize group expander icon

You can customize the group expander icon using the [GetGroupExpanderIcon](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormLayoutManager.html#Syncfusion_XForms_DataForm_DataFormLayoutManager_GetGroupExpanderIcon_Syncfusion_XForms_DataForm_DataFormGroupItem_) method.

{% tabs %}
{% highlight c# %}
 dataForm.LayoutManager = new DataFormLayoutManagerExt(dataForm);
 public class DataFormLayoutManagerExt : DataFormLayoutManager
    {
        public DataFormLayoutManagerExt(SfDataForm dataForm) : base(dataForm)
        {
             
        }
        protected internal ImageSource  GetGroupExpanderIcon()
        {
          return null;
        }
    }
{% endhighlight %}
{% endtabs %}

### Changing  padding
To customize the padding, override the below `DataFormLayoutManager` methods and assign to the `SfDataForm.LayoutManager` property.

* You can change the editor padding by overriding the `GetLeftPaddingForEditor` and `GetRightPaddingForEditor` methods,

* You can change the group header padding by overriding the `GetLeftPaddingForGroupHeader`  and `GetRightPaddingForGroupHeader` methods.

* You can change the group icon padding by overriding the `GetLeftPaddingForGroupIcon` and `GetRightPaddingForGroupIcon` methods.

* You can change the label padding by overriding the `GetLeftPaddingForLabel` and `GetRightPaddingForLabel` methods, its applicable only for `DataForm.LayoutOptions` is `Default`.

* You can change the validation label padding by overriding the `GetLeftPaddingForValidationLabel` and `GetRightPaddingForValidationLabel` methods, its applicable only for `DataForm.LayoutOptions` is `Default`.

{% tabs %}
{% highlight c# %}
dataForm.LayoutManager = new DataFormLayoutManagerExt(dataForm);
public class DataFormLayoutManagerExt : DataFormLayoutManager
{
    public DataFormLayoutManagerExt(SfDataForm dataForm) : base(dataForm)
    {

    }
    protected override int GetLeftPaddingForEditor(DataFormItem dataFormItem)
    {
       return 20;
    }
    protected override int GetRightPaddingForEditor(DataFormItem dataFormItem)
    {
       return 50;
    }
    protected override int GetLeftPaddingForGroupHeader(DataFormItem dataFormItem)
    {
       return 50;
    }
    protected override int GetLeftPaddingForGroupIcon(DataFormItem dataFormItem)
    {
       return 50;
    }
    protected override int GetLeftPaddingForLabel(DataFormItem dataFormItem)
    {
       if (dataFormItem.Name == "FirstName")
          return 50;
       return base.GetLeftPaddingForLabel(dataFormItem);
    }
    protected override int GetLeftPaddingForValidationLabel(DataFormItem dataFormItem)
    {
       if (dataFormItem.Name == "FirstName")
          return 50;
       return base.GetLeftPaddingForValidationLabel(dataFormItem);
    }
    protected override int GetRightPaddingForGroupHeader(DataFormItem dataFormItem)
    {
       return 50;
    }
    protected override int GetRightPaddingForGroupIcon(DataFormItem dataFormItem)
    {
       return 50;
    }
    protected override int GetRightPaddingForLabel(DataFormItem dataFormItem)
    {
       if (dataFormItem.Name == "FirstName")
          return 50;
       return base.GetLeftPaddingForLabel(dataFormItem);
    }
    protected override int GetRightPaddingForValidationLabel(DataFormItem dataFormItem)
    {
       if (dataFormItem.Name == "FirstName")
           return 50;
       return base.GetLeftPaddingForValidationLabel(dataFormItem);
    }
}
{% endhighlight %}
{% endtabs %}

Here, the LastName padding is customized.

![Editor with left padding in Xamarin.Forms DataForm](SfDataForm_images/Layout_LeftPadding.png)

### Customizing label and editor

By using DataFormLayoutManager class , you can customize the generated label by overriding the `GenerateViewForLabel` method and also you can customize the editor by overriding the `OnEditorCreated` method.Here, BackgroundColor and TextColor of label and editor is customized.

{% tabs %}
{% highlight c# %}

public class ContactsInfo
{
    public ContactsInfo()
    {

    }

    private string firstName = "Iris";
    public string FirstName
    {
        get { return this.firstName; }
        set
        {
            this.firstName = value;
        }
    }

    private string lastName;
    public string LastName
    {
        get { return this.lastName; }
        set
        {
            this.lastName = value;
        }
    }
}
{% endhighlight %}
{% highlight c# %}

dataForm.LayoutManager = new DataFormLayoutManagerExt(dataForm);

public class DataFormLayoutManagerExt : DataFormLayoutManager
{
    public DataFormLayoutManagerExt(SfDataForm dataForm) : base(dataForm)
    {

    }

    protected override View GenerateViewForLabel(DataFormItem dataFormItem)
    {
        var label = base.GenerateViewForLabel(dataFormItem);
        if (label is Label)
        { 
            (label as Label).BackgroundColor = Color.FromHex("#ff9522");
            (label as Label).TextColor = Color.White;
        }
        return label;
    }
    
    protected override void OnEditorCreated(DataFormItem dataFormItem, View editor)
    { 
        if (editor is Entry)
            (editor as Entry).TextColor = Color.White;
        editor.BackgroundColor = Color.FromHex("#0073dc"); 
    }
}
{% endhighlight %}
{% endtabs %}

![Customization of label through LayoutManager in Xamarin.Forms DataForm](SfDataForm_images/Layout_LabelCustomization.jpg)

## Label width customization

You can set label and editor width proportionally by using [LabelWidth](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_LabelWidth) and [EditorWidth](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_EditorWidth) properties.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             xmlns:dataForm ="clr-namespace:Syncfusion.XForms.DataForm;assembly=Syncfusion.SfDataForm.XForms"
             x:Class="GettingStarted.MainPage">
    <ContentPage.Content>        
            <dataForm:SfDataForm x:Name="dataForm" LabelWidth="1" EditorWidth="2"/>                    
    </ContentPage.Content>    
</ContentPage>
{% endhighlight %}
{% highlight c# %}
dataForm.LabelWidth = 1;
dataForm.EditorWidth = 2;
{% endhighlight %}
{% endtabs %}

Here, the available width is divided into proportionally for editor (2) and label (1).

![Customization of label width in Xamarin.Forms DataForm](SfDataForm_images/Layout_LabelWidth.png)

N> It is applicable only when `LabelPosition` is Left.

By default, the available width is divided equally for editor and label.

## Spanning rows and columns

You can increase row height and column width by defining the `DisplayOptions` attribute or by handling `AutoGeneratingDataFormItem` event.

### Row span

### Using attributes

You can increase the row height by using the [RowSpan](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DisplayOptionsAttribute.html#Syncfusion_XForms_DataForm_DisplayOptionsAttribute_RowSpan) property in the`DisplayOptions` attribute.

{% tabs %}
{% highlight c# %}
private string firstName;
[DisplayOptions(RowSpan = 2)]
public string FirstName
{
    get { return this.firstName; }
    set
    {
        this.firstName = value;
    }
}
{% endhighlight %}
{% endtabs %}

### Using event

You can increase the row height of each `DataFormItem` using the [RowSpan](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItemBase.html#Syncfusion_XForms_DataForm_DataFormItemBase_RowSpan) property and it will be handled in the `AutoGeneratingDataFormItem` event.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender,AutoGeneratingDataFormItemEventArgs e)
{
if (e.DataFormItem != null)
{
if (e.DataFormItem.Name == "FirstName" )
{
e.DataFormItem.RowSpan = 2;
}
}
}
{% endhighlight %}
{% endtabs %}

Here, `FirstName` field’s row height is increased.

![Setting row span to data form item in Xamarin.Forms DataForm](SfDataForm_images/Layout_RowSpan.png)

### Column span

### Using attributes

When the grid layout is used, you can increase the column width by using the [ColumnSpan](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DisplayOptionsAttribute.html#Syncfusion_XForms_DataForm_DisplayOptionsAttribute_ColumnSpan) property in the `DisplayOptions `attribute.

{% tabs %}
{% highlight c# %}
dataForm.ColumnCount = 2;
{% endhighlight %}
{% highlight c# %}
private string firstName;
[DisplayOptions(ColumnSpan = 2)]
public string FirstName
{
    get { return this.firstName; }
    set
    {
        this.firstName = value;
    }
}
{% endhighlight %}
{% endtabs %}

### Using event

When the grid layout is used, you can increase the column width of each `DataFormItem` using the [ColumnSpan](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItemBase.html#Syncfusion_XForms_DataForm_DataFormItemBase_ColumnSpan)  property and it will be handled in the `AutoGeneratingDataFormItem` event.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender,AutoGeneratingDataFormItemEventArgs e)
{
if (e.DataFormItem != null)
{
if (e.DataFormItem.Name == "FirstName" )
{
e.DataFormItem.ColumnSpan = 2;
}
}
}

{% endhighlight %}
{% endtabs %}

![Setting column span to data form item in Xamarin.Forms DataForm](SfDataForm_images/Layout_ColumnSpan.png)

## Change DataFormItem visibility at runtime

You can change the field visibility by using the [IsVisible](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItemBase.html#Syncfusion_XForms_DataForm_DataFormItemBase_IsVisible) property in the `DataFormItem`.

{% tabs %}
{% highlight c# %}
var dataFormItem = dataForm.ItemManager.DataFormItems["Name"];
if (dataFormItem.Name == "Name")
{
    dataFormItem.IsVisible = false;
}
{% endhighlight %}
{% endtabs %}
Here, the `Name` field will be hidden.

## Change DataFormGroupItem visibility at runtime

You can change the [DataFormGroupItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormGroupItem.html) visibility by using the [IsVisible](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItemBase.html#Syncfusion_XForms_DataForm_DataFormItemBase_IsVisible) property in the `DataFormGroupItem`.

{% tabs %}
{% highlight c# %}
var dataFormGroupItem = dataForm.ItemManager.GetDataFormGroupItem("Name");
if (dataFormGroupItem.GroupName == "Name")
{
	dataFormGroupItem.IsVisible = false;
}
{% endhighlight %}
{% endtabs %}

Here, the `Name` group will be hidden.

![DataFormGroupItem visibility at runtime in Xamarin.Forms DataForm](SfDataForm_images/CollapseGroupItems.gif)

## Programmatically scroll to specific editor

You can programmatically scroll to specific editor using the [ScrollTo](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_ScrollTo_System_String_) method by passing the `property name`. 

{% tabs %}
{% highlight c# %}
dataForm.ScrollTo("ContactNumber")
{% endhighlight %}
{% endtabs %}

![Scroll to specific editor in Xamarin.Forms DataForm](SfDataForm_images/xamarin-forms-scrolltosupport.gif)

## Changing the height of DataFormItem.

You can define the height of each `DataFormItem` using the [Height](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html#Syncfusion_XForms_DataForm_DataFormItem_Height) property, and it will be handled in the `AutoGeneratingDataFormItem` event.

You can define the `Height` as described as follows.

* You can directly set the exact `Height` value; it considers the `GridLength` as `GridUnitType.Absolute`. 
* You can use the `GridLength.Auto` to size the height of `DataFormItem`, so that it fits to the label text that it contains. 
* You can use the `GridLength.Star` to display the default `DataFormItem` height. 

{% tabs %}

{% highlight c# %}

dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender,AutoGeneratingDataFormItemEventArgs e)
{
   if (e.DataFormItem != null)
     {
         if (e.DataFormItem.Name == "Experience" || e.DataFormItem.Name == "Rating" || e.DataFormItem.Name == "Recommend")
         {
             e.DataFormItem.Height = GridLength.Auto;
         }
         if (e.DataFormItem.Name == "Improvement")
         {
             e.DataFormItem.Height = 200;
         }
     }
}
{% endhighlight %}

{% endtabs %}

![Data form item height in Xamarin.Forms DataForm](SfDataForm_images/xamarin.forms-Height.png)