---
layout: post
title: Various Customizations in Syncfusion AvatarView Control
description: Learn about the avatar types available in SfAvatarView and how to configure them in Xamarin.Forms.
platform: Xamarin
control: SfAvatarView
documentation: ug
---

# Content Types in Xamarin Avatar View (SfAvatarView)

## Avatar Types

The [`SfAvatarView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html) control offers five different ways to display its content:

- [`Default`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.ContentType.html#Syncfusion_XForms_AvatarView_ContentType_Default): Provides a default image with no additional source.
- [`AvatarName`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_AvatarName): Sets the initial value for display.
- [`Custom`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.ContentType.html#Syncfusion_XForms_AvatarView_ContentType_Custom): Displays a user-provided custom image.
- [`AvatarCharacter`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.ContentType.html#Syncfusion_XForms_AvatarView_ContentType_AvatarCharacter): Uses a preset vector image.
- [`Group`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.ContentType.html#Syncfusion_XForms_AvatarView_ContentType_Group): Combines up to three images or initials within a single view.

## Default

The automatic avatar view displays a default vector image when initialized without initials, custom images, or group view types.

{% tabs %}

{% highlight xaml %}

    <sfavatar:SfAvatarView ContentType="Default"     
                            VerticalOptions="Center"
                            HorizontalOptions="Center"
                            WidthRequest="50"
                            HeightRequest="50"
                            CornerRadius="25">
    </sfavatar:SfAvatarView>
	
{% endhighlight %}

{% highlight C# %}

            Grid mainGrid = new Grid();       
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.WidthRequest = 50;
            avatarview.HeightRequest = 50;
            avatarview.CornerRadius = 25;
            avatarview.ContentType = ContentType.Default;   
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;

{% endhighlight %}

{% endtabs %}

![ShadowImage](images/CharacterAvatar.jpg)

## Initials 

To use initials with the [`SfAvatarView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html), set up the initial character using the following properties:

- [`InitialsType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_InitialsType): Defines the type of initials displayed.
- [`AvatarName`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_AvatarName): Gets or sets the initials value.
- [`InitialsColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_InitialsColor): Sets the initial color value.

### InitialsType

