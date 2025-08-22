# How to work with checkboxes in unbound mode in WPF TreeView

This example describes how to work with check boxes in unbound mode in [WPF TreeView](https://www.syncfusion.com/wpf-controls/treeview) (SfTreeView). 

You can directly set the checkbox state by setting the [TreeViewNode.IsChecked](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html#Syncfusion_UI_Xaml_TreeView_Engine_TreeViewNode_IsChecked) property value while creating nodes.

``` xml
<Window 
    x:Class="TreeNodeWithCheckBoxDemo.Window1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="clr-namespace:TreeNodeWithCheckBoxDemo"
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
    xmlns:Engine="clr-namespace:Syncfusion.UI.Xaml.TreeView.Engine;assembly=Syncfusion.SfTreeView.WPF"
    Title="Node With CheckBox"
    Width="450"
    Height="500"
    Icon="App.ico"
    WindowStartupLocation="CenterScreen">
    <Grid>
        <syncfusion:SfTreeView x:Name="sfTreeView"
                                Width="400"
                                Margin="10,10,10,10"
                                BorderThickness="1"
                                BorderBrush="LightGray"
                                IsAnimationEnabled="True"
                                ItemTemplateDataContextType="Node" 
                                CheckBoxMode="Recursive" >
            <syncfusion:SfTreeView.Nodes>
                <Engine:TreeViewNode Content="Grains" IsExpanded="True" IsChecked="True">
                    <Engine:TreeViewNode.ChildNodes>
                        <Engine:TreeViewNode Content="Cereals" IsExpanded="True">
                            <Engine:TreeViewNode.ChildNodes>
                                <Engine:TreeViewNode Content="Rice" IsChecked="True"/>
                                <Engine:TreeViewNode Content="Barley"/>
                            </Engine:TreeViewNode.ChildNodes>
                        </Engine:TreeViewNode>
                        <Engine:TreeViewNode Content="Oilseeds">
                            <Engine:TreeViewNode.ChildNodes>
                                <Engine:TreeViewNode Content="Safflower" IsChecked="True"/>
                            </Engine:TreeViewNode.ChildNodes>
                        </Engine:TreeViewNode>
                    </Engine:TreeViewNode.ChildNodes>
                </Engine:TreeViewNode>
                <Engine:TreeViewNode Content="Fruits" IsExpanded="true">
                    <Engine:TreeViewNode.ChildNodes>
                        <Engine:TreeViewNode Content="Orange" IsChecked="True"/>
                        <Engine:TreeViewNode Content="Apples" IsExpanded="true"/>
                    </Engine:TreeViewNode.ChildNodes>
                </Engine:TreeViewNode>
                <Engine:TreeViewNode Content="Vegetables" IsExpanded="true" IsChecked="True">
                    <Engine:TreeViewNode.ChildNodes>
                        <Engine:TreeViewNode Content="Root Vegetables" IsExpanded="true">
                            <Engine:TreeViewNode.ChildNodes>
                                <Engine:TreeViewNode Content="Potato" IsChecked="True"/>
                                <Engine:TreeViewNode Content="Carrot"/>
                            </Engine:TreeViewNode.ChildNodes>
                        </Engine:TreeViewNode>
                        <Engine:TreeViewNode Content="Podded">
                            <Engine:TreeViewNode.ChildNodes>
                                <Engine:TreeViewNode Content="Peanut" IsChecked="True"/>
                                <Engine:TreeViewNode Content="Lentil"/>
                            </Engine:TreeViewNode.ChildNodes>
                        </Engine:TreeViewNode>
                    </Engine:TreeViewNode.ChildNodes>
                </Engine:TreeViewNode>
            </syncfusion:SfTreeView.Nodes>
            <syncfusion:SfTreeView.ItemTemplate>
                <DataTemplate>
                    <Grid>
                        <CheckBox x:Name="CheckBox" FocusVisualStyle="{x:Null}"
                                            IsChecked="{Binding IsChecked, Mode=TwoWay}" Content="{Binding Content}"/>

                    </Grid>
                </DataTemplate>
            </syncfusion:SfTreeView.ItemTemplate>
        </syncfusion:SfTreeView>
    </Grid>
</Window>
```