---
layout: post
title: Customizing Font | SfRichTextEditor | Xamarin | Syncfusion
description: Rich Text Editor in Xamarin.Forms provides support to use custom TTF fonts in the Rich Text Editor content.
platform: xamarin
control: SfRichTextEditor
documentation: UG
---

# Font Customization in Xamarin Rich Text Editor(SfRichTextEditor)

The SfRichTextEditor allows you to use TTF fonts in the Rich Text Editor content. The font can be included in the `SfRichTextEditor` using the [`FontButtonCommand`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html#Syncfusion_XForms_RichTextEditor_SfRichTextEditor_FontButtonCommand) property or the [`FontButtonClicked`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html) event.

## FontButtonCommand command

The following code example shows how to include fonts in Rich Text Editor using the `FontButtonCommand` property.

{% tabs %}
{% highlight xaml %} 

<ContentPage.BindingContext>
<ContentPage.BindingContext>
    <local:ViewModel/>
</ContentPage.BindingContext>
<ContentPage.Content>
    <StackLayout>
        <richtexteditor:SfRichTextEditor x:Name="rte" VerticalOptions="FillAndExpand" FontButtonCommand="{Binding FontButtonCommand}"/>
    </StackLayout>
</ContentPage.Content>

{% endhighlight %}

{% highlight c# %}
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
    }
}

/// <summary>
/// Represents a view model class of the application
/// </summary>
public class ViewModel : INotifyPropertyChanged
{
    Stream boogalooFontStream, handleeFontStream, kaushanFontStream, pinyonFontStream;
    /// <summary>
    /// Font button command property to be executed when font button is pressed
    /// </summary>
    public ICommand FontButtonCommand { get; set; }

    public ViewModel()
    {
        Assembly assembly = typeof(MainPage).GetTypeInfo().Assembly;
        boogalooFontStream = assembly.GetManifestResourceStream("Sample.Fonts.Boogaloo.ttf");
        handleeFontStream = assembly.GetManifestResourceStream("Sample.Fonts.Handlee.ttf");
        kaushanFontStream = assembly.GetManifestResourceStream("Sample.Fonts.Kaushan Script.ttf");
        pinyonFontStream = assembly.GetManifestResourceStream("Sample.Fonts.Pinyon Script.ttf");
        FontButtonCommand = new Command<object>(LoadFonts);
    }

    /// <summary>
    /// Load the fonts to the font event args
    /// </summary>
    /// <param name="obj"></param>
    void LoadFonts(object obj)
    {
        FontButtonClickedEventArgs fontEventArgs = (obj as FontButtonClickedEventArgs);
        if (!fontEventArgs.FontStreamCollection.ContainsKey("Boogaloo"))
            fontEventArgs.FontStreamCollection.Add("Boogaloo", boogalooFontStream);
        if (!fontEventArgs.FontStreamCollection.ContainsKey("Handlee"))
            fontEventArgs.FontStreamCollection.Add("Handlee", handleeFontStream);
        if (!fontEventArgs.FontStreamCollection.ContainsKey("Kaushan Script"))
            fontEventArgs.FontStreamCollection.Add("Kaushan Script", kaushanFontStream);
        if (!fontEventArgs.FontStreamCollection.ContainsKey("Pinyon Script"))
            fontEventArgs.FontStreamCollection.Add("Pinyon Script", pinyonFontStream);
    }
    /// <summary>
    ///  Property changed event of the NotifyPropertyChanged interface
    /// </summary>
    public event PropertyChangedEventHandler PropertyChanged;

    /// <summary>
    /// Property changed raise method of the NotifyPropertyChanged interface
    /// </summary>
    /// <param name="propertyname">Property that has been changed</param>
    public void RaisePropertyChange([CallerMemberName] string propertyname = null)
    {
        if (PropertyChanged != null)
        {
            PropertyChanged(this, new PropertyChangedEventArgs(propertyname));
        }
    }
}
{% endhighlight %}
{% endtabs %}

![Rich Text Editor font support using FontButtonCommand](SfRichTextEditor_Images/Font.png)

You can download the sample [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Font_Family-1369712876).

## FontButtonClicked Event

The following code example shows how to include fonts in Rich Text Editor using the `FontButtonClicked` event.

{% tabs %} 