The `InitialsType` property provides these options:
- [`SingleCharacter`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.InitialsType.html#Syncfusion_XForms_AvatarView_InitialsType_SingleCharacter)
- [`DoubleCharacter`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.InitialsType.html#Syncfusion_XForms_AvatarView_InitialsType_DoubleCharacter)
#### SingleCharacter

The [`SingleCharacter`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.InitialsType.html#Syncfusion_XForms_AvatarView_InitialsType_SingleCharacter) is used for displaying the first character in the string you have set in the [`Initials`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.ContentType.html#Syncfusion_XForms_AvatarView_ContentType_Initials) property.

{% tabs %}
{% highlight xaml %}

        <sfavatar:SfAvatarView ContentType="Initials"
                               HorizontalOptions="Center"
                               VerticalOptions="Center"
                               InitialsType="SingleCharacter"
                               AvatarName="Alex"
                               InitialsColor="Black" 
                               WidthRequest="50"
                               FontAttributes="Bold"
                               HeightRequest="50"
                               CornerRadius="25"          
                               BackgroundColor="Bisque">
        </sfavatar:SfAvatarView>

{% endhighlight %}
{% highlight c# %}
             
            Grid mainGrid = new Grid();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.BackgroundColor = Color.Bisque;
            avatarview.WidthRequest = 50;
            avatarview.HeightRequest = 50;
            avatarview.CornerRadius = 25;
            avatarview.ContentType = ContentType.Initials;
            avatarview.AvatarName = "Alex";
            avatarview.InitialsType = InitialsType.SingleCharacter;
            avatarview.InitialsColor = Color.Black;
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;

{% endhighlight %}
{% endtabs %}

![SingleCharacter](images/Initial_Single_AvatarView.png)

### DoubleCharacter

The [`DoubleCharacter`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.InitialsType.html#Syncfusion_XForms_AvatarView_InitialsType_DoubleCharacter) is used for displaying a two-characters text you have set in the [`Initials`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.ContentType.html#Syncfusion_XForms_AvatarView_ContentType_Initials) property. If the initials contain one word, it shows the first and last letters of the single string. If it contains two or more words, it displays the first letter of the first string and first letter of the last string.

{% tabs %}
{% highlight xaml %}

        <sfavatar:SfAvatarView ContentType="Initials"
                               InitialsType="DoubleCharacter"
                               AvatarName="Alex"
                               InitialsColor="Black"                     
                               WidthRequest="50"
                               FontAttributes="Bold"                     
                               HeightRequest="50"
                               CornerRadius="25"                        
                               BackgroundColor="Bisque">
        </sfavatar:SfAvatarView>

{% endhighlight %}
{% highlight c# %}
          
            Grid mainGrid = new Grid();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.BackgroundColor = Color.Bisque;
            avatarview.WidthRequest = 50;
            avatarview.HeightRequest = 50;
            avatarview.CornerRadius = 25;
            avatarview.ContentType = ContentType.Initials;
            avatarview.AvatarName = "Alex";
            avatarview.InitialsType = InitialsType.DoubleCharacter;
            avatarview.InitialsColor = Color.Black;
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;

{% endhighlight %}
{% endtabs %}

![bordercolor](images/Initial_Double_AvatarView.png)

## Custom Image

Add a custom image using the [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_ImageSource) property. More details can be found in the [documentation](https://help.syncfusion.com/xamarin/SfAvatarView/getting-started).

## Character Avatars

Use preset vector images in avatar view by setting the [`AvatarCharacter`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_AvatarCharacter) property.

{% tabs %}
{% highlight xaml %}

        <sfavatar:SfAvatarView  VerticalOptions="Center"
                                HorizontalOptions="Center"
                                ContentType="AvatarCharacter"
                                AvatarCharacter="Avatar10"
                                WidthRequest="50"
                                HeightRequest="50"
                                CornerRadius="25">
        </sfavatar:SfAvatarView>

{% endhighlight %}
{% highlight c# %}
            
            Grid mainGrid = new Grid();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.WidthRequest = 50;
            avatarview.HeightRequest = 50;
            avatarview.CornerRadius = 25;
            avatarview.ContentType = ContentType.AvatarCharacter;
            avatarview.AvatarCharacter = AvatarCharacter.Avatar10;
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;
            
{% endhighlight %}
{% endtabs %}

![cornerradius](images/AvatarCharacter10.jpg)

## GroupView 

In a GroupView, you can combine up to three images or initials.

Set the [`InitialsMemberPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_InitialsMemberPath) for initials or `ImageSourcePath` for images.
{% tabs %}
{% highlight c# %}
 public class Employee
    {

        private string name;
        public string Name
        {
            get { return name; }
            set { name = value; }
        }

        private string imagesource;

        public string ImageSource
        {
            get { return imagesource; }
            set { imagesource = value; }
        }

        private Color colors;

        public Color Colors
        {
            get { return colors; }
            set { colors = value; }
        }

    }

    public class EmployeeViewMdoel : INotifyPropertyChanged
    {

        public event PropertyChangedEventHandler PropertyChanged;
        private void OnPropertyRaised(string propertyname)
        {
            if (PropertyChanged != null)
            {
                PropertyChanged(this, new PropertyChangedEventArgs(propertyname));
            }
        }
        private ObservableCollection<Employee> collectionimage;

        public ObservableCollection<Employee> CollectionImage
        {
            get { return collectionimage; }
            set
            {
                collectionimage = value;
                OnPropertyRaised("CollectionImage");
            }
        }

        public EmployeeViewMdoel()
        {
            CollectionImage = new ObservableCollection<Employee>();
            CollectionImage.Add(new Employee { Name="Mike" , ImageSource = "mike.png",Colors=Color.Gray });
            CollectionImage.Add(new Employee { Name="Alex",ImageSource= "alex.png", Colors = Color.Bisque });
            CollectionImage.Add(new Employee { Name="Ellanaa", ImageSource= "ellanaa.png",Colors=Color.LightCoral })
        }

    }
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<ContentPage.BindingContext>
        <local:EmployeeViewMdoel/>
</ContentPage.BindingContext>

   <sfavatar:SfAvatarView ContentType="Group"                         
                          VerticalOptions="Center"
                          HorizontalOptions="Center"
                          GroupSource="{Binding CollectionImage}"
                          InitialsMemberPath="Name"
                          BackgroundColorMemberPath="Colors"
                          ImageSourceMemberPath="ImageSource"
                          WidthRequest="50"
                          HeightRequest="50"
                          CornerRadius="25">
    </sfavatar:SfAvatarView>

{% endhighlight %}
{% highlight c# %}

 public partial class MainPage : ContentPage, INotifyPropertyChanged
    {
        EmployeeViewMdoel emp;

           public MainPage()
          {
            InitializeComponent();
            Grid mainGrid = new Grid();
            emp = new EmployeeViewMdoel();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.WidthRequest = 50;
            avatarview.HeightRequest = 50;
            avatarview.CornerRadius = 25;
            avatarview.ContentType = ContentType.Group;
            avatarview.GroupSource = emp.CollectionImage;
            avatarview.InitialsMemberPath = "Name";
            avatarview.ImageSourceMemberPath = "ImageSource";
            avatarview.BackgroundColorMemberPath = "Colors";
            this.BindingContext = emp;
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;
            }
    }

{% endhighlight %}
{% endtabs %}

![GroupViewImage](images/GroupView_SfAvatarView.png)

## Add initials only in GroupView

You can set the initials only in the group view by setting the [`InitialsMemberPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_InitialsMemberPath) alone. It is demonstrated in the following code sample.

{% tabs %}

{% highlight xaml %}

<ContentPage.BindingContext>
        <local:EmployeeViewMdoel/>
</ContentPage.BindingContext>

   <sfavatar:SfAvatarView ContentType="Group"                  
                          VerticalOptions="Center"
                          HorizontalOptions="Center"
                          GroupSource="{Binding CollectionImage}"
                          InitialsMemberPath="Name"
                          BackgroundColorMemberPath="Colors"
                          WidthRequest="50"
                          HeightRequest="50"
                          CornerRadius="25">
                </sfavatar:SfAvatarView>

{% endhighlight %}

{% highlight c# %}

public partial class MainPage : ContentPage, INotifyPropertyChanged
    {
        EmployeeViewMdoel emp;
         public MainPage()
        {

            Grid mainGrid = new Grid();
            emp = new EmployeeViewMdoel();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.WidthRequest = 50;
            avatarview.HeightRequest = 50;
            avatarview.CornerRadius = 25;
            avatarview.ContentType = ContentType.Group;
            avatarview.GroupSource = emp.CollectionImage;
            avatarview.InitialsMemberPath = "Name";
            avatarview.BackgroundColorMemberPath = "Colors";
            this.BindingContext = emp;
            mainGrid.Children.Add(avatarview);
            this.Content = mainGrid;
         }
      }

{% endhighlight %}
{% endtabs %}

![GroupView in ListView](images/GroupView_Initilasalone.png)

## Add both image and initials in a GroupView

You have to set both the image and initials based on what should be added in the collection. If the image needs to be added, set `ImageSourcePath`, or if initials need to be added, set [`InitialsMemberPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html#Syncfusion_XForms_AvatarView_SfAvatarView_InitialsMemberPath). This is demonstrated in the following code snippet.

{% tabs %}
{% highlight c# %}

 public class EmployeeViewMdoel : INotifyPropertyChanged
    {
          public EmployeeViewMdoel()
        {
            CollectionImage = new ObservableCollection<Employee>();
            CollectionImage.Add(new Employee { ImageSource="mike.png" });
            CollectionImage.Add(new Employee { Name= "alex", Colors=Color.White });
            CollectionImage.Add(new Employee { ImageSource= "ellanaa.png" });
        } 
        
    }
}

{% endhighlight %}
{% endtabs %}


![GroupView in ListView](images/GroupView_InitilalandImage.png)

## Add GroupView using MVVM

Create model and view model for initializing and assigning a value for adding image or initials in the [`SfAvatarView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.AvatarView.SfAvatarView.html). The following code sample demonstrates how to use the `GroupView` property using MVVM pattern.

{% tabs %}
{% highlight c# %}

//Model.cs
   public class Model
    {      
        public string Name { get; set; }

        public string Images { get; set; }
    }

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

//ViewModel.cs
 public class AvatarViewModel
    {
       
        /// <summary>
        /// Gets or sets the value for PeopleCollection field.
        /// </summary>
        public ObservableCollection<Model> PeopleCollection { get; set; }

        /// <summary>
        /// Gets oe sets the value for the group view collections.
        /// </summary>
        public ObservableCollection<Model> GroupViewCollection { get; set; }

        /// <summary>
        /// AvatarViewModel
        /// </summary>
        /// <param name="count">Count value</param>
        public AvatarViewModel(int count)
        {
            PopulateModel();
            PopulatePeopleCollection(count);
        }

        /// <summary>
        /// Static count value.
        /// </summary>
        static int staticcount = 0;

        /// <summary>
        /// Change the collections for each group.
        /// </summary>
        /// <param name="count">count value</param>
        private void PopulatePeopleCollection(int count)
        {
            PeopleCollection = new ObservableCollection<Model>();
            for (int i = 0; i < count; i++)
            {
                while (true)
                {
                    if (GroupViewCollection.Count <= staticcount)
                        staticcount = 0;
                    var person = GroupViewCollection[staticcount++];
                    if (!PeopleCollection.Contains(person))
                    {
                        PeopleCollection.Add(person);
                        break;
                    }
                }
            }

        }

        /// <summary>
        /// To add the name and images.
        /// </summary>
        private void PopulateModel()
        {
            GroupViewCollection = new ObservableCollection<Model>();
            GroupViewCollection.Add(new Model() { Name = "Adriana", Images = "Adriana.png" });
            GroupViewCollection.Add(new Model() { Name = "Aiden", Images = "Aiden.png" });
            GroupViewCollection.Add(new Model() { Name = "Alexander" });
            GroupViewCollection.Add(new Model() { Name = "Arianna", Images = "Arianna.png" });
            GroupViewCollection.Add(new Model() { Name = "Clara", Images = "Clara.png" });
            GroupViewCollection.Add(new Model() { Name = "Daleyza", Images = "Daleyza.png" });
            GroupViewCollection.Add(new Model() { Name = "Ellie", Images = "Ellie.png" });
            GroupViewCollection.Add(new Model() { Name = "Finley" });
            GroupViewCollection.Add(new Model() { Name = "Jackson", Images = "Jackson.png" });
            GroupViewCollection.Add(new Model() { Name = "Jayden" });
            GroupViewCollection.Add(new Model() { Name = "Kaylee", Images = "Kaylee.png" });
            GroupViewCollection.Add(new Model() { Name = "Lucy" });

        }
    }

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<!--MainPage.Xaml-->

   <sfavatarview:SfAvatarView ContentType="Group"
                              Margin="5,0,0,0"
                              HorizontalOptions="Center"
                              HeightRequest="50"
                              WidthRequest="50"
                              CornerRadius="25"
                              VerticalOptions="Center"
                              GroupSource="{Binding PeopleCollection}"
                              ImageSourceMemberPath="Images"
                              InitialsMemberPath="Name">
     </sfavatarview:SfAvatarView>

{% endhighlight %}
{% highlight c# %}

//MainPage.Xaml.cs
            avm = new AvatarViewModel();
            SfAvatarView avatarview = new SfAvatarView();
            avatarview.VerticalOptions = LayoutOptions.Center;
            avatarview.HorizontalOptions = LayoutOptions.Center;
            avatarview.WidthRequest = 50;
            avatarview.HeightRequest = 50;
            avatarview.CornerRadius = 25;
            avatarview.ContentType = ContentType.Group;
            avatarview.GroupSource = avm.PeopleCollection;
            avatarview.InitialsMemberPath = "Name";
            avatarview.BackgroundColorMemberPath = "Colors";
            mainGrid.Children.Add(avatarview);

{% endhighlight %}
{% endtabs %}

![GroupView in ListView](images/GroupView_Listview.png)

The complete SfAvatarView of GroupView type using MVVM is available in this [sample](https://www.syncfusion.com/downloads/support/directtrac/general/ze/GroupViewSample1097739977).

