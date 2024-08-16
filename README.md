<Window x:Class="CustomSpinControl.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:dx="http://schemas.devexpress.com/winfx/2008/xaml/core"
        xmlns:dxe="http://schemas.devexpress.com/winfx/2008/xaml/editors"
        xmlns:dxet="http://schemas.devexpress.com/winfx/2008/xaml/editors/themekeys"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        dx:ThemeManager.ThemeName="Office2019Colorful"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">

    <Window.Resources>

        <DataTemplate x:Key="{dxet:ButtonsThemeKey ResourceKey=SpinRightGlyph, ThemeName=Office2019Colorful}">
            <Grid x:Name="MainGrid" MinWidth="16" Background="Transparent" >
                <Path Fill="{TemplateBinding TextElement.Foreground}" >
                    <Path.Style>
                        <Style TargetType="{x:Type Path}">
                            <Setter Property="Stroke" Value="#FF2C2C2C" />
                            <Setter Property="Height" Value="9" />
                            <Setter Property="Width" Value="15" />
                            <Setter Property="StrokeThickness" Value="2" />
                            <Setter Property="UseLayoutRounding" Value="True" />
                            <Setter Property="StrokeLineJoin" Value="Round" />
                            <Setter Property="Margin" Value="10,5,10,5" />
                            <Setter Property="HorizontalAlignment" Value="Center" />
                            <Setter Property="VerticalAlignment" Value="Center" />

                            <Setter Property="Data">
                                <Setter.Value>
                                    <PathGeometry>
                                        <PathFigure IsFilled="False" StartPoint="2,7">
                                            <PolyLineSegment Points="7.5,1.5 13,7"/>
                                        </PathFigure>
                                    </PathGeometry>
                                </Setter.Value>
                            </Setter>
                        </Style>
                    </Path.Style>
                </Path>
            </Grid>

            <DataTemplate.Triggers>
                <Trigger Property="dx:ThemeManager.IsTouchEnabled" Value="True">
                    <Setter Property="MinWidth"
                            TargetName="MainGrid"
                            Value="42" />
                </Trigger>

                <Trigger Property="IsMouseOver" Value="True">
                    <Setter TargetName="MainGrid" Property="Background" Value="#FF919699" />
                </Trigger>
                <Trigger Property="IsFocused" Value="True">
                    <Setter TargetName="MainGrid" Property="Background" Value="#FF919699" />
                </Trigger>

            </DataTemplate.Triggers>
        </DataTemplate>

        <DataTemplate x:Key="{dxet:ButtonsThemeKey ResourceKey=SpinLeftGlyph, ThemeName=Office2019Colorful}">
            <Grid x:Name="MainGrid" MinWidth="16" Background="Transparent">
                <Path Fill="{TemplateBinding TextElement.Foreground}"  >
                    <Path.Style>
                        <Style TargetType="{x:Type Path}">
                            <Setter Property="Stroke" Value="#FF2C2C2C" />
                            <Setter Property="Height" Value="9" />
                            <Setter Property="Width" Value="15" />
                            <Setter Property="StrokeThickness" Value="2" />
                            <Setter Property="UseLayoutRounding" Value="True" />
                            <Setter Property="StrokeLineJoin" Value="Round" />
                            <Setter Property="Margin" Value="10,5,10,5" />
                            <Setter Property="HorizontalAlignment" Value="Center" />
                            <Setter Property="VerticalAlignment" Value="Center" />

                            <Setter Property="Data">
                                <Setter.Value>
                                    <PathGeometry>
                                        <PathFigure IsFilled="False" StartPoint="2,1.5">
                                            <PolyLineSegment Points="7.5,7 13,1.5"/>
                                        </PathFigure>
                                    </PathGeometry>
                                </Setter.Value>
                            </Setter>

                        </Style>
                    </Path.Style>
                </Path>
            </Grid>
            <DataTemplate.Triggers>
                <Trigger Property="dx:ThemeManager.IsTouchEnabled" Value="True">
                    <Setter Property="MinWidth"
                            TargetName="MainGrid"
                            Value="42" />
                </Trigger>

                <Trigger Property="IsMouseOver" Value="True">
                    <Setter TargetName="MainGrid" Property="Background" Value="#FF919699" />
                </Trigger>
                <Trigger Property="IsFocused" Value="True">
                    <Setter TargetName="MainGrid" Property="Background" Value="#FF919699" />
                </Trigger>
            </DataTemplate.Triggers>
        </DataTemplate>

    </Window.Resources>


    <Border VerticalAlignment="Top" >

        <Border x:Name="border"  >

            <StackPanel VerticalAlignment="Top">

                <TextBox Background="Bisque" Width="200" HorizontalAlignment="Left" Height="30"/>


                <dxe:SpinEdit  x:Name="tboValue" 
                               Margin="0,24,0,0" 
                               Padding="10,0,10,0" 
                               Value="50" 
                               Height="30" 
                               Width="158" 
                               FontSize="16" 
                               FontWeight="SemiBold" 
                               HorizontalAlignment="Left" 
                               VerticalAlignment="Top"
                               dxe:HorizontalContentAlignment="Left" 
                               dxe:VerticalContentAlignment="Center"
                               AllowDefaultButton="False" 
                               dxe:NumericMaskOptions.AlwaysShowDecimalSeparator="False"
                               Background="#FFFAF5F5" 
                               CornerRadius="3" 
                               BorderThickness="0,0,0,3"  
                               BorderBrush="Transparent" >

                    <VisualStateManager.VisualStateGroups>
                        <VisualStateGroup x:Name="CommonStates">
                            <VisualState x:Name="Normal" >
                                <Storyboard>
                                    <ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(dxe:SpinEdit.BorderBrush)" Storyboard.TargetName="tboValue">
                                        <DiscreteObjectKeyFrame KeyTime="0">
                                            <DiscreteObjectKeyFrame.Value>
                                                <SolidColorBrush Color="Transparent"/>
                                            </DiscreteObjectKeyFrame.Value>
                                        </DiscreteObjectKeyFrame>
                                    </ObjectAnimationUsingKeyFrames>

                                    <ThicknessAnimationUsingKeyFrames Storyboard.TargetProperty="(dxe:SpinEdit.BorderThickness)" Storyboard.TargetName="tboValue">
                                        <EasingThicknessKeyFrame KeyTime="0" Value="0,0,0,0.1"/>
                                    </ThicknessAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>

                            <VisualState x:Name="MouseOver">
                                <Storyboard>
                                    <ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(dxe:SpinEdit.BorderBrush)" Storyboard.TargetName="tboValue">
                                        <DiscreteObjectKeyFrame KeyTime="0">
                                            <DiscreteObjectKeyFrame.Value>
                                                <SolidColorBrush Color="Purple"/>
                                            </DiscreteObjectKeyFrame.Value>
                                        </DiscreteObjectKeyFrame>
                                    </ObjectAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>

                            <VisualState x:Name="Pressed">
                                <Storyboard>
                                </Storyboard>
                            </VisualState>

                            <VisualState x:Name="Selected" >
                                <Storyboard>
                                    <ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(dxe:SpinEdit.BorderBrush)" Storyboard.TargetName="tboValue">
                                        <DiscreteObjectKeyFrame KeyTime="0">
                                            <DiscreteObjectKeyFrame.Value>
                                                <SolidColorBrush Color="Yellow"/>
                                            </DiscreteObjectKeyFrame.Value>
                                        </DiscreteObjectKeyFrame>
                                    </ObjectAnimationUsingKeyFrames>

                                    <ThicknessAnimationUsingKeyFrames Storyboard.TargetProperty="(dxe:SpinEdit.BorderThickness)" Storyboard.TargetName="tboValue">
                                        <EasingThicknessKeyFrame KeyTime="0" Value="0,0,0,3"/>
                                    </ThicknessAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>
                        </VisualStateGroup>

                        <VisualStateGroup x:Name="FocusStates">
                            <VisualState x:Name="Focused" >
                                <Storyboard>
                                    <ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(dxe:SpinEdit.BorderBrush)" Storyboard.TargetName="tboValue">
                                        <DiscreteObjectKeyFrame KeyTime="0">
                                            <DiscreteObjectKeyFrame.Value>
                                                <SolidColorBrush Color="Red"/>
                                            </DiscreteObjectKeyFrame.Value>
                                        </DiscreteObjectKeyFrame>
                                    </ObjectAnimationUsingKeyFrames>

                                    <ThicknessAnimationUsingKeyFrames Storyboard.TargetProperty="(dxe:SpinEdit.BorderThickness)" Storyboard.TargetName="tboValue">
                                        <EasingThicknessKeyFrame KeyTime="0" Value="0,0,0,3"/>
                                    </ThicknessAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>

                            <VisualState x:Name="Unfocused" >
                                <Storyboard>
                                    <ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(dxe:SpinEdit.BorderBrush)" Storyboard.TargetName="tboValue">
                                        <DiscreteObjectKeyFrame KeyTime="0">
                                            <DiscreteObjectKeyFrame.Value>
                                                <SolidColorBrush Color="Green"/>
                                            </DiscreteObjectKeyFrame.Value>
                                        </DiscreteObjectKeyFrame>
                                    </ObjectAnimationUsingKeyFrames>

                                    <ThicknessAnimationUsingKeyFrames Storyboard.TargetProperty="(dxe:SpinEdit.BorderThickness)" Storyboard.TargetName="tboValue">
                                        <EasingThicknessKeyFrame KeyTime="0" Value="0,0,0,3"/>
                                    </ThicknessAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>
                        </VisualStateGroup>

                    </VisualStateManager.VisualStateGroups>
                    <dxe:SpinButtonInfo IsDefaultButton="True" SpinStyle="Horizontal" Margin="0,0,5,0" />
                    <dxe:ButtonInfo Margin="0,0,0,0"  />

                </dxe:SpinEdit>
            </StackPanel>
        </Border>

    </Border>

</Window>
