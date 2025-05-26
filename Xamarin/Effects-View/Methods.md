---
layout: post
title: Methods in Xamarin Effects View Control | Syncfusion
description: Explore the methods supported in the Syncfusion Xamarin Effects View (SfEffectsView) control for managing effects programmatically.
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Methods in Xamarin Effects View (SfEffectsView)

The `SfEffectsView` control allows you to add or remove effects programmatically using the [`ApplyEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_ApplyEffects_Syncfusion_XForms_EffectsView_SfEffects_Syncfusion_XForms_EffectsView_RippleStartPosition_System_Nullable_System_Drawing_Point__System_Boolean_) or [`Reset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_Reset) methods.

## ApplyEffects

The [`ApplyEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_ApplyEffects_Syncfusion_XForms_EffectsView_SfEffects_Syncfusion_XForms_EffectsView_RippleStartPosition_System_Nullable_System_Drawing_Point__System_Boolean_) method is used to initiate effect rendering, with or without repetition. The method can accept the following optional parameters:

* **`effects`**: The [`SfEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffects.html) to be applied, with `SfEffects.Ripple` as the default.
* **`rippleStartPosition`**: The [`RippleStartPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.RippleStartPosition.html) value, which can be left, top, right, bottom, or default. By default, the ripple starts from the center.
* **`rippleStartPoint`**: Specifies the starting point for the ripple animation. The default is `null`.
* **`repeat`**: A boolean that specifies whether to repeat the applied effect. The default is `false`. Only `SfEffects.Ripple` and `SfEffects.Highlight` can repeat.

> **Note:** Effects applied using the `ApplyEffects` method will not be automatically removed.
## Reset

The [`Reset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_Reset) method is used to reset the `SfEffects.Highlight` and `SfEffects.Ripple` effects applied through the `ApplyEffects` method.
