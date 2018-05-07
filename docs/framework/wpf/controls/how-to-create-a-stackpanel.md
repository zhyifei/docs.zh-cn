---
title: 如何：创建 StackPanel
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: 30f24d8dba7c09271a5957822439af6b64e05aca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-stackpanel"></a>如何：创建 StackPanel
此示例演示如何创建<xref:System.Windows.Controls.StackPanel>。  
  
## <a name="example"></a>示例  
 A<xref:System.Windows.Controls.StackPanel>允许你堆栈指定方向中的元素。 通过使用定义的属性<xref:System.Windows.Controls.StackPanel>，内容可以同时垂直排列，这是默认设置，还是水平。  
  
 下面的示例垂直堆栈五个<xref:System.Windows.Controls.TextBlock>控件，每个替换为其他<xref:System.Windows.Controls.Border>和<xref:System.Windows.Controls.Border.Background%2A>，通过使用<xref:System.Windows.Controls.StackPanel>。 没有指定的子元素<xref:System.Windows.FrameworkElement.Width%2A>拉伸以填充父窗口; 但是，子元素具有指定<xref:System.Windows.FrameworkElement.Width%2A>，在窗口内居中。  
  
 中的默认堆栈方向<xref:System.Windows.Controls.StackPanel>为垂直。 控件中的内容流到<xref:System.Windows.Controls.StackPanel>，使用<xref:System.Windows.Controls.StackPanel.Orientation%2A>属性。 你可以通过使用控制水平对齐方式<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性。  
  
```xaml  
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" WindowTitle="StackPanel Sample">  
  <StackPanel>  
    <Border Background="SkyBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="12">Stacked Item #1</TextBlock>  
    </Border>  
    <Border Width="400" Background="CadetBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="14">Stacked Item #2</TextBlock>  
    </Border>  
    <Border Background="LightGoldenRodYellow" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="16">Stacked Item #3</TextBlock>  
    </Border>  
    <Border Width="200" Background="PaleGreen" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="18">Stacked Item #4</TextBlock>  
    </Border>  
    <Border Background="White" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="20">Stacked Item #5</TextBlock>  
    </Border>  
  </StackPanel>  
</Page>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.StackPanel>  
 [面板概述](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/controls/stackpanel-how-to-topics.md)
