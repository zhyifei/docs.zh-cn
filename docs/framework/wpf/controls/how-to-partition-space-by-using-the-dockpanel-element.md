---
title: 如何：使用 DockPanel 元素对空间进行分区
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
ms.openlocfilehash: ab51270644bf370944ebc933c765b40c528681c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158881"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="6e507-102">如何：使用 DockPanel 元素对空间进行分区</span><span class="sxs-lookup"><span data-stu-id="6e507-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="6e507-103">下面的示例创建一个简单[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]框架，它使用<xref:System.Windows.Controls.DockPanel>元素。</span><span class="sxs-lookup"><span data-stu-id="6e507-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="6e507-104"><xref:System.Windows.Controls.DockPanel>分区到其子元素可用空间。</span><span class="sxs-lookup"><span data-stu-id="6e507-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e507-105">示例</span><span class="sxs-lookup"><span data-stu-id="6e507-105">Example</span></span>  
 <span data-ttu-id="6e507-106">此示例使用<xref:System.Windows.Controls.DockPanel.Dock%2A>属性，它是附加的属性，若要将两个相同停靠<xref:System.Windows.Controls.Border>元素出现在<xref:System.Windows.Controls.Dock.Top>的已分区的空间。</span><span class="sxs-lookup"><span data-stu-id="6e507-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="6e507-107">第三个<xref:System.Windows.Controls.Border>元素停靠至<xref:System.Windows.Controls.Dock.Left>，其宽度设置为 200 像素。</span><span class="sxs-lookup"><span data-stu-id="6e507-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="6e507-108">第四个<xref:System.Windows.Controls.Border>停靠到<xref:System.Windows.Controls.Dock.Bottom>的屏幕。</span><span class="sxs-lookup"><span data-stu-id="6e507-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="6e507-109">最后一个<xref:System.Windows.Controls.Border>元素将自动填充剩余的空间。</span><span class="sxs-lookup"><span data-stu-id="6e507-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  <span data-ttu-id="6e507-110">默认情况下的最后一个子级<xref:System.Windows.Controls.DockPanel>元素填充剩余的未分配空间。</span><span class="sxs-lookup"><span data-stu-id="6e507-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="6e507-111">如果不希望出现此行为，请设置 `LastChildFill="False"`。</span><span class="sxs-lookup"><span data-stu-id="6e507-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="6e507-112">已编译的应用程序将生成如下所示的新 UI。</span><span class="sxs-lookup"><span data-stu-id="6e507-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="6e507-113">![典型的 DockPanel 方案。](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="6e507-113">![A typical DockPanel scenario.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e507-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e507-114">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="6e507-115">面板概述</span><span class="sxs-lookup"><span data-stu-id="6e507-115">Panels Overview</span></span>](panels-overview.md)
