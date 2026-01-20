---
layout: post
title: Accessibility in Xamarin Carousel View Control | Syncfusion
description: Discover the accessibility support offered by the Syncfusion Xamarin Carousel View (SfCarousel) control.
platform: Xamarin.Forms
control: SfCarousel
documentation: ug
---

# Accessibility in Xamarin Carousel View (SfCarousel)

The [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) control provides built-in `AutomationId` for its inner elements. This `AutomationId` API enables automation frameworks to locate and interact seamlessly with the inner elements of the [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) control. Inner elements' AutomationIds are uniquely updated based on the control's `AutomationId` to ensure uniqueness.

For example, if you set a SfCarouselItem's `AutomationId` to "Person," the automation framework will reference the fourth carousel item as "Person SfCarouselItem 4 of 6" (where 6 denotes the total count).
 
The following screenshot illustrates the AutomationIds of inner elements. If the SfCarousel's `AutomationId` is set to "Gallery," the automation framework will identify the LoadMore as "Gallery LoadMore. Tap to load more items." Note that interaction with a carousel item is restricted if you attempt to select an index not visibly displayed.

N> Please note that `AutomationId` cannot be provided when the carousel item is populated using a custom template.

![AutomationId Image](images/AutomationId.png)
