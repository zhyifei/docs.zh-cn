---
title: Windows Presentation Foundation 客户端中的数据绑定
ms.date: 03/30/2017
ms.assetid: bb8c8293-5973-4aef-9b07-afeff5d3293c
ms.openlocfilehash: 7bc389056872841905336dcf658a07223906bf82
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183825"
---
# <a name="data-binding-in-a-windows-presentation-foundation-client"></a>Windows Presentation Foundation 客户端中的数据绑定
本示例演示 Windows Presentation Foundation (WPF) 客户端中数据绑定的用法。 该示例使用 Windows 通信基础 （WCF） 服务，该服务随机生成相册数组以返回到客户端。 每个唱片集都有名称、价格和唱片集曲目列表。 唱片集曲目具有名称和持续时间。 服务返回的信息将自动绑定到 Windows 演示基础 （WPF） 客户端提供的用户界面 （UI）。  
  
> [!NOTE]
> 本主题的最后介绍了此示例的设置过程和生成说明。  
  
 使用数据绑定可以将数据源自动绑定到 UI。 这简化了编程模型，因为它不需要您以编程方式使用数据对象中的数据或数据对象数组中的数据更新每个 UI 元素。 您可以将对象绑定到单个 UI 元素或将数组绑定到采用多个输入的控件（如 `ListBox`）。 下面的代码演示如何将数据绑定到 UI 元素的 `DataContext`。  
  
```csharp  
// Event handler executed when call is complete  
void client_GetAlbumListCompleted(object sender, GetAlbumListCompletedEventArgs e)  
{  
    // This is on the UI thread, myPanel can be accessed directly  
    myPanel.DataContext = e.Result;
}  
```  
  
 在前面的示例中，将名为 `DataContext` 的 `grid` 布局元素的 `myPanel` 设置为 `GetAlbumList` 方法返回的数据。 `DataContext` 使元素可以从它们的父元素继承有关用于绑定的数据源以及绑定的其他特征（例如路径）的信息。 每次更新服务器上的数据时，必须执行该代码行。 例如，初始化窗口时和添加新唱片集时执行该代码行。  
  
 在下面的示例 XAML 代码中，`ListBox` 指定 `ItemsSource="{Binding }"`。  
  
```xml  
<ListBox
          ItemTemplate="{StaticResource AlbumStyle}"  
          ItemsSource="{Binding }"
          IsSynchronizedWithCurrentItem="true" />  
```  
  
 这将指定绑定到顶级 UI 元素的数据也绑定到此控件（即唱片集数组）。 此外，`ItemTemplate="{StaticResource AlbumStyle}"` 指定将用于 `ListBox` 中每个项的数据模板。 您也可以定义数据模板以指定应如何格式化数据。 应用程序中的其他 UI 元素可以重复使用这些数据模板，优点是在同一位置定义和维护数据模板。  
  
 `AlbumStyle` 数据模板并排使用两个 `TextBlock` 布置网格。 一个指定唱片集的名称，另一个指定唱片集中的曲目数。  
  
```xaml  
<DataTemplate x:Key="AlbumStyle">  
    <Grid>  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition Width="260" />  
            <ColumnDefinition Width="60" />  
        </Grid.ColumnDefinitions>  
        <TextBlock Grid.Column="0" TextContent="{Binding Path=Title}" />  
        <TextBlock Grid.Column="1" TextContent="{Binding Path=Tracks#.Count}" HorizontalAlignment="Right" />  
    </Grid>  
</DataTemplate>  
```  
  
 下面的 XAML 代码创建另一个 `ListBox`。  
  
```xaml  
<ListBox Grid.Row="2"
            Grid.ColumnSpan="2"
            ItemTemplate="{StaticResource TrackStyle}"  
            ItemsSource="{Binding Path=Tracks}" />  
```  
  
 该代码指定 `ItemsSource` 的路径。 这表示绑定到此控件的数据不是顶级数据，而是名为 `Tracks` 的顶级数据的属性。 此属性表示唱片集内包含的曲目数组。 此外，指定了名为 `DataTemplate` 的另一个 `TrackStyle`。 `TrackStyle` 模板的布局类似于 `AlbumStyle` 模板的布局，但 `TextBlock` 绑定到不同的属性。 这是因为两个模板用于不同的数据对象。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1. 确保已为 Windows[通信基础示例执行一次性设置过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2. 若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。  
  
3. 要在单机或跨计算机配置中运行示例，请按照[运行 Windows 通信基础示例中的](../../../../docs/framework/wcf/samples/running-the-samples.md)说明操作。  
  
> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。 此示例位于以下目录：  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WPFDataBinding`  
