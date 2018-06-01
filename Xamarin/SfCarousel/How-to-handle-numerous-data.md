---
layout : post
title : How to handle numerous data in Syncfusion Carousel control in Xamarin.Forms.
description : Learn how to handle numerous data in Carousel for Xamarin.Forms.
platform : Xamarin
control : Carousel
documentation : ug
---

# How to handle numerous data in the carousel control

When loading numerous data to the carousel control, a support is needed for virtualization to consider the performance. With that criteria, the support is achieved by using the following features:

* [LoadMore](https://help.syncfusion.com/xamarin/sfcarousel/LoadMore)  - Instead of loading all items initially, split that collection by some specific count value (`LoadMoreItemsCount` property), then add the first set into the carousel view. By maintaining the load more view in carousel view, you can add next set. 

* [UIVirtualization](https://help.syncfusion.com/xamarin/sfcarousel/UIVirtualization) – Here, a particular count of items (View port adaptable count) are maintained in carousel view. Items can be added at the right of the view while swiping countable items in forward direction. At the same time, same number of items can be removed at the left of view for maintaining the same viewport items count. Similarly,items can be added at the left of the view while swiping in backward direction for maintaining the same viewport items count. Same time and same number of items can be removed at the right of the view.
