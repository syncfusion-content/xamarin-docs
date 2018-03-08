---
layout: post
title: Getting Started with Syncfusion SfMaskedEdit control for Xamarin.Forms 
description: A quick tour to initial users on Syncfusion SfMaskedEdit control for Xamarin.Forms platform
platform: Xamarin
control: SfMaskedEdit
documentation: ug
---

# Getting Started
This section explains you the steps to configure a SfMaskedEdit control in a real-time scenario and provides a walk-through on some of the customization features available in SfMaskedEdit control.

## Add SfMaskedEdit reference

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

 **{Syncfusion Essential Studio Installed location}\Essential Studio{Essential Studio version}\Xamarin\lib**

Example: C:\Program Files (x86)\Syncfusion\Essential Studio\16.1.0.24\Xamarin\lib

To know about the assemblies required for adding SfMaskedEdit to your project, refer to the following table: 

### Assemblies
<table>
<tr>
<td>PCL/.NET Standard</td>
<td>Syncfusion.SfMaskedEdit.XForms.dll</td>
</tr>
<tr>
<td>Android</td>
<td>
Syncfusion.SfMaskedEdit.XForms.dll<br/>Syncfusion.SfMaskedEdit.XForms.Android.dll</td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfMaskedEdit.XForms.dll<br/>Syncfusion.SfMaskedEdit.XForms.iOS.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfInput.UWP.dll<br/>Syncfusion.SfShared.UWP.dll<br/>Syncfusion.SfMaskedEdit.XForms.dll<br/>Syncfusion.SfMaskedEdit.XForms.UWP.dll</td>
</tr>
</table>

After adding the assembly reference, an additional step is required for iOS and UWP projects.

### Additional step for iOS

To launch SfMaskedEdit in iOS, call the SfMaskedEditRenderer.Init() in FinishedLaunching overridden method of AppDelegate class after the Xamarin.Forms Framework initialization and before the Load Application is called, as demonstrated in the following code example.


{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
global::Xamarin.Forms.Forms.Init();

new SfMaskedEditRenderer();

LoadApplication(new App());

return base.FinishedLaunching(app, options);
}

{% endhighlight %}


### Additional step for UWP

This step is required only if the application is deployed in Release mode with .NET native tool chain enabled and it is for resolving the known Framework issue “Custom controls not rendering in Release mode” in UWP platform. Initializing the SfMaskedEdit assembly at OnLaunched overridden method of the App class in UWP project is the suggested work around. And the code example is shown below:

