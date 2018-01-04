---
title: "如何：使控件与窗体边缘对齐"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock property [Windows Forms], aligning controls (using code)
- forms [Windows Forms], aligning controls
- controls [Windows Forms], aligning on forms
- custom controls [Windows Forms], docking using code
ms.assetid: 5994cb59-242b-4e75-bd0e-62879c34d702
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7979b58d52c6df7341259af50a39e104781dd148
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-align-a-control-to-the-edges-of-forms"></a><span data-ttu-id="e51ff-102">如何：使控件与窗体边缘对齐</span><span class="sxs-lookup"><span data-stu-id="e51ff-102">How to: Align a Control to the Edges of Forms</span></span>
<span data-ttu-id="e51ff-103">通过设置 <xref:System.Windows.Forms.Control.Dock%2A> 属性，可以使控件与窗体的边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="e51ff-103">You can make your control align to the edge of your forms by setting the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span> <span data-ttu-id="e51ff-104">此属性指定控件在窗体中的驻留位置。</span><span class="sxs-lookup"><span data-stu-id="e51ff-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="e51ff-105">可以将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为下列值：</span><span class="sxs-lookup"><span data-stu-id="e51ff-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>  
  
|<span data-ttu-id="e51ff-106">设置</span><span class="sxs-lookup"><span data-stu-id="e51ff-106">Setting</span></span>|<span data-ttu-id="e51ff-107">控件上的效果</span><span class="sxs-lookup"><span data-stu-id="e51ff-107">Effect on your control</span></span>|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="e51ff-108">停靠到窗体底部。</span><span class="sxs-lookup"><span data-stu-id="e51ff-108">Docks to the bottom of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="e51ff-109">占据窗体中的所有剩余空间。</span><span class="sxs-lookup"><span data-stu-id="e51ff-109">Fills all remaining space in the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="e51ff-110">停靠到窗体的左侧。</span><span class="sxs-lookup"><span data-stu-id="e51ff-110">Docks to the left side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="e51ff-111">不在任何位置停靠，它显示在由 <xref:System.Windows.Forms.Control.Location%2A> 属性指定的位置。</span><span class="sxs-lookup"><span data-stu-id="e51ff-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="e51ff-112">停靠到窗体的右侧。</span><span class="sxs-lookup"><span data-stu-id="e51ff-112">Docks to the right side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="e51ff-113">停靠到窗体的顶部。</span><span class="sxs-lookup"><span data-stu-id="e51ff-113">Docks to the top of the form.</span></span>|  
  
 <span data-ttu-id="e51ff-114">Visual Studio 中具有对此功能的设计时支持。</span><span class="sxs-lookup"><span data-stu-id="e51ff-114">There is design-time support for this feature in Visual Studio.</span></span>  
  
### <a name="to-set-the-dock-property-for-your-control-at-run-time"></a><span data-ttu-id="e51ff-115">在运行时设置控件的 Dock 属性</span><span class="sxs-lookup"><span data-stu-id="e51ff-115">To set the Dock property for your control at run time</span></span>  
  
1.  <span data-ttu-id="e51ff-116">在代码中将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="e51ff-116">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to the appropriate value in code.</span></span>  
  
    ```vb  
    ' To set the Dock property internally.  
    Me.Dock = DockStyle.Top  
    ' To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top  
    ```  
  
    ```csharp  
    // To set the Dock property internally.  
    this.Dock = DockStyle.Top;  
    // To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e51ff-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e51ff-117">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="e51ff-118">使用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="e51ff-118">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="e51ff-119">如何：在 FlowLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="e51ff-119">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [<span data-ttu-id="e51ff-120">如何：在 TableLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="e51ff-120">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="e51ff-121">AutoSize 属性概述</span><span class="sxs-lookup"><span data-stu-id="e51ff-121">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)
