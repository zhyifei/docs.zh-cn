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
ms.locfileid: "33553022"
---
# <a name="how-to-create-a-stackpanel"></a><span data-ttu-id="c7505-102">如何：创建 StackPanel</span><span class="sxs-lookup"><span data-stu-id="c7505-102">How to: Create a StackPanel</span></span>
<span data-ttu-id="c7505-103">此示例演示如何创建<xref:System.Windows.Controls.StackPanel>。</span><span class="sxs-lookup"><span data-stu-id="c7505-103">This example shows how to create a <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7505-104">示例</span><span class="sxs-lookup"><span data-stu-id="c7505-104">Example</span></span>  
 <span data-ttu-id="c7505-105">A<xref:System.Windows.Controls.StackPanel>允许你堆栈指定方向中的元素。</span><span class="sxs-lookup"><span data-stu-id="c7505-105">A <xref:System.Windows.Controls.StackPanel> allows you to stack elements in a specified direction.</span></span> <span data-ttu-id="c7505-106">通过使用定义的属性<xref:System.Windows.Controls.StackPanel>，内容可以同时垂直排列，这是默认设置，还是水平。</span><span class="sxs-lookup"><span data-stu-id="c7505-106">By using properties that are defined on <xref:System.Windows.Controls.StackPanel>, content can flow both vertically, which is the default setting, or horizontally.</span></span>  
  
 <span data-ttu-id="c7505-107">下面的示例垂直堆栈五个<xref:System.Windows.Controls.TextBlock>控件，每个替换为其他<xref:System.Windows.Controls.Border>和<xref:System.Windows.Controls.Border.Background%2A>，通过使用<xref:System.Windows.Controls.StackPanel>。</span><span class="sxs-lookup"><span data-stu-id="c7505-107">The following example vertically stacks five <xref:System.Windows.Controls.TextBlock> controls, each with a different <xref:System.Windows.Controls.Border> and <xref:System.Windows.Controls.Border.Background%2A>, by using <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="c7505-108">没有指定的子元素<xref:System.Windows.FrameworkElement.Width%2A>拉伸以填充父窗口; 但是，子元素具有指定<xref:System.Windows.FrameworkElement.Width%2A>，在窗口内居中。</span><span class="sxs-lookup"><span data-stu-id="c7505-108">The child elements that have no specified <xref:System.Windows.FrameworkElement.Width%2A> stretch to fill the parent window; however, the child elements that have a specified <xref:System.Windows.FrameworkElement.Width%2A>, are centered within the window.</span></span>  
  
 <span data-ttu-id="c7505-109">中的默认堆栈方向<xref:System.Windows.Controls.StackPanel>为垂直。</span><span class="sxs-lookup"><span data-stu-id="c7505-109">The default stack direction in a <xref:System.Windows.Controls.StackPanel> is vertical.</span></span> <span data-ttu-id="c7505-110">控件中的内容流到<xref:System.Windows.Controls.StackPanel>，使用<xref:System.Windows.Controls.StackPanel.Orientation%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="c7505-110">To control content flow in a <xref:System.Windows.Controls.StackPanel>, use the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property.</span></span> <span data-ttu-id="c7505-111">你可以通过使用控制水平对齐方式<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="c7505-111">You can control horizontal alignment by using the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c7505-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7505-112">See Also</span></span>  
 <xref:System.Windows.Controls.StackPanel>  
 [<span data-ttu-id="c7505-113">面板概述</span><span class="sxs-lookup"><span data-stu-id="c7505-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="c7505-114">帮助主题</span><span class="sxs-lookup"><span data-stu-id="c7505-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/stackpanel-how-to-topics.md)
