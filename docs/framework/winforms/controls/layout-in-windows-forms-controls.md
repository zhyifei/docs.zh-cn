---
title: "Windows 窗体控件的布局"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- layout [Windows Forms]
- sizing [Windows Forms], automatic [Windows Forms]
- Margin property [Windows Forms]
- Padding property [Windws Forms]
ms.assetid: 99400e3a-720e-4f56-b68f-89df911a251c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6244b21c2729df3bfe5899a4f4970f4b48030057
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="layout-in-windows-forms-controls"></a><span data-ttu-id="96e20-102">Windows 窗体控件的布局</span><span class="sxs-lookup"><span data-stu-id="96e20-102">Layout in Windows Forms Controls</span></span>
<span data-ttu-id="96e20-103">在窗体上精确地放置控件对于许多应用程序而言是高优先级。</span><span class="sxs-lookup"><span data-stu-id="96e20-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="96e20-104"><xref:System.Windows.Forms?displayProperty=nameWithType>命名空间为你提供许多布局工具实现此目的。</span><span class="sxs-lookup"><span data-stu-id="96e20-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout tools to accomplish this.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96e20-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="96e20-105">In This Section</span></span>  
 [<span data-ttu-id="96e20-106">AutoSize 属性概述</span><span class="sxs-lookup"><span data-stu-id="96e20-106">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 <span data-ttu-id="96e20-107">描述<xref:System.Windows.Forms.Control.AutoSize%2A>属性和它在布局中的作用。</span><span class="sxs-lookup"><span data-stu-id="96e20-107">Describes the <xref:System.Windows.Forms.Control.AutoSize%2A> property and its role in layout.</span></span>  
  
 [<span data-ttu-id="96e20-108">Windows 窗体控件中的边距和填充</span><span class="sxs-lookup"><span data-stu-id="96e20-108">Margin and Padding in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)  
 <span data-ttu-id="96e20-109">描述<xref:System.Windows.Forms.Control.Margin%2A>和<xref:System.Windows.Forms.Control.Padding%2A>属性和布局中的其角色。</span><span class="sxs-lookup"><span data-stu-id="96e20-109">Describes the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties and their roles in layout.</span></span>  
  
 [<span data-ttu-id="96e20-110">如何：让控件与窗体边缘对齐</span><span class="sxs-lookup"><span data-stu-id="96e20-110">How to: Align a Control to the Edges of Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)  
 <span data-ttu-id="96e20-111">演示如何使用<xref:System.Windows.Forms.Control.Dock%2A>属性以你控件与它所占据窗体边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="96e20-111">Demonstrates how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>  
  
 [<span data-ttu-id="96e20-112">如何：使用填充在 Windows 窗体控件周围创建边框</span><span class="sxs-lookup"><span data-stu-id="96e20-112">How to: Create a Border Around a Windows Forms Control Using Padding</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-border-around-a-windows-forms-control-using-padding.md)  
 <span data-ttu-id="96e20-113">演示如何使用<xref:System.Windows.Forms.Control.Padding%2A>属性来创建控件的轮廓。</span><span class="sxs-lookup"><span data-stu-id="96e20-113">Demonstrates how to use the <xref:System.Windows.Forms.Control.Padding%2A> property to outline a control.</span></span>  
  
 [<span data-ttu-id="96e20-114">如何：实现自定义布局引擎</span><span class="sxs-lookup"><span data-stu-id="96e20-114">How to: Implement a Custom Layout Engine</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-layout-engine.md)  
 <span data-ttu-id="96e20-115">演示如何实现<xref:System.Windows.Forms.Layout.LayoutEngine>用于排列 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="96e20-115">Demonstrates how to implement a <xref:System.Windows.Forms.Layout.LayoutEngine> for arranging Windows Forms controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="96e20-116">参考</span><span class="sxs-lookup"><span data-stu-id="96e20-116">Reference</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <span data-ttu-id="96e20-117">提供关于 <xref:System.Windows.Forms.TableLayoutPanel> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="96e20-117">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <span data-ttu-id="96e20-118">提供关于 <xref:System.Windows.Forms.FlowLayoutPanel> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="96e20-118">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e20-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96e20-119">See Also</span></span>  
 [<span data-ttu-id="96e20-120">如何：在 FlowLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="96e20-120">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [<span data-ttu-id="96e20-121">如何：在 TableLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="96e20-121">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="96e20-122">如何：设计非常适合本地化的 Windows 窗体布局</span><span class="sxs-lookup"><span data-stu-id="96e20-122">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [<span data-ttu-id="96e20-123">TableLayoutPanel 控件中的自动调整大小行为</span><span class="sxs-lookup"><span data-stu-id="96e20-123">AutoSize Behavior in the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/autosize-behavior-in-the-tablelayoutpanel-control.md)
