---
layout: post
title: Popup Events| SfPopupLayout |Xamarin| Syncfusion
description: How to use different events exposed in SfPopupLayout.
platform: Xamarin
control: SfPopupLayout
documentation: ug
--- 

# Events

There are four built-in events in the SfPopupLayout control namely:

* Opening
* Opened
* Closing
* Closed

## Opening event

The [SfPopupLayout.Opening](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~Opening_EV.html) event will be fired whenever opening the Pop-upView in the application. It can cancel pop-up opening with `CancelEventArgs` that contains the following property:

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true): Pop-up opening is based on this value.

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

## Opened event

The [SfPopupLayout.Opened](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~Opened_EV.html) event will be fired whenever displaying the Pop-upView in the application.

You can execute your own set of codes once the pop-up is opened, and visible in the application in its respective event handler.

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

## Closing event

The [SfPopupLayout.Closing](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~Opening_EV.html) event will be fired whenever closing the Pop-upView in the application. It can cancel pop-up closing with `CancelEventArgs` that contains the following property:

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true): Pop-up opening is based on this value.

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

## Closed event

The [SfPopupLayout.Closed](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~Closed_EV.html) event will be fired whenever dismissing the Pop-upView from the view.

You can execute your own set of codes once the pop-up is completely closed in its respective event handler.

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
    // Codes that needs to be executed once popup is completely closed.
}
{% endhighlight %}
{% endtabs %}

## Footer button commands

Following two commands are available in the footer:

* AcceptCommand
* DeclineCommand

### Accept command

The [SfPopupLayout.PopupView.AcceptCommand](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~AcceptCommand.html) will be fired when clicking the Accept button in the pop-up footer.

To handle the Accept button, follow the procedure:

* Derive a class from `ICommand`, and implement the necessary interface.
* Return true in the `CanExecute()` override method to close the pop-up, and fire the `Execute()` method.
* Return false to prevent pop-up from closing, and `Execute()` method is not fired.

{% tabs %}

{% highlight xaml %}

<sfPopup:SfPopupLayout x:Name="popUpLayout">
    <sfPopup:SfPopupLayout.PopupView>
        <sfPopup:PopupView AppearanceMode="TwoButton" />
    </sfPopup:SfPopupLayout.PopupView>
</sfPopup:SfPopupLayout>

{% endhighlight %}

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

{% endtabs %}

{% tabs %}

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

{% endtabs %}

### Decline command

The [SfPopupLayout.PopupView.DeclineCommand](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~DeclineCommand.html) will be fired when clicking the Decline button in the pop-up footer. 

To handle the Decline button, follow the procedure:

* Derive a class from `ICommand`, and implement the necessary interface. 
* Return true in the `CanExecute()` override method to close the pop-up, and fire the `Execute()` method. 
* Return false to prevent pop-up from closing, and `Execute()` method is not fired.

{% tabs %}

{% highlight xaml %}

<sfPopup:SfPopupLayout x:Name="popUpLayout">
    <sfPopup:SfPopupLayout.PopupView>
        <sfPopup:PopupView AppearanceMode="TwoButton" />
    </sfPopup:SfPopupLayout.PopupView>
</sfPopup:SfPopupLayout>

{% endhighlight %}

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

{% endtabs %}

{% tabs %}

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

{% endtabs %}