{% highlight C# %}

// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
{
rootFrame.NavigationFailed += OnNavigationFailed;
		
// you'll need to add `using System.Reflection;`
List<Assembly> assembliesToInclude = new List<Assembly>();

//Now, add all the assemblies your app uses
assembliesToInclude.Add(typeof(SfMaskedEditRenderer).GetTypeInfo().Assembly);

// replaces Xamarin.Forms.Forms.Init(e);        
Xamarin.Forms.Forms.Init(e, assembliesToInclude);    
}
{% endhighlight %}



## Create a Simple SfMaskedEdit 

The SfMaskedEdit control is configured entirely in C# code or by using XAML markup. The following steps explain how to create a SfMaskedEdit and configure its elements:

**Add namespace for referred assemblies**

{% tabs %}

{% highlight xaml %}

	xmlns:maskedEdit ="clr-namespace:Syncfusion.XForms.MaskedEdit;assembly=Syncfusion.SfMaskedEdit.XForms"

{% endhighlight %}

{% highlight c# %}

	using Syncfusion.XForms.MaskedEdit;

{% endhighlight %}

{% endtabs %}

**Refer SfMaskedEdit control with declared suffix name for Namespace**

{% tabs %}

{% highlight xaml %}

	<?xml version="1.0" encoding="utf-8"?>
	<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" xmlns:local="clr-namespace:GettingStarted" 
	xmlns:syncfusion=" clr-namespace:Syncfusion.XForms.MaskedEdit;assembly=Syncfusion.SfMaskedEdit.XForms " 
	x:Class="GettingStarted.MaskedEditControlPage"> 
	<ContentPage.Content>
 	<syncfusion:SfMaksedEdit x:Name="maskedEdit" /> 
 	</ContentPage.Content> 
 	</ContentPage>

{% endhighlight %}

{% highlight c# %}


using Syncfusion.XForms.MaskedEdit; 
using Xamarin.Forms; 

namespace GettingStarted 
{ 
public partial class MaskedEditControlPage : ContentPage 
{         
public MaskedEditControlPage()
{	  
InitializeComponent();

SfMaskedEdit sfMaskedEdit = new SfMaskedEdit(); 

this.Content = sfMaskedEdit; 
} 

{% endhighlight %}

{% endtabs %}

## Masking the input

To mask the input, set the MaskType and Mask properties as follows:

{% tabs %}

{% highlight xaml %}

	<maskedEdit:SfMaskedEdit MaskType="Text" Mask="00/00/0000"/>
	
{% endhighlight %}

{% highlight c# %}

SfMaskedEdit maskededit = new SfMaskedEdit(); 
maskededit.MaskType = MaskType.Text; 
maskedEdit.Mask = "00/00/0000";
this.Content = maskededit;
{% endhighlight %}

{% endtabs %}

This mask expression allows only numeric inputs in the places of 0.


## Setting Value

Set the Value for the control as follows,

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfMaskedEdit MaskType="Text" Mask="00/00/0000" Value="14/11/2014"/>
	
{% endhighlight %}

{% highlight c# %}

SfMaskedEdit maskededit = new SfMaskedEdit(); 
maskededit.MaskType=MaskType.Text;
maskedEdit.Mask="00/00/0000";
maskedEdit.Value=”14/11/2014”;
this.Content = maskededit;
	
{% endhighlight %}

{% endtabs %}

 
## MaskType

Each MaskType has different set of mask elements that are combined to form a mask expression. Based on the complexity and usage, mask types are classified as:

1.	Text
2.	Reg-Ex

## Text

Expressions that are generated with letters, digits and special characters are come under this group. This is mainly used for fixed length inputs. For example: Phone number, PAN number.

**Text Mask elements:**
<table>
<tr>
<th>Elements</th>
<th>Description</th>
</tr>
<tr>
<td>A</td>
<td>Alphanumeric, required.</td>
</tr>
<tr>
<td>a</td>
<td>Alphanumeric, optional.</td>
</tr>
<tr>
<td>L</td>
<td>Letter, required. Restricts input to the ASCII letters a-z and A-Z. </td>
</tr>
<tr>
<td>l</td>
<td>Letter, optional. Restricts input to the ASCII letters a-z and A-Z. </td>
</tr>
<tr>
<td>0</td>
<td>Digit, required. This element accepts any single digit between 0 and 9</td>
</tr>
<tr>
<td>9</td>
<td>Digit or space, optional. </td>
</tr>
<tr>
<td>#</td>
<td>Digit or space, optional. Plus (+) and minus (-) signs are allowed.  </td>
</tr>
<tr>
<td>C</td>
<td>Character, optional. </td>
</tr>
<tr>
<td>\</td>
<td>Escapes a mask character, turning it into a literal. "\" is the escape sequence for a backslash.  </td>
</tr>
<tr>
<td>Any other characters</td>
<td>Considered as literals. Literals always occupy a static position in the mask at run time, and cannot be moved or deleted. </td>
</tr>
</table>
{% tabs %}

{% highlight xaml %}

	<maskedEdit:SfMaskedEdit MaskType="Text" Mask="+1(000)000000"/>
	
{% endhighlight %}

{% highlight c# %}

SfMaskedEdit maskedEdit=new SfMaskedEdit();
maskedEdit.Mask = "+1(000)000000";
maskedEdit.MaskType = MaskType.Text;
this.Content = mask;

{% endhighlight %}

{% endtabs %}

This mask expression allows only numeric inputs in the places of 0.


## Regex

The expressions that are generated with regular expressions come under this group, preferable for variable length inputs and input in range. For example: Hexadecimal values [0-9A-C].
The regular expressions provide significant advantages when creating masks as compared with other masked modes. 

**Advantages:**
1)	Allows to enter value of indeterminate length.
2)	Restricts with specific pattern. Example email, password etc.
3)	Restricts to enter specific range at specific position.

 **Regex Mask Elements**
<table>
<tr>
<th>Elements</th>
<th>Description</th>
</tr>
<tr>
<td>\w</td>
<td>Accepts any alphabet, number, including the _(Underscore) character.</td>
</tr>
<tr>
<td>\d</td>
<td>Accepts any digit.</td>
</tr>
<tr>
<td>{n}l</td>
<td>Accepts the input for 'n' number of times</td>
</tr>
<tr>
<td>{n,m}</td>
<td>Accepts the input for 'n' minimum number of times and 'm' maximum number of times</td>
</tr>
<tr>
<td>?</td>
<td>Optional input.</td>
</tr>
<tr>
<td>+</td>
<td>Accepts the input for one or more times.</td>
</tr>
<tr>
<td>*</td>
<td>Accepts the input for zero or more times.</td>
</tr>
<tr>
<td>[aeiou]</td>
<td>Accepts any single character included in the specified set of characters. </td>
</tr>
<tr>
<td>[0-9a-fA-F]</td>
<td>Accepts any character between[A-F]/[a-f] and numbers between [0-9].</td>
</tr>
</table>

{% tabs %}

{% highlight xaml %}

	<maskededit:SfMaskedEdit Mask="+(1)(\d{3})\d{5}" MaskType="RegEx" ></maskededit:SfMaskedEdit>
	
{% endhighlight %}

{% highlight c# %}

SfMaskedEdit mask = new SfMaskedEdit();
mask.Mask = @"+(1)(\d{3})\d{5}";
mask.MaskType = MaskType.RegEx;
this.Content = mask;

{% endhighlight %}

{% endtabs %}

This mask expression’\d{3}’ and’ \d{5}’ allows only numeric, where {n} is the count that the input should be accepted.


## Setting Value

The SfMaskedEdit control display value can be set using Value property,

{% tabs %}

{% highlight xaml %}

	<maskedEdit:SfMaskedEdit MaskType="Text" Mask="00/00/0000" Value="14/11/2014"/>
	
{% endhighlight %}

{% highlight c# %}

SfMaskedEdit maskededit = new SfMaskedEdit(); 
maskededit.MaskType=MaskType.Text;
maskedEdit.Mask="00/00/0000";
maskedEdit.Value="14/11/2014";
this.Content = maskededit;

{% endhighlight %}

{% endtabs %}


## Localization
The special symbols like a currency symbol, date separator, decimal separator etc., can be localized to any specific culture with 'Culture' property.

<table>
<tr>
<th>Elements</th>
<th>Description</th>
</tr>
<tr>
<td>.</td>
<td>Decimal separator determined by current culture.</td>
</tr>
<tr>
<td>,</td>
<td>Group separator determined by current culture.</td>
</tr>
<tr>
<td>/</td>
<td>Date separator determined by current culture. </td>
</tr>
<tr>
<td>:</td>
<td>Time separator determined by current culture.</td>
</tr>
<tr>
<td>$</td>
<td>Currency symbol determined by current culture.</td>
</tr>
</table>

{% tabs %}
{% highlight c# %}

SfMaskedEdit mask = new SfMaskedEdit();
mask.Mask = "$ 0,000.00";
mask.MaskType = MaskType.Text;
mask.Culture= new CultureInfo("fr-FR");
this.Content = mask;

{% endhighlight %}
{% endtabs %}

## ValidationMode

Input validation happens based on the value of the ‘ValidationMode’ property. The enum values of this property are

•	KeyPress
•	LostFocus

The default value for validation mode is ‘LostFocus’.


{% tabs %}

{% highlight xaml %}

	<maskededit:SfMaskedEdit  Mask="000000" MaskType="Text" ValidationMode="KeyPress" />
	
{% endhighlight %}

{% highlight c# %}

SfMaskedEdit maskEdit = new SfMaskedEdit(); 
maskEdit.Mask = "000000";
maskEdit.MaskType = MaskType.Text;
maskEdit.ValidationMode = InputValidationMode.KeyPress;
this.Content = maskEdit;


{% endhighlight %}

{% endtabs %}

When the ValidationMode is LostFocus, the validation take place when the control get lost its focus. For KeyPress, the validation triggers for each key press.


### Prompt Character

Displays prompt character for the absence of user input in Mask and its default value is ‘_’

{% tabs %}

{% highlight xaml %}

	<maskededit:SfMaskedEdit  Mask="000000" MaskType="Text" PromptChar="*"/>
	
{% endhighlight %}

{% highlight c# %}

SfMaskedEdit maskededit = new SfMaskedEdit(); 
maskededit.Mask = "000000";
maskededit.MaskType = MaskType.Text;
maskededit.PromptChar = '*'; 
this.Content = maskededit;


{% endhighlight %}

{% endtabs %}
