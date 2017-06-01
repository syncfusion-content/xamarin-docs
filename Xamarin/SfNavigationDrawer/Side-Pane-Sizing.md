---
layout: post
title: Sizing of drawer in Syncfusion NavigationDrawer control for Xamarin.Forms
description: Learn how to set ReSize the DrawerView panel.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---
# Side Pane Sizing

The size of side pane can be adjusted using `DrawerHeight` and `DrawerWidth` properties.

## Drawer Height

`DrawerHeight` property is used to change the height of side pane when the Position is Top or Bottom.

{% tabs %}

{% highlight xaml %}

<navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" DrawerHeight="40" Position=”Top”>       
        <navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
            <Label Text="This is a very short content used to demonstrate the DrawerHeight property "/>            
        </navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
</navigationdrawer:SfNavigationDrawer>
	
{% endhighlight %}	
	
{% highlight c# %} 


Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer navigationDrawer = new Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer();

navigationDrawer.Position = Position.Top;

navigationDrawer.DrawerHeight = 40;

navigationDrawer.DrawerHeaderView = new Label()

{

    Text = "This is a very short content used to demonstrate the DrawerHeight property"

};

Content = navigationDrawer;



{% endhighlight %}

{% endtabs %}

## Drawer Width

`DrawerWidth` property is used to change the width of side pane when the Position is Left or Right.

{% tabs %}

{% highlight xaml %}

<navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" DrawerWidth="200" Position=”Left”>       
	<navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
		<Label Text="This is a very long text used to demonstrate the DrawerWidth property"/>            
	</navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
</navigationdrawer:SfNavigationDrawer>
	
{% endhighlight %}	
	
{% highlight c# %} 

Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer navigationDrawer = new Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer();

navigationDrawer.Position = Position.Left;

navigationDrawer.DrawerWidth = 200;

navigationDrawer.DrawerHeaderView = new Label()

{

	Text = "This is a very long text used to demonstrate the DrawerWidth property"

};

Content = navigationDrawer;


{% endhighlight %}

{% endtabs %}