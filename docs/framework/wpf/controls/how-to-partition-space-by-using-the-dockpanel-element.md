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
ms.openlocfilehash: d22a808ce3ab95e3b351408bf4cc372a335da553
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960188"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="df7ab-102">如何：使用 DockPanel 元素对空间进行分区</span><span class="sxs-lookup"><span data-stu-id="df7ab-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="df7ab-103">下面的示例<xref:System.Windows.Controls.DockPanel>使用元素创建[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]一个简单框架。</span><span class="sxs-lookup"><span data-stu-id="df7ab-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="df7ab-104">将<xref:System.Windows.Controls.DockPanel>可用空间分区给其子元素。</span><span class="sxs-lookup"><span data-stu-id="df7ab-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df7ab-105">示例</span><span class="sxs-lookup"><span data-stu-id="df7ab-105">Example</span></span>  
 <span data-ttu-id="df7ab-106">此示例使用<xref:System.Windows.Controls.DockPanel.Dock%2A>属性, 该属性是一个附加属性, 用于将两个<xref:System.Windows.Controls.Border>相同的元素<xref:System.Windows.Controls.Dock.Top>停靠在分区空间的上。</span><span class="sxs-lookup"><span data-stu-id="df7ab-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="df7ab-107">第三<xref:System.Windows.Controls.Border>个元素停靠<xref:System.Windows.Controls.Dock.Left>到, 其宽度设置为200像素。</span><span class="sxs-lookup"><span data-stu-id="df7ab-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="df7ab-108">第四<xref:System.Windows.Controls.Border>个停靠<xref:System.Windows.Controls.Dock.Bottom>到屏幕的。</span><span class="sxs-lookup"><span data-stu-id="df7ab-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="df7ab-109">最后一个<xref:System.Windows.Controls.Border>元素自动填充剩余的空间。</span><span class="sxs-lookup"><span data-stu-id="df7ab-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
> <span data-ttu-id="df7ab-110">默认情况下, <xref:System.Windows.Controls.DockPanel>元素的最后一个子元素会填充剩余的未分配空间。</span><span class="sxs-lookup"><span data-stu-id="df7ab-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="df7ab-111">如果不希望出现此行为，请设置 `LastChildFill="False"`。</span><span class="sxs-lookup"><span data-stu-id="df7ab-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="df7ab-112">已编译的应用程序将生成如下所示的新 UI。</span><span class="sxs-lookup"><span data-stu-id="df7ab-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="df7ab-113">![典型的 DockPanel 方案。](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="df7ab-113">![A typical DockPanel scenario.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df7ab-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="df7ab-114">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="df7ab-115">面板概述</span><span class="sxs-lookup"><span data-stu-id="df7ab-115">Panels Overview</span></span>](panels-overview.md)
