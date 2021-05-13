---
layout: post
title: Methods in Xamarin Effects View control | Syncfusion
description: Learn here all about Methods support in Syncfusion Xamarin Effects View (SfEffectsView) control and more.
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Methods in Xamarin Effects View (SfEffectsView)

You can add or remove effect programmatically using the [`ApplyEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_ApplyEffects_Syncfusion_XForms_EffectsView_SfEffects_Syncfusion_XForms_EffectsView_RippleStartPosition_System_Nullable_System_Drawing_Point__System_Boolean_) or [`Reset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_Reset) method.

## ApplyEffects

The [`ApplyEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_ApplyEffects_Syncfusion_XForms_EffectsView_SfEffects_Syncfusion_XForms_EffectsView_RippleStartPosition_System_Nullable_System_Drawing_Point__System_Boolean_) method is used to trigger the effects rendering with or without repetition. The following are the optional parameters to be passed:

* `effects` - [`SfEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffects.html) to be applied. By default, `SfEffects.Ripple` will be applied.
* `rippleStartPosition` - [`RippleStartPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.RippleStartPosition.html) can be left, top, right, bottom, or default. By default, ripple starts from the center.
* `rippleStartPoint` - point at which ripple animation starts. The default value is null.
* `repeat` - bool value used to set whether to repeat the applied effect. The default value is false. Only `SfEffects.Ripple` and `SfEffects.Highlight` can be repeated.

N> The [`SfEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffects.html) applied using [`ApplyEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_ApplyEffects_Syncfusion_XForms_EffectsView_SfEffects_Syncfusion_XForms_EffectsView_RippleStartPosition_System_Nullable_System_Drawing_Point__System_Boolean_) method will not be removed automatically.

## Reset

The [`Reset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_Reset) method is used to reset the `SfEffects.Highlight` and `SfEffects.Ripple` effects, which are applied using the [`ApplyEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_ApplyEffects_Syncfusion_XForms_EffectsView_SfEffects_Syncfusion_XForms_EffectsView_RippleStartPosition_System_Nullable_System_Drawing_Point__System_Boolean_) method.