{% highlight xaml %} 
<ContentPage.Content>
    <StackLayout>
        <richtexteditor:SfRichTextEditor x:Name="rte" VerticalOptions="FillAndExpand" FontButtonClicked="rte_FontButtonClicked"/>
    </StackLayout>
</ContentPage.Content>
{% endhighlight %}

{% highlight C# %} 
public partial class MainPage : ContentPage
{
    Stream boogalooFontStream, handleeFontStream, kaushanFontStream, pinyonFontStream;
    public MainPage()
    {
        InitializeComponent();
        Assembly assembly = typeof(MainPage).GetTypeInfo().Assembly;
        boogalooFontStream = assembly.GetManifestResourceStream("Sample.Fonts.Boogaloo.ttf");
        handleeFontStream = assembly.GetManifestResourceStream("Sample.Fonts.Handlee.ttf");
        kaushanFontStream = assembly.GetManifestResourceStream("Sample.Fonts.Kaushan Script.ttf");
        pinyonFontStream = assembly.GetManifestResourceStream("Sample.Fonts.Pinyon Script.ttf");
    }

    private void rte_FontButtonClicked(object sender, FontButtonClickedEventArgs e)
    {
        if (!e.FontStreamCollection.ContainsKey("Boogaloo"))
            e.FontStreamCollection.Add("Boogaloo", boogalooFontStream);
        if (!e.FontStreamCollection.ContainsKey("Handlee"))
            e.FontStreamCollection.Add("Handlee", handleeFontStream);
        if (!e.FontStreamCollection.ContainsKey("Kaushan Script"))
            e.FontStreamCollection.Add("Kaushan Script", kaushanFontStream);
        if (!e.FontStreamCollection.ContainsKey("Pinyon Script"))
            e.FontStreamCollection.Add("Pinyon Script", pinyonFontStream);
    }
}
{% endhighlight %}
{% endtabs %}

## DefaultFont

The SfRichTextEditor provides support to modify the default font used in the Rich text editor control. The default font of the Rich Text Editor can be changed using the [`DefaultFont`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.RichTextEditor.SfRichTextEditor.html#Syncfusion_XForms_RichTextEditor_SfRichTextEditor_DefaultFont) property.

N> The DefaultFont property accepts fonts as Embedded source, System Font Name, or Base64 TTF string.

{% tabs %} 

{% highlight xaml %} 

<ContentPage.Content>
    <StackLayout>
        <richtexteditor:SfRichTextEditor x:Name="rte" DefaultFont="monospace" VerticalOptions="FillAndExpand"/>
    </StackLayout>
</ContentPage.Content>
 
{% endhighlight %}

{% highlight C# %} 
richtexteditor = new SfRichTextEditor()
{
    VerticalOptions = LayoutOptions.FillAndExpand,
    DefaultFont = "monospace"
};
this.Content = richtexteditor;
{% endhighlight %}
{% endtabs %}

## DefaultFontSize

The SfRichTextEditor provides support to modify the default font size used in the Rich text editor control.The default font size of the Rich Text Editor can be changed using the DefaultFontSize property.

{% tabs %} 

{% highlight xaml %} 

<ContentPage.Content>
    <StackLayout>
        <richtexteditor:SfRichTextEditor x:Name="rte" DefaultFontSize="20" VerticalOptions="FillAndExpand"/>
    </StackLayout>
</ContentPage.Content>
 
{% endhighlight %}

{% highlight C# %} 
richtexteditor = new SfRichTextEditor()
{
    VerticalOptions = LayoutOptions.FillAndExpand,
    DefaultFontSize = "20"
};
this.Content = richtexteditor;
{% endhighlight %}
{% endtabs %}

## DefaultFontColor

The SfRichTextEditor provides support to modify the default font color used in the Rich text editor control.The default font color of the Rich Text Editor can be changed using the DefaultFontColor property.

{% tabs %} 

{% highlight xaml %} 

<ContentPage.Content>
    <StackLayout>
        <richtexteditor:SfRichTextEditor x:Name="rte" DefaultFontColor="Blue" VerticalOptions="FillAndExpand"/>
    </StackLayout>
</ContentPage.Content>
 
{% endhighlight %}

{% highlight C# %} 
richtexteditor = new SfRichTextEditor()
{
    VerticalOptions = LayoutOptions.FillAndExpand,
    DefaultFontColor = "Blue"
};
this.Content = richtexteditor;
{% endhighlight %}
{% endtabs %}