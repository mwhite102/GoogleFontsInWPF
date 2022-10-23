# Using Custom Fonts in WPF

Simple example of using a custom font in a WPF application two different ways.

The font being used is [Architects Daughter](https://fonts.google.com/specimen/Architects+Daughter?query=arch) from Google fonts.

For both methods, download the font and unzip the contents into your project.  Set the Build Action for the font to 'Resource'.

![Properties Window](/assets/properties.png "Properties Window")

## Finding the Font Name

Both methods require the font name.  The font name is not the name of font's filename.

To find the font name, double click the font file and the font name can be found in the font viewer.

![Font Viewer](/assets/fontviewer.png "Font Viewer")

## Style Method

Add a style to the Application Resources in App.xaml referenceing the font using a [pack uri](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/app-development/pack-uris-in-wpf?view=netframeworkdesktop-4.8).

```c#
    <Application.Resources>
        <Style x:Key="ArchitectsDaughter">
            <Setter Property="TextElement.FontFamily" Value="pack://application:,,,/fonts/#Architects Daughter" />
        </Style>
    </Application.Resources>
```

Then set the style of the control you want to use the font on the sytle using a static resource.

```c#
<TextBlock
    FontSize="21px"
    Style="{StaticResource ArchitectsDaughter}"
    Text="From Style in App.xaml" />
```

## FontFamily Methods

Reference the font directly on the control you wish to use font on.

```c#
<TextBlock
    HorizontalAlignment="Center"
    FontFamily="fonts/ArchitectsDaughter-Regular.ttf #Architects Daughter"
    FontSize="21px"
    Text="From resource" />
```
