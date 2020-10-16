---
layout: post
title: Return key types and command support in Syncfusion NumericTextBox.
description: This section describes how to customise the retun key and set command for return key in NumericTextBox
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Return Type in Xamarin Numeric Entry (SfNumericTextBox)

We can able to define the return key type of NumericTextBox by using the `ReturnType` property of the type [Xamarin.Forms ReturnType](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.entry.returntype?view=xamarin-forms).

{% tabs %}

{% highlight xaml %}

<syncfusion:SfNumericTextBox x:Name="numericTextBox" ReturnType= "Next" Value="123" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox = new SfNumericTextBox();
numericTextBox.ReturnType = ReturnType.Next;
numericTextBox.Value = 123;

{% endhighlight %}

{% endtabs %}

N> Default value of `ReturnType` is `Default`.

## Return Command

The `ReturnCommand` property defines an [`ICommand`](https://docs.microsoft.com/en-us/dotnet/api/system.windows.input.icommand?view=netframework-4.8) implementation that wraps an action when the user presses return button.

## Return Command Parameter

The `ReturnCommandParameter` property is used to set the parameter that is sent to the `ReturnCommand`.

{% tabs %}

{% highlight xaml %}

<ContentPage.BindingContext>
    <local:ViewModel />
 </ContentPage.BindingContext>

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" ReturnType="Next" Value="123" ReturnCommand="{Binding CommandProperty}" />
	
{% endhighlight %}

{% highlight c# %}

  public class ViewModel : INotifyPropertyChanged
    {
        public event PropertyChangedEventHandler PropertyChanged = delegate { };
        public ICommand CommandProperty { protected set; get; }
        public ViewModel()
        {
            CommandProperty = new Command(
                execute: () =>
                {
                    OnSubmit();
                },
                canExecute: () =>
                {
                    return true;
                });
        }
        
        private void OnSubmit()
        {

        }
    }

{% endhighlight %}

{% endtabs %}

## See also

[How to get the localized return key on the iOS keyboard in SfNumericTextBox](https://www.syncfusion.com/kb/11630/how-to-get-the-localized-return-key-on-the-ios-keyboard-in-xamarin-forms-numeric-controls)
