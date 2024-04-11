# XamlStyler-GithubActions-Reference

Reference repository for checking the output when used as an action but with different logging levels.

This repo contains 2 XAML files. 
One file meets the defined settings.
One file doe not meet the defined settings.

That one of the files does not meet the defined settings means the passive check as part of a PR will FAIL.

Here's the output produced with all the different supported log levels. 

## None

```ascii
Error: Process completed with exit code 1.
```

## Minimal

```ascii

1 of 2 files pass format check.
Error: Process completed with exit code 1.
```

## Default

```ascii
Checking: ./SimpleValidFile.xaml
  PASS
Checking: ./SimpleInvalidFile.xaml
  FAIL

1 of 2 files pass format check.
Error: Process completed with exit code 1.
```

## Verbose

```ascii
Checking: ./SimpleValidFile.xaml
  PASS
Checking: ./SimpleInvalidFile.xaml
  FAIL

1 of 2 files pass format check.
Error: Process completed with exit code 1.
```

## Debug

```ascii
File Parameter: 'System.String[]'
File Count: 0
File Directory: '.'
["x:Class","xmlns, xmlns:x","xmlns:*","x:Key, Key, x:Name, Name, x:Uid, Uid, Title","Grid.Row, Grid.RowSpan, Grid.Column, Grid.ColumnSpan, Canvas.Left, Canvas.Top, Canvas.Right, Canvas.Bottom","Width, Height, MinWidth, MinHeight, MaxWidth, MaxHeight","Margin, Padding, HorizontalAlignment, VerticalAlignment, HorizontalContentAlignment, VerticalContentAlignment, Panel.ZIndex","*:*, *","PageSource, PageIndex, Offset, Color, TargetName, Property, Value, StartPoint, EndPoint","mc:Ignorable, d:IsDataSource, d:LayoutOverrides, d:IsStaticText","Storyboard.*, From, To, Duration"]
Checking: ./SimpleValidFile.xaml
Extension: .xaml
Full Path: ./SimpleValidFile.xaml
  PASS
Checking: ./SimpleInvalidFile.xaml
Extension: .xaml
Full Path: ./SimpleInvalidFile.xaml
  FAIL

1 of 2 files pass format check.
Error: Process completed with exit code 1.
```

## Insanity

```ascii
File Parameter: 'System.String[]'
File Count: 0
File Directory: '.'
{"IndentSize":4,"IndentWithTabs":true,"AttributesTolerance":1,"KeepFirstAttributeOnSameLine":true,"NewlineExemptionElements":"RadialGradientBrush, GradientStop, LinearGradientBrush, ScaleTransform, SkewTransform, RotateTransform, TranslateTransform, Trigger, Condition, Setter, StaticResource","AttributeIndentationStyle":0,"EnableAttributeReordering":false,"AttributeOrderingRuleGroups":["x:Class","xmlns, xmlns:x","xmlns:*","x:Key, Key, x:Name, Name, x:Uid, Uid, Title","Grid.Row, Grid.RowSpan, Grid.Column, Grid.ColumnSpan, Canvas.Left, Canvas.Top, Canvas.Right, Canvas.Bottom","Width, Height, MinWidth, MinHeight, MaxWidth, MaxHeight","Margin, Padding, HorizontalAlignment, VerticalAlignment, HorizontalContentAlignment, VerticalContentAlignment, Panel.ZIndex","*:*, *","PageSource, PageIndex, Offset, Color, TargetName, Property, Value, StartPoint, EndPoint","mc:Ignorable, d:IsDataSource, d:LayoutOverrides, d:IsStaticText","Storyboard.*, From, To, Duration"],"OrderAttributesByName":false,"ReorderVSM":0,"CommentPadding":1}
["x:Class","xmlns, xmlns:x","xmlns:*","x:Key, Key, x:Name, Name, x:Uid, Uid, Title","Grid.Row, Grid.RowSpan, Grid.Column, Grid.ColumnSpan, Canvas.Left, Canvas.Top, Canvas.Right, Canvas.Bottom","Width, Height, MinWidth, MinHeight, MaxWidth, MaxHeight","Margin, Padding, HorizontalAlignment, VerticalAlignment, HorizontalContentAlignment, VerticalContentAlignment, Panel.ZIndex","*:*, *","PageSource, PageIndex, Offset, Color, TargetName, Property, Value, StartPoint, EndPoint","mc:Ignorable, d:IsDataSource, d:LayoutOverrides, d:IsStaticText","Storyboard.*, From, To, Duration"]
Checking: ./SimpleValidFile.xaml
Extension: .xaml
Full Path: ./SimpleValidFile.xaml

Original Content:

<UserControl x:Class="EncodingBug.UserControlUtf8Bom"
			 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
			 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

	<Grid>
		<TextBlock Text="This file meets the defined styling settings" />
	</Grid>
</UserControl>


  PASS
Checking: ./SimpleInvalidFile.xaml
Extension: .xaml
Full Path: ./SimpleInvalidFile.xaml

Original Content:

<UserControl x:Class="EncodingBug.UserControlUtf8Bom"
			 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
			 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

	<Grid
    >
        <TextBlock 
                      Text="This file DOES NOT meet the defined styling settings"
                  />
	 </Grid>
</UserControl>


  FAIL

1 of 2 files pass format check.
Error: Process completed with exit code 1.
```



