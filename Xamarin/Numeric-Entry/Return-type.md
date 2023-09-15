---
layout: post
title: Return Type in Xamarin Numeric Entry control | Syncfusion
description: Learn here all about Return Type support in Syncfusion Xamarin Numeric Entry (SfNumericTextBox) control and more.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Return Type in Xamarin Numeric Entry (SfNumericTextBox)

You can define the return key type of [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) by using the [`ReturnType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_ReturnType) property of the type [Xamarin.Forms ReturnType](https://learn.microsoft.com/en-us/dotnet/api/xamarin.forms.entry.returntype?view=xamarin-forms).

{% tabs %}

{% highlight xaml %}

<syncfusion:SfNumericTextBox ReturnType= "Next" Value="123" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox = new SfNumericTextBox();
numericTextBox.ReturnType = ReturnType.Next;
numericTextBox.Value = 123;

{% endhighlight %}

{% endtabs %}

N> Default value of ReturnType is `Default`.

![Xamarin.Forms Numeric TextBox with return type](images/retureType.PNG)

## Return Command

The [`ReturnCommand`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_ReturnCommand) property defines an [`ICommand`](https://learn.microsoft.com/en-us/dotnet/api/system.windows.input.icommand?view=netframework-4.8) implementation that wraps an action when the user presses return button.

## Return Command Parameter

The [`ReturnCommandParameter`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_ReturnCommandParameter) property is used to set the parameter that is sent to the [`ReturnCommand`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_ReturnCommand).

{% tabs %}

{% highlight xaml %}

  <ContentPage.BindingContext>
    <local:ViewModel />
 </ContentPage.BindingContext>

	<syncfusion:SfNumericTextBox x:Name="NumericTextBox"
                             ReturnType="Next"
                             Value="123"
                             ReturnCommand="{Binding CommandProperty}"
                             ReturnCommandParameter="{x:Reference NumericTextBox}"/>
                             	
{% endhighlight %}

{% highlight c# %}

  public class ViewModel : INotifyPropertyChanged
    {
        public event PropertyChangedEventHandler PropertyChanged = delegate { };
        public ICommand CommandProperty { protected set; get; }
        public ViewModel()
        {
            CommandProperty = new Command(ReturnButtonClicked);
        }
        
        private void ReturnButtonClicked(object obj)
        {
            var numericTextBox = obj as SfNumericTextBox;
        }
    }

{% endhighlight %}

{% endtabs %}

## See also

[How to get the localized return key on the iOS keyboard in SfNumericTextBox](https://support.syncfusion.com/kb/article/10234/how-to-get-the-localized-return-key-on-the-ios-keyboard-in-xamarin-forms-numeric-controls)
