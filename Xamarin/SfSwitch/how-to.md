---
layout: post
title: States in Syncfusion SfSwitch Xamarin.Forms.
description: Explaining about states in SfSwitch.
platform: Xamarin
control: Switch
documentation: ug
---

## How to

### Show busy indicator to perform async action

The busy indicator indicates the users that something is progress in the background. For instance, some data is being fetched from the back end. Here when user about to switch state,  StateChanging event is triggerred at we can here set the `IsBusy` property as true to show busy indicator and can perform fetching the data from the server. After fetching the data, `IsOn` property will be true or false based on validation. After validation, `IsBusy` property is set to false.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch x:Name="sfSwitch" StateChanging="Stc_StateChanging"/>
        
{% endhighlight %}

{% highlight c# %}

       private async void Stc_StateChanging(object sender, Syncfusion.XForms.Core.CancelEventArgs e)
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

{% endtabs %}

![switch control with busy indicator](images/busy-indicator.png)

### Change thumb color alone, based on its state and devices

You customize the thumb color by using `ThumbColor` property in  based on its visual state and devices.

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
                Name = "OFF"
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

### Change thumb color alone based on its state with Material theme for all devices?

By using the `MaterialSwitchSettings`, `CupertinoSwitchSettings` and 
`FluentSwitchSettings` properties, you can change the thumb color based on its state for all devices. 

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

{% endtabs %}

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
                Name = "OFF"
            };

            offState.Setters.Add(new Setter { Property = SfSwitch.SwitchSettingsProperty, Value = defaultSwitch1 });

            commonStateGroup.States.Add(onState);
            commonStateGroup.States.Add(offState);
            visualStateGroupList.Add(commonStateGroup);

            VisualStateManager.SetVisualStateGroups(sfSwitch, visualStateGroupList);

            this.Content = sfSwitch;

{% endhighlight %}

![switch conrol with thumb color](images/thumb-color-based-on-device.png)