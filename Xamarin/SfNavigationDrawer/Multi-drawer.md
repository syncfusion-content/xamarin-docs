---
layout: post
title: Multi drawer support of Syncfusion NavigationDrawer control for Xamarin.Forms
description: Learn how to set multi drawer view in NavigationDrawer.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---


# Multi drawer

The navigation drawer allows the user to provide the multi drawer contents and each of them can be opened with their opening methods.

*	Default drawer settings

*	Secondary drawer settings

N> Header and Footer content are optional but Drawer content is mandatory to allocate space for the drawer.
		
## Default drawer settings

The user can provided the default drawer contents inside default drawer settings. The below code illustrates the code for default drawer settings.

{% tabs %}

{% highlight xaml %}

    <navigationdrawer:SfNavigationDrawer.DefaultDrawerSettings >
    <navigationdrawer:DrawerSettings
        DrawerWidth="150"
        DrawerHeight="150"
        Transition ="SlideOnTop"
        DrawerHeaderHeight="150"
        DrawerFooterHeight="150"
        Position="Left">
    </navigationdrawer:DrawerSettings>
    </navigationdrawer:SfNavigationDrawer.DefaultDrawerSettings>


{% endhighlight %}

{% highlight c# %}

DrawerSettings defaultDrawerSettings = new DrawerSettings();
defaultDrawerSettings.DrawerHeight = 150;
defaultDrawerSettings.Position = Position.Left;
defaultDrawerSettings.Transition = Transition.SlideOnTop;
defaultDrawerSettings.DrawerWidth = 150;
navigationDrawer.DrawerHeaderHeight = 150;
navigationDrawer.DrawerFooterHeight = 150;
navigationDrawer.DefaultDrawerSettings = defaultDrawerSettings;
  
{% endhighlight %}

{% endtabs %}

### Default drawer Header view

The header view of the default drawer can be provided using the below codes. 

{% tabs %}

{% highlight xaml %}
    <Grid BackgroundColor="#1aa1d6">
    <Grid.RowDefinitions>
    <RowDefinition Height="120"/>
    </Grid.RowDefinitions>
    <navigationdrawer:DrawerSettings.DrawerHeaderView>
        <Label Text="Syncfusion Xamarin Products"  HorizontalTextAlignment="Center" HorizontalOptions="Center" FontSize="20" TextColor="White"/>
     </Grid>
    </navigationdrawer:DrawerSettings.DrawerHeaderView>


{% endhighlight %}

{% highlight c# %}

    Grid headerLayout = new Grid();
    headerLayout.BackgroundColor = Color.FromHex("#1aa1d6");
    Label header = new Label();
    header.Text = "Syncfusion Xamarin Products";
    header.FontSize = 20;
    header.TextColor = Color.White;
    header.HorizontalTextAlignment = TextAlignment.Center;
    headerLayout.Children.Add(header);
    defaultDrawerSettings.DrawerHeaderView = headerLayout;

{% endhighlight %}

{% endtabs %}      

### Default drawer Content view

The drawer content view of the default drawer can be provided using the below codes. 

{% tabs %}

{% highlight xaml %}

<navigationdrawer:SfNavigationDrawer.DefaultDrawerSettings>
<navigationdrawer:DrawerSettings>
<navigationdrawer:DrawerSettings.DrawerContentView>
    <Label Text="DrawerContent "  HorizontalTextAlignment="Center" HorizontalOptions="Center" FontSize="20" TextColor="White"/>
</navigationdrawer:DrawerSettings.DrawerContentView>
</navigationdrawer:DrawerSettings>   
</navigationdrawer:SfNavigationDrawer.DefaultDrawerSettings>
      
{% endhighlight %}
{% highlight c# %}

Grid contentLayout = new Grid();
contentLayout.BackgroundColor = Color.FromHex("#1aa1d6");
Label content = new Label();
content.Text = "DrawerContent";
content.FontSize = 20;
content.TextColor = Color.White;
content.HorizontalTextAlignment = TextAlignment.Center;
contentLayout.Children.Add(content);
defaultDrawerSettings.DrawerContentView = contentLayout;

{% endhighlight %}

{% endtabs %}   

### Default drawer Footer view

The footer view of the default drawer can be provided using the below codes. 

{% tabs %}

{% highlight xaml %}
    
    <navigationdrawer:DrawerSettings.DrawerFooterView>
    <Grid BackgroundColor="#1aa1d6">
    <Grid.RowDefinitions>
    <RowDefinition Height="120"/>
    </Grid.RowDefinitions>
        <Label Text="Close" Grid.Row="0" HorizontalTextAlignment="Center" HorizontalOptions="Center" FontSize="20" TextColor="White"/>
    </Grid>
    </navigationdrawer:DrawerSettings.DrawerFooterView>


{% endhighlight %}

{% highlight c# %}

Grid footerLayout = new Grid();
footerLayout.BackgroundColor = Color.FromHex("#1aa1d6");
Label footer = new Label();
footer.Text = "Close";
footer.FontSize = 20;
footer.TextColor = Color.White;
footer.HorizontalTextAlignment = TextAlignment.Center;
footerLayout.Children.Add(footer);
defaultDrawerSettings.DrawerFooterView = footerLayout;
{% endhighlight %}

{% endtabs %}   

## Secondary drawer settings   

The user can provided the secondary drawer contents inside secondary drawer settings. The below code illustrates the code for secondary drawer settings.

{% tabs %}

{% highlight xaml %}

    <navigationdrawer:SfNavigationDrawer.SecondaryDrawerSettings >
    <navigationdrawer:DrawerSettings x:Name="secondaryDrawer"
    DrawerHeaderHeight="40"
    DrawerFooterHeight="40"
    DrawerHeight="300"
    DrawerWidth= 150;
    Duration="400" 
    Position="Right"
    Transition="SlideOnTop">
    </navigationdrawer:SfNavigationDrawer.SecondaryDrawerSettings>
               
{% endhighlight %}

{% highlight c# %}

DrawerSettings secondaryDrawer = new DrawerSettings();
secondaryDrawer.DrawerHeight = 300;
secondaryDrawer.Position = Position.Right;
secondaryDrawer.Transition = Transition.SlideOnTop;
secondaryDrawer.DrawerWidth = 150;
secondaryDrawer.DrawerHeaderHeight = 40;
secondaryDrawer.DrawerFooterHeight = 40;
navigationDrawer.SecondaryDrawerSettings = secondaryDrawer;

  
{% endhighlight %}

{% endtabs %}

### Secondary drawer Header view

The header view of the secondary drawer can be provided using the below codes. 

{% tabs %}

{% highlight xaml %}
    
    <navigationdrawer:DrawerSettings.DrawerHeaderView>
    <Grid BackgroundColor="#1aa1d6">
    <Grid.RowDefinitions>
    <RowDefinition Height="120"/>
    </Grid.RowDefinitions>
        <Label Text="Syncfusion Enterprise solution" Grid.Row="0" HorizontalTextAlignment="Center" HorizontalOptions="Center" FontSize="20" TextColor="White"/>
    </Grid>
    </navigationdrawer:DrawerSettings.DrawerHeaderView>

{% endhighlight %}

{% highlight c# %}

Grid secondary = new Grid();
secondary.BackgroundColor = Color.FromHex("#1aa1d6");
Label header = new Label();
header.Text = "Syncfusion Enterprise solution";
header.FontSize = 20;
header.TextColor = Color.White;
header.HorizontalTextAlignment = TextAlignment.Center;
secondary.Children.Add(header);
secondaryDrawer.DrawerHeaderView = secondary;

{% endhighlight %}

{% endtabs %}      

### Secondary drawer Content view

The drawer content view of the secondary drawer can be provided using the below codes. 

{% tabs %}

{% highlight xaml %}

<navigationdrawer:SfNavigationDrawer.SecondaryDrawerSettings>
<navigationdrawer:DrawerSettings>
<navigationdrawer:DrawerSettings.DrawerContentView>
    <Label Text="DrawerContent "  HorizontalTextAlignment="Center" HorizontalOptions="Center" FontSize="20" TextColor="White"/>
</navigationdrawer:DrawerSettings.DrawerContentView>
</navigationdrawer:DrawerSettings>   
</navigationdrawer:SfNavigationDrawer.SecondaryDrawerSettings>
      
      
{% endhighlight %}

{% highlight c# %}

Grid Layout = new Grid();
Layout.BackgroundColor = Color.FromHex("#1aa1d6");
Label content = new Label();
content.Text = "DrawerContent";
content.FontSize = 20;
content.TextColor = Color.White;
content.HorizontalTextAlignment = TextAlignment.Center;
Layout.Children.Add(content);
secondaryDrawer.DrawerContentView = Layout;

{% endhighlight %}

{% endtabs %}   

### Secondary drawer Footer view

The footer view of the secondary drawer can be provided using the below codes. 

{% tabs %}

{% highlight xaml %}
    
    <navigationdrawer:DrawerSettings.DrawerFooterView>
    <Grid BackgroundColor="#1aa1d6">
    <Grid.RowDefinitions>
    <RowDefinition Height="120"/>
    </Grid.RowDefinitions>
        <Label Text="Close" Grid.Row="0" HorizontalTextAlignment="Center" HorizontalOptions="Center" FontSize="20" TextColor="White"/>
    </Grid>
    </navigationdrawer:DrawerSettings.DrawerFooterView>

{% endhighlight %}

{% highlight c# %}

Grid Layout = new Grid();
Layout.BackgroundColor = Color.FromHex("#1aa1d6");
Label footer = new Label();
footer.Text = "Close";
footer.FontSize = 20;
footer.TextColor = Color.White;
footer.HorizontalTextAlignment = TextAlignment.Center;
Layout.Children.Add(footer);
secondaryDrawer.DrawerFooterView = Layout;

{% endhighlight %}

{% endtabs %}   

Note: The sample implemnting multi drawer can be downloaded from this [link](http://www.syncfusion.com/downloads/support/directtrac/general/ze/NavigationDrawerSample_2-228312513)

