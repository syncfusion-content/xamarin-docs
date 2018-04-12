---
layout: post
title: Popup Events| SfPopupLayout |Xamarin| Syncfusion
description: How to use different events exposed in SfPopupLayout.
platform: Xamarin
control: SfPopupLayout
documentation: ug
--- 

# Events

There are four built-in events in the SfPopupLayout control namely,

* Opening
* Opened
* Closing
* Closed

## Opening Event

[SfPopupLayout.Opening](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~Opening_EV.html) event will be fired whenever the PopupView is opening in the application. It provides support to cancel the opening of the popup with `CancelEventArgs` that contains the following property.

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true) - Based on this value, you can cancel the popup opening.

Refer to the following code example in which the pop-up will be canceled in `SfPopupLayout.Opening` event.

{% tabs %}
{%highlight Xaml%}
<sfPopup:SfPopupLayout x:Name="popupLayout" Opening="PopupLayout_Opening"/>
{%endhighlight%}

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.Opening += PopupLayout_Opening;
    ....
}

private void PopupLayout_Opening(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

## Opened Event

[SfPopupLayout.Opened](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~Opened_EV.html) event will be fired whenever the PopupView is displayed in the application.
You can write your set of codes that needs to be executed once the popup is opened and visible in the application, in its respective event handler.

Refer to the following code example for using `SfPopupLayout.Opened` event.

{% tabs %}
{%highlight Xaml%}
<sfPopup:SfPopupLayout x:Name="popupLayout" Opened="PopupLayout_Opened"/>
{%endhighlight%}

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.Opened += PopupLayout_Opened;
    ....
}

private void PopupLayout_Opened(object sender, EventArgs e)
{
   // Codes that needs to be executed once popup is visible in the screen.
}
{% endhighlight %}
{% endtabs %}

## Closing Event

[SfPopupLayout.Closing](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~Opening_EV.html) event will be fired whenever the PopupView is about to be closed in the application. It provides support to cancel closing of the popup with `CancelEventArgs` that contains the following property.

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true) - Based on this value, you can cancel the popup closing.

Refer to the following code example in which the closing of the pop-up will be canceled in `SfPopupLayout.Closing` event.

{% tabs %}
{%highlight Xaml%}
<sfPopup:SfPopupLayout x:Name="popupLayout"  Closing="PopupLayout_Closing"/>
{%endhighlight%}

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.Closing += PopupLayout_Closing;
    ....
}

private void PopupLayout_Closing(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

## Closed Event

[SfPopupLayout.Closed](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~Closed_EV.html) event will be fired whenever the PopupView is dismissed from the view.
You can write your set of codes that needs to be executed once the popup is completely closed, in its respective event handler.

Refer to the following code example for using `SfPopupLayout.Closed` event.

{% tabs %}
{%highlight Xaml%}
<sfPopup:SfPopupLayout x:Name="popupLayout" Closed="PopupLayout_Closed"/>
{%endhighlight%}

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.Closed += PopupLayout_Closed;
    ....
}

private void PopupLayout_Closed(object sender, EventArgs e)
{
    // Codes that needs to be executed once popup is completly closed.
}
{% endhighlight %}
{% endtabs %}

## Footer Button Commands

Following are the two commands available in the Footer.

* AcceptCommand
* DeclineCommand

### Accept Command

[SfPopupLayout.PopupView.AcceptCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~AcceptCommand.html) will be fired when the accept button in the footer of the popup is clicked.

Derive a class from `ICommand` and implement the necessary interface.
Return true in the `CanExecute()` override method to close the popup and fire the `Execute()` method.
Return false to prevent popup from closing and `Execute()` method is not fired.

Refer to the following code example in which the pop-up closing will be canceled based on the return value of `CanExecute()` method.

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.AppearanceMode = AppearanceMode.TwoButton;
    popupLayout.PopupView.AcceptCommand = new AcceptButtonCustomCommand();
    ....
}
{% endhighlight %}

{% highlight c# %}
//Accept Button Event handler

public class AcceptButtonCustomCommand : ICommand
{
    public event EventHandler CanExecuteChanged;

    public bool CanExecute(object parameter)
    {
        return false;
    }

    public void Execute(object parameter)
    {
      // You can write your set of codes that needs to be executed
    }
}
{% endhighlight %}

### Decline Command

[SfPopupLayout.PopupView.DeclineCommand](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~DeclineCommand.html) will be fired when the decline button in the footer of the popup is clicked. 

Derive a class from `ICommand` and implement the necessary interface. 
Return true in the `CanExecute()` override method to close the popup and fire the `Execute()` method. 
Return false to prevent popup from closing and `Execute()` method is not fired.

Refer to the following code example in which the pop-up closing will be canceled based on the return value of `CanExecute()` method.

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.AppearanceMode = AppearanceMode.TwoButton;
    popupLayout.PopupView.DeclineCommand = new DeclineButtonCustomCommand();
    ....
}
{% endhighlight %}

{% highlight c# %}
//Decline Button Event handler

public class DeclineButtonCustomCommand : ICommand
{
    public event EventHandler CanExecuteChanged;

    public bool CanExecute(object parameter)
    {
        return false;
    }

    public void Execute(object parameter)
    {
       // You can write your set of codes that needs to be executed
    }
}
{% endhighlight %}