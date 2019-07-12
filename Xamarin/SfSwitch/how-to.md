---
layout: post
title: States in Syncfusion Switch control for Xamarin.Forms.
description: Explaining about states in SfSwitch.
platform: Xamarin
control: Switch
documentation: ug
---

# How to

## Show busy indicator to perform async action

The busy indicator indicates users that something is on progress in the background. For instance, some data is being fetched from the back end. Here, when users about to switch the state, the StateChanging event occurs, and users can set the `IsBusy` property to true to show busy indicator and perform fetching the data from the server. After fetching the data, the `IsOn` property will be set to true or false based on validation. After validation, the `IsBusy` property is set to false.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch x:Name="sfSwitch" StateChanging="State_StateChanging"/>
        
{% endhighlight %}

{% highlight c# %}

 SfSwitch sfSwitch = new SfSwitch();

 sfSwitch.StateChanged += State_StateChanging;

{% endhighlight %}

{% endtabs %}

{% highlight c# %}

    private async void State_StateChanging(object sender, SwitchStateChangingEventArgs e)
        {
            this.sfSwitch.IsBusy = true;
            await Task.Delay(2500);
            this.sfSwitch.IsOn = ValidateInternetConnection();
            this.sfSwitch.IsBusy = false;
        }

        private bool ValidateInternetConnection()
        {
            Random randomValue = new Random();
            if (randomValue.Next() % 2 == 0)
            {
                return false;
            }
            return true;
        }
        
{% endhighlight %}

![switch control with busy indicator](images/busy-indicator.png)

## Change thumb color alone based on its state and devices

You can customize the thumb color using the `ThumbColor` property based on its visual state and devices.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch  VisualType="Custom">

        <VisualStateManager.VisualStateGroups>

            <VisualStateGroup x:Name="CommonStates">

                <VisualState x:Name="On">

                    <VisualState.Setters>

                        <Setter Property="SwitchSettings">

                            <Setter.Value>

                                <syncfusion:FluentSwitchSettings x:TypeArguments="syncfusion:OnState"

                                 ThumbColor="Green"/>

                            </Setter.Value>

                        </Setter>

                    </VisualState.Setters>

                </VisualState>

                <VisualState x:Name="Off">

                    <VisualState.Setters>

                        <Setter Property="SwitchSettings">

                            <Setter.Value>

                                <syncfusion:FluentSwitchSettings x:TypeArguments="syncfusion:OffState"

                                 ThumbColor="Green"/>

                            </Setter.Value>

                        </Setter>

                    </VisualState.Setters>

                </VisualState>

            </VisualStateGroup>

        </VisualStateManager.VisualStateGroups>

    </syncfusion:SfSwitch>

{% endhighlight %}

{% highlight c# %}

            SfSwitch sfSwitch = new SfSwitch();
            sfSwitch.VisualType = VisualType.Custom;

            DefaultSwitchSettings<OnState> defaultSwitch = new DefaultSwitchSettings<OnState>();
            defaultSwitch.ThumbColor = Color.Green;
           
            DefaultSwitchSettings<OffState> defaultSwitch1 = new DefaultSwitchSettings<OffState>();
            defaultSwitch1.ThumbColor = Color.Green;

            VisualStateGroupList visualStateGroupList = new VisualStateGroupList();

            VisualStateGroup commonStateGroup = new VisualStateGroup();
            VisualState onState = new VisualState
            {
                Name = "On"
            };
            onState.Setters.Add(new Setter { Property = SfSwitch.SwitchSettingsProperty, Value = defaultSwitch });

            VisualState offState = new VisualState
            {
                Name = "Off"
            };

            offState.Setters.Add(new Setter { Property = SfSwitch.SwitchSettingsProperty, Value = defaultSwitch1 });

            commonStateGroup.States.Add(onState);
            commonStateGroup.States.Add(offState);
            visualStateGroupList.Add(commonStateGroup);

            VisualStateManager.SetVisualStateGroups(sfSwitch, visualStateGroupList);

            this.Content = sfSwitch;

{% endhighlight %}

{% endtabs %}

![switch control with busy indicator](images/thumb-color.png)

## Change thumb color alone based on its state with Material theme for all devices

By using the `MaterialSwitchSettings`, `CupertinoSwitchSettings`, and `FluentSwitchSettings` properties, you can change the thumb color based on its state for all devices.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch  VisualType="Custom">

        <VisualStateManager.VisualStateGroups>

            <VisualStateGroup x:Name="CommonStates">

                <VisualState x:Name="On">

                    <VisualState.Setters>

                        <Setter Property="SwitchSettings">

                            <Setter.Value>

                                <syncfusion:MaterialSwitchSettings x:TypeArguments="syncfusion:OnState"

                                 ThumbColor="Brown"/>

                            </Setter.Value>

                        </Setter>

                    </VisualState.Setters>

                </VisualState>

                <VisualState x:Name="Off">

                    <VisualState.Setters>

                        <Setter Property="SwitchSettings">

                            <Setter.Value>

                                <syncfusion:MaterialSwitchSettings x:TypeArguments="syncfusion:OffState"

                                 ThumbColor="Brown"/>

                            </Setter.Value>

                        </Setter>

                    </VisualState.Setters>

                </VisualState>

            </VisualStateGroup>

        </VisualStateManager.VisualStateGroups>

    </syncfusion:SfSwitch>

{% endhighlight %}

{% highlight c# %}

            SfSwitch sfSwitch = new SfSwitch();
            sfSwitch.VisualType = VisualType.Custom;

            MaterialSwitchSettings<OnState> defaultSwitch = new MaterialSwitchSettings<OnState>();
            defaultSwitch.ThumbColor = Color.Brown;

            MaterialSwitchSettings<OffState> defaultSwitch1 = new MaterialSwitchSettings<OffState>();
            defaultSwitch1.ThumbColor = Color.Brown;

            VisualStateGroupList visualStateGroupList = new VisualStateGroupList();

            VisualStateGroup commonStateGroup = new VisualStateGroup();
            VisualState onState = new VisualState
            {
                Name = "On"
            };
            onState.Setters.Add(new Setter { Property = SfSwitch.SwitchSettingsProperty, Value = defaultSwitch });

            VisualState offState = new VisualState
            {
                Name = "Off"
            };

            offState.Setters.Add(new Setter { Property = SfSwitch.SwitchSettingsProperty, Value = defaultSwitch1 });

            commonStateGroup.States.Add(onState);
            commonStateGroup.States.Add(offState);
            visualStateGroupList.Add(commonStateGroup);

            VisualStateManager.SetVisualStateGroups(sfSwitch, visualStateGroupList);

            this.Content = sfSwitch;

{% endhighlight %}

{% endtabs %}

![switch conrol with thumb color](images/thumb-color-based-on-device.png)

## Set color for disabled state

The Switch control provides options to customize the color based on the disabled states. The below code example illustrates this customization.

{% tabs %}

{% highlight xaml %}

     <syncfusion:SfSwitch  VisualType="Custom" IsEnabled="False"  IsOn="True">

        <VisualStateManager.VisualStateGroups>
            <VisualStateGroup  x:Name="CommonStates">
                <VisualState x:Name="DisabledOn">
                    <VisualState.Setters>
                        <Setter Property="SwitchSettings">
                            <Setter.Value>
                                <syncfusion:DefaultSwitchSettings  x:TypeArguments="syncfusion:DisabledOnState" 
                                ThumbBorderColor="Red" ThumbColor="Green" 
                                 TrackBorderColor="LightGreen" TrackColor="OrangeRed" 
                                 BusyIndicatorColor="Pink">
                                </syncfusion:DefaultSwitchSettings>
                            </Setter.Value>
                        </Setter>
                    </VisualState.Setters>
                </VisualState>

                <VisualState x:Name="DisabledOff">
                    <VisualState.Setters>
                        <Setter Property="SwitchSettings">
                            <Setter.Value>
                                <syncfusion:DefaultSwitchSettings x:TypeArguments="syncfusion:DisabledOffState" 
                                   ThumbBorderColor="Red" ThumbColor="Green" 
                                 TrackBorderColor="LightGreen" TrackColor="OrangeRed" 
                                 />
                            </Setter.Value>
                        </Setter>
                    </VisualState.Setters>
                </VisualState>
            </VisualStateGroup>

        </VisualStateManager.VisualStateGroups>
    </syncfusion:SfSwitch>

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();
sfSwitch.VisualType = VisualType.Custom;
sfSwitch.IsOn = true;
sfSwitch.IsEnabled = false;

DefaultSwitchSettings<DisabledOnState> defaultSwitch = new DefaultSwitchSettings<DisabledOnState>();
defaultSwitch.ThumbBorderColor = Color.Red;
defaultSwitch.ThumbColor = Color.Green;
defaultSwitch.TrackBorderColor = Color.LightGreen;
defaultSwitch.TrackColor = Color.OrangeRed;
defaultSwitch.BusyIndicatorColor = Color.Pink;

DefaultSwitchSettings<DisabledOffState> defaultSwitch1 = new DefaultSwitchSettings<DisabledOffState>();
defaultSwitch1.ThumbBorderColor = Color.Red;
defaultSwitch1.ThumbColor = Color.Green;
defaultSwitch1.TrackBorderColor = Color.LightGreen;
defaultSwitch1.TrackColor = Color.OrangeRed;

VisualStateGroupList visualStateGroupList = new VisualStateGroupList();

VisualStateGroup commonStateGroup = new VisualStateGroup();
VisualState onState = new VisualState
{
Name = "DisabledOn"
};
onState.Setters.Add(new Setter { Property = SfSwitch.SwitchSettingsProperty, Value = defaultSwitch });

VisualState offState = new VisualState
{
Name = "DisabledOff"
};

offState.Setters.Add(new Setter { Property = SfSwitch.SwitchSettingsProperty, Value = defaultSwitch1 });

commonStateGroup.States.Add(onState);

commonStateGroup.States.Add(offState);

visualStateGroupList.Add(commonStateGroup);

VisualStateManager.SetVisualStateGroups(sfSwitch, visualStateGroupList);

this.Content = sfSwitch;

{% endhighlight %}

{% endtabs %}

![switch conrol with image](images/thumb-color-in-disabled-state.png)

## Change busy indicator color

You can customize the busy indicator color using the `BusyIndicatorColor` property based on its visual state and devices.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch  VisualType="Custom"  IsBusy="True">

        <VisualStateManager.VisualStateGroups>

            <VisualStateGroup  x:Name="CommonStates">

                <VisualState x:Name="On">

                    <VisualState.Setters>

                        <Setter Property="SwitchSettings">

                            <Setter.Value>

                                <syncfusion:DefaultSwitchSettings  x:TypeArguments="syncfusion:OnState"  BusyIndicatorColor="Red" >

                                </syncfusion:DefaultSwitchSettings>

                            </Setter.Value>

                        </Setter>

                    </VisualState.Setters>

                </VisualState>

                <VisualState x:Name="Off">

                    <VisualState.Setters>

                        <Setter Property="SwitchSettings">

                            <Setter.Value>

                                <syncfusion:DefaultSwitchSettings x:TypeArguments="syncfusion:OffState" BusyIndicatorColor="Red" />

                            </Setter.Value>

                        </Setter>

                    </VisualState.Setters>

                </VisualState>

            </VisualStateGroup>

        </VisualStateManager.VisualStateGroups>

    </syncfusion:SfSwitch>

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();
sfSwitch.VisualType = VisualType.Custom;
sfSwitch.IsBusy = true;
DefaultSwitchSettings<OnState> defaultSwitch = new DefaultSwitchSettings<OnState>();
defaultSwitch.BusyIndicatorColor = Color.Red;
DefaultSwitchSettings<OffState> defaultSwitch1 = new DefaultSwitchSettings<OffState>();
defaultSwitch1.BusyIndicatorColor = Color.Red;

VisualStateGroupList visualStateGroupList = new VisualStateGroupList();

VisualStateGroup commonStateGroup = new VisualStateGroup();
VisualState onState = new VisualState
{
Name = "On"
};
onState.Setters.Add(new Setter { Property = SfSwitch.SwitchSettingsProperty, Value = defaultSwitch });

VisualState offState = new VisualState
{
Name = "Off"
};

offState.Setters.Add(new Setter { Property = SfSwitch.SwitchSettingsProperty, Value = defaultSwitch1 });

commonStateGroup.States.Add(onState);
commonStateGroup.States.Add(offState);
visualStateGroupList.Add(commonStateGroup);

VisualStateManager.SetVisualStateGroups(sfSwitch, visualStateGroupList);

this.Content = sfSwitch;

{% endhighlight %}

{% endtabs %}

![switch control with busy indicator color](images/change-busy-indicator-color.png)

## Set all state in same look

All state can be customized in same look by setting the same state for all switch settings.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch  VisualType="Custom" >

        <VisualStateManager.VisualStateGroups>

            <VisualStateGroup  x:Name="CommonStates">

                <VisualState x:Name="On">

                    <VisualState.Setters>

                        <Setter Property="SwitchSettings">

                            <Setter.Value>

                                <syncfusion:DefaultSwitchSettings  x:TypeArguments="syncfusion:OnState" />

                            </Setter.Value>

                        </Setter>

                    </VisualState.Setters>

                </VisualState>

                <VisualState x:Name="Off">

                    <VisualState.Setters>

                        <Setter Property="SwitchSettings">

                            <Setter.Value>

                                <syncfusion:DefaultSwitchSettings x:TypeArguments="syncfusion:OnState" />

                            </Setter.Value>

                        </Setter>

                    </VisualState.Setters>

                </VisualState>

            </VisualStateGroup>

        </VisualStateManager.VisualStateGroups>

    </syncfusion:SfSwitch>

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();
sfSwitch.VisualType = VisualType.Custom;

DefaultSwitchSettings<OnState> defaultSwitch = new DefaultSwitchSettings<OnState>();

DefaultSwitchSettings<OnState> defaultSwitch1 = new DefaultSwitchSettings<OnState>();

VisualStateGroupList visualStateGroupList = new VisualStateGroupList();

VisualStateGroup commonStateGroup = new VisualStateGroup();
VisualState onState = new VisualState
{
Name = "On"
};
onState.Setters.Add(new Setter { Property = SfSwitch.SwitchSettingsProperty, Value = defaultSwitch });

VisualState offState = new VisualState
{
Name = "Off"
};

offState.Setters.Add(new Setter { Property = SfSwitch.SwitchSettingsProperty, Value = defaultSwitch1 });

commonStateGroup.States.Add(onState);

commonStateGroup.States.Add(offState);

visualStateGroupList.Add(commonStateGroup);

VisualStateManager.SetVisualStateGroups(sfSwitch, visualStateGroupList);

this.Content = sfSwitch;

{% endhighlight %}

{% endtabs %}

![switch control with same look](images/All-state-in-same-look.png)

## Set RTL to switch control

Switch supports to change the layout direction of the control in the right-to-left direction by setting the `FlowDirection` to `RightToLeft`.
The device direction takes when we set the `FlowDirection` as `MatchParent`.

### Setting right to left

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch  FlowDirection="RightToLeft" >
    </syncfusion:SfSwitch>

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();
sfSwitch.FlowDirection = FlowDirection.RightToLeft;
this.Content = sfSwitch;

{% endhighlight %}

{% endtabs %}

![switch control with RTL support](images/RTL-support.png)

### Setting match parent

{% tabs %}

{% highlight xaml %}

     <Grid FlowDirection="RightToLeft">
        <syncfusion:SfSwitch FlowDirection="MatchParent" />
    </Grid>

{% endhighlight %}

{% highlight c# %}

Grid grid = new Grid();
grid.FlowDirection = FlowDirection.RightToLeft;
SfSwitch sfSwitch = new SfSwitch();
sfSwitch.FlowDirection = FlowDirection.MatchParent;
grid.Children.Add(sfSwitch);
this.Content = grid;

{% endhighlight %}

{% endtabs %}

![switch control with RTL support](images/RTL-support.png)

## Get default color of the switches in all three state.

The following table illustrate the default color of the switches in all three state.

### Material

<table>
    <tr>
        <th>Elements<br/>
            <br/></th>        
        <th>
          State
            <br/>
            <br/>
        </th>
        <th>
            Colors
            <br/>
            <br/>
        </th>
    </tr>
 	<tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            On
            <br/>
            <br/>
        </td>
        <td>
            Accent
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            Off
            <br/>
            <br/>
        </td>
        <td>
            #FFFFFFFF
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Accent
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled On
            <br/>
            <br/>
        </td>
        <td>
            Accent with 0.4 opacity
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled Off
            <br/>
            <br/>
        </td>
        <td>
            #FFFFFFFF
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Accent with 0.4 opacity
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            On
            <br/>
            <br/>
        </td>
        <td>
            Accent
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Off
            <br/>
            <br/>
        </td>
        <td>
            LightGray
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Accent
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled On
            <br/>
            <br/>
        </td>
        <td>
            Accent with 0.4 opacity
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled Off
            <br/>
            <br/>
        </td>
        <td>
            #DADADA
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Accent with 0.4 opacity
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Color     
            <br/>
            <br/>
        </td>
        <td>
            On
            <br/>
            <br/>
        </td>
        <td>
            Accent with 0.2 opacity
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Color     
            <br/>
            <br/>
        </td>
        <td>
            Off
            <br/>
            <br/>
        </td>
        <td>
            #949494
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Track Color       
            <br/>
            <br/>
        </td>
        <td>
            Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            #CACACA
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled On
            <br/>
            <br/>
        </td>
        <td>
            Accent with 0.2 opacity
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled Off
            <br/>
            <br/>
        </td>
        <td>
            #E0E0E0
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Track Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            #E0E0E0
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Track Border Color     
            <br/>
            <br/>
        </td>
        <td>
            On
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Off
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Track Border Color       
            <br/>
            <br/>
        </td>
        <td>
            Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Border Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled On
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Border Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled Off
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Track Border Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Busy Indicator Color    
            <br/>
            <br/>
        </td>
        <td>
            On
            <br/>
            <br/>
        </td>
        <td>
            #00BFFF
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Busy Indicator Color     
            <br/>
            <br/>
        </td>
        <td>
            Off
            <br/>
            <br/>
        </td>
        <td>
            #00BFFF
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Busy Indicator Color       
            <br/>
            <br/>
        </td>
        <td>
            Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            #00BFFF
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Busy Indicator Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled On
            <br/>
            <br/>
        </td>
        <td>
            #00BFFF
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Busy Indicator Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled Off
            <br/>
            <br/>
        </td>
        <td>
            #00BFFF
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Busy Indicator Color      
            <br/>
            <br/>
        </td>
        <td>
            Disabled Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            #00BFFF
            <br/>
            <br/>
        </td>
    </tr>
    </table>

### Cupertino 

<table>
    <tr>
        <th>Elements<br/>
            <br/></th>        
        <th>
          State
            <br/>
            <br/>
        </th>
        <th>
            Colors
            <br/>
            <br/>
        </th>
    </tr>
 	<tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            On
            <br/>
            <br/>
        </td>
        <td>
            #FFFFFF
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            Off
            <br/>
            <br/>
        </td>
        <td>
            #FFFFFF
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Accent
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled On
            <br/>
            <br/>
        </td>
        <td>
            #FFFFFFFF
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled Off
            <br/>
            <br/>
        </td>
        <td>
            #FFFFFFFF
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Accent with 0.5 opacity
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            On
            <br/>
            <br/>
        </td>
        <td>
            0.1 Opacity
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Off
            <br/>
            <br/>
        </td>
        <td>
            0.3 Opacity
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            0.1 Opacity
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled On
            <br/>
            <br/>
        </td>
        <td>
            0.5 Opacity
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled Off
            <br/>
            <br/>
        </td>
        <td>
            0.3 Opacity
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            0.5 Opacity
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Color     
            <br/>
            <br/>
        </td>
        <td>
            On
            <br/>
            <br/>
        </td>
        <td>
            Accent
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Color     
            <br/>
            <br/>
        </td>
        <td>
            Off
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Track Color       
            <br/>
            <br/>
        </td>
        <td>
            Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled On
            <br/>
            <br/>
        </td>
        <td>
            Accent with 0.5 opacity
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled Off
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Track Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Track Border Color     
            <br/>
            <br/>
        </td>
        <td>
            On
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Off
            <br/>
            <br/>
        </td>
        <td>
            #E5E5E5
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Track Border Color       
            <br/>
            <br/>
        </td>
        <td>
            Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Accent
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Border Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled On
            <br/>
            <br/>
        </td>
        <td>
            Accent with 0.5 opacity
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Border Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled Off
            <br/>
            <br/>
        </td>
        <td>
            #F2F2F2
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Track Border Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Accent with 0.5 opacity
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Busy Indicator Color    
            <br/>
            <br/>
        </td>
        <td>
            On
            <br/>
            <br/>
        </td>
        <td>
            #00BFFF
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Busy Indicator Color     
            <br/>
            <br/>
        </td>
        <td>
            Off
            <br/>
            <br/>
        </td>
        <td>
            #00BFFF
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Busy Indicator Color       
            <br/>
            <br/>
        </td>
        <td>
            Indeterminate
            <br/>
            <br/>
        </td>
        <td>
           #00BFFF  
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Busy Indicator Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled On
            <br/>
            <br/>
        </td>
        <td>
            #00BFFF
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Busy Indicator Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled Off
            <br/>
            <br/>
        </td>
        <td>
            #00BFFF
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Busy Indicator Color      
            <br/>
            <br/>
        </td>
        <td>
            Disabled Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            #00BFFF
            <br/>
            <br/>
        </td>
    </tr>
</table>

### Fluent

<table>
    <tr>
        <th>Elements<br/>
            <br/></th>        
        <th>
          State
            <br/>
            <br/>
        </th>
        <th>
            Colors
            <br/>
            <br/>
        </th>
    </tr>
 	<tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            On
            <br/>
            <br/>
        </td>
        <td>
            #FFFFFFFF
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            Off
            <br/>
            <br/>
        </td>
        <td>
            #000000
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Accent
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled On
            <br/>
            <br/>
        </td>
        <td>
            0.2 Opacity
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled Off
            <br/>
            <br/>
        </td>
        <td>
             0.2 Opacity
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Thumb Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled Indeterminate
            <br/>
            <br/>
        </td>
        <td>
             0.2 Opacity
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            On
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Off
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled On
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled Off
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Thumb Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Disabled Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Color     
            <br/>
            <br/>
        </td>
        <td>
            On
            <br/>
            <br/>
        </td>
        <td>
            Accent
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Color     
            <br/>
            <br/>
        </td>
        <td>
            Off
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Track Color       
            <br/>
            <br/>
        </td>
        <td>
            Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Transparent
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled On
            <br/>
            <br/>
        </td>
        <td>
            0.2 opacity
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled Off
            <br/>
            <br/>
        </td>
        <td>
            0.2 opacity
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Track Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            0.2 opacity
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Track Border Color     
            <br/>
            <br/>
        </td>
        <td>
            On
            <br/>
            <br/>
        </td>
        <td>
            Accent
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Border Color     
            <br/>
            <br/>
        </td>
        <td>
            Off
            <br/>
            <br/>
        </td>
        <td>
            #000000
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Track Border Color       
            <br/>
            <br/>
        </td>
        <td>
            Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            Accent
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Border Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled On
            <br/>
            <br/>
        </td>
        <td>
            0.2 Opacity
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Track Border Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled Off
            <br/>
            <br/>
        </td>
        <td>
            0.2 Opacity
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Track Border Color       
            <br/>
            <br/>
        </td>
        <td>
            Disabled Indeterminate
            <br/>
            <br/>
        </td>
        <td>
            0.2 Opacity
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Busy Indicator Color    
            <br/>
            <br/>
        </td>
        <td>
            On
            <br/>
            <br/>
        </td>
        <td>
            #00BFFF
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Busy Indicator Color     
            <br/>
            <br/>
        </td>
        <td>
            Off
            <br/>
            <br/>
        </td>
        <td>
            #00BFFF
            <br/>
            <br/>
        </td>
    </tr>
      <tr>
		<td>
            Busy Indicator Color       
            <br/>
            <br/>
        </td>
        <td>
            Indeterminate
            <br/>
            <br/>
        </td>
        <td>
           #00BFFF  
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Busy Indicator Color       
            <br/>
            <br/>
        </td>
        <td>
            DisabledOn
            <br/>
            <br/>
        </td>
        <td>
            #00BFFF
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
		<td>
            Busy Indicator Color       
            <br/>
            <br/>
        </td>
        <td>
            DisabledOff
            <br/>
            <br/>
        </td>
        <td>
            #00BFFF
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
		<td>
            Busy Indicator Color      
            <br/>
            <br/>
        </td>
        <td>
            DisabledIndeterminate
            <br/>
            <br/>
        </td>
        <td>
            #00BFFF
            <br/>
            <br/>
        </td>
    </tr>
</table>