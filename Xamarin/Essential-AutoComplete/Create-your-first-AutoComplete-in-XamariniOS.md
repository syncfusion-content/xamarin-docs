---
layout: post
title: Create-your-first-AutoComplete-in-XamariniOS
description: create your first autocomplete in xamarin.ios
platform: xamarin
control: Control Name undefined
documentation: ug
---

#### Create your first AutoComplete in Xamarin.iOS

This section provides a quick overview to work with the AutoComplete in Objective C. This example explains how to create an AutoComplete with different AutoCompleteModes and SuggestionModes.

![](Create-your-first-AutoComplete-in-XamariniOS_images/Create-your-first-AutoComplete-in-XamariniOS_img1.png)
{:.image }


Add Framework reference to the project

You can refer to the following link to learn how to refer to the framework to your project. 
[http://help.syncfusion.com/ug/ios/default.htm#!documents/addframeworkreferenc.htm](http://help.syncfusion.com/ug/ios/default.htm)

Create an AutoComplete

To develop an application with iOS AutoComplete is simple. 

Create an AutComplete object in the View Controller and add the AutoComplete as subview in viewdidload override method.

You can create an AutoComplete object by using the following code example.



@interface ViewController ()

{

    SFAutoComplete *autocomplete;



}



- (void)viewDidLoad

{

    [super viewDidLoad];

    autocomplete=[[ SFAutoComplete alloc]init];

    [self.view addSubview:autocomplete];

}



Setting the AutoCompleteSource to AutoComplete

You can set the suggestion list to the AutoComplete by using the property AutoCompleteSource.

-(NSMutableArray*) countryArray{

    NSMutableArray * array= [NSMutableArray array];



    [array addObject:[[AutoCompleteSource alloc]init:@"Afghanistan"]];

    [array addObject:[[AutoCompleteSource alloc]init:@"Akrotiri"]];

    [array addObject:[[AutoCompleteSource alloc]init:@"Albania"]];

    [array addObject:[[AutoCompleteSource alloc]init:@"Algeria"]];

}

@property (nonatomic, strong) AutoCompleteSource *source;

_source=[[AutoCompleteSource alloc]init];

autoComplete1.autoCompleteSource=[_source countryArray];





Setting AutoComplete Customizations

AutoComplete is customized by setting the properties as explained in the following code example.

_autoComplete1.suggestionMode=SFAutoCompleteSuggestionModeStartsWith;

_autoComplete1.autoCompleteSource=[_source countryArray];

_autoComplete1.tableViewStyle=UITableViewCellStyleDefault;

_autoComplete1.watermark=@"Enter country name";

_autoComplete1.autoCompleteMode=SFAutoCompleteAutoCompleteModeSuggest;

_autoComplete1.popUpDelay = 100;





