---
layout: post
title: Accessibility in Xamarin Text Input Layout control | Syncfusion
description: Learn here all about Accessibility support in Syncfusion Xamarin Text Input Layout (SfTextInputLayout) control and more.
platform: Xamarin
control: SfTextInputLayout
documentation: ug
---

## AutomationId

The text input layout control has built-in AutomationId for inner elements. To keep unique id for inner elements, AutomationId of inner elements are updated based on SfTextInputLayout's AutomationId. For example, if SfTextInputLayout's AutomationId is set as sfTextInputLayout.AutomationId = "textInputLayout", then AutomationId of inner elements will be updated as follows.

<table>
<tr>
 <th>Element</th>
 <th>Element AutomationId</th>
 <th>Qualified AutomationId</th>
</tr>
<tr>
<td>Password Toggle VisibleIcon</td>
<td>show password</td>
<td>textInputLayout show password</td>
</tr>
<tr>
<td>Password Toggle CollapsedIcon</td>
<td>hide password</td>
<td>textInputLayout hide password</td>
</tr>
<tr>
<td>DropDown Button</td>
<td>drop down</td>
<td>textInputLayout drop down</td>
</tr>
</table>

The following code snippet demonstrates how to set the `AutomationId` to SfTextInputLayout.

{% tabs %}

{% highlight xaml %}

<inputLayout:SfTextInputLayout
    Hint="Name"
    EnablePasswordVisibilityToggle="true"
    AutomationId="textInputLayout">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight c# %}

SfTextInputLayout inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.EnablePasswordVisibilityToggle = true;
inputLayout.InputView = new Entry() { Text = "John" };
inputLayout.AutomationId = "textInputLayout";

{% endhighlight %}

{% endtabs %}

Refer to the following code snippet to access the inner elements of SfTextInputLayout from the automation script.

{% tabs %}

{% highlight c# %}

[Test]
[Description("SfTextInputLayout Automation Id")]
public void SfTextInputLayout_AutomationId()
{
   // To tap the Password Toggle VisibleIcon
   App.Tap("textInputLayout show password");

   // To tap the Password Toggle CollapsedIcon
   App.Tap("textInputLayout hide password");
}

{% endhighlight %}

{% endtabs %}