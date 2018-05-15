---
title: Windows 窗体控件的布局
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- sizing [Windows Forms], automatic [Windows Forms]
- Margin property [Windows Forms]
- Padding property [Windws Forms]
ms.assetid: 99400e3a-720e-4f56-b68f-89df911a251c
ms.openlocfilehash: 11db7b49f37b4367f31b2c27c61225f8f71bde80
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="layout-in-windows-forms-controls"></a><span data-ttu-id="0dc01-102">Windows 窗体控件的布局</span><span class="sxs-lookup"><span data-stu-id="0dc01-102">Layout in Windows Forms Controls</span></span>
<span data-ttu-id="0dc01-103">在窗体上精确地放置控件对于许多应用程序而言是高优先级。</span><span class="sxs-lookup"><span data-stu-id="0dc01-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="0dc01-104"><xref:System.Windows.Forms?displayProperty=nameWithType>命名空间为你提供许多布局工具实现此目的。</span><span class="sxs-lookup"><span data-stu-id="0dc01-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout tools to accomplish this.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0dc01-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="0dc01-105">In This Section</span></span>  
 [<span data-ttu-id="0dc01-106">AutoSize 属性概述</span><span class="sxs-lookup"><span data-stu-id="0dc01-106">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 <span data-ttu-id="0dc01-107">描述<xref:System.Windows.Forms.Control.AutoSize%2A>属性和它在布局中的作用。</span><span class="sxs-lookup"><span data-stu-id="0dc01-107">Describes the <xref:System.Windows.Forms.Control.AutoSize%2A> property and its role in layout.</span></span>  
  
 [<span data-ttu-id="0dc01-108">Windows 窗体控件中的边距和填充</span><span class="sxs-lookup"><span data-stu-id="0dc01-108">Margin and Padding in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)  
 <span data-ttu-id="0dc01-109">描述<xref:System.Windows.Forms.Control.Margin%2A>和<xref:System.Windows.Forms.Control.Padding%2A>属性和布局中的其角色。</span><span class="sxs-lookup"><span data-stu-id="0dc01-109">Describes the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties and their roles in layout.</span></span>  
  
 [<span data-ttu-id="0dc01-110">如何：让控件与窗体边缘对齐</span><span class="sxs-lookup"><span data-stu-id="0dc01-110">How to: Align a Control to the Edges of Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)  
 <span data-ttu-id="0dc01-111">演示如何使用<xref:System.Windows.Forms.Control.Dock%2A>属性以你控件与它所占据窗体边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="0dc01-111">Demonstrates how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>  
  
 [<span data-ttu-id="0dc01-112">如何：使用填充在 Windows 窗体控件周围创建边框</span><span class="sxs-lookup"><span data-stu-id="0dc01-112">How to: Create a Border Around a Windows Forms Control Using Padding</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-border-around-a-windows-forms-control-using-padding.md)  
 <span data-ttu-id="0dc01-113">演示如何使用<xref:System.Windows.Forms.Control.Padding%2A>属性来创建控件的轮廓。</span><span class="sxs-lookup"><span data-stu-id="0dc01-113">Demonstrates how to use the <xref:System.Windows.Forms.Control.Padding%2A> property to outline a control.</span></span>  
  
 [<span data-ttu-id="0dc01-114">如何：实现自定义布局引擎</span><span class="sxs-lookup"><span data-stu-id="0dc01-114">How to: Implement a Custom Layout Engine</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-layout-engine.md)  
 <span data-ttu-id="0dc01-115">演示如何实现<xref:System.Windows.Forms.Layout.LayoutEngine>用于排列 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="0dc01-115">Demonstrates how to implement a <xref:System.Windows.Forms.Layout.LayoutEngine> for arranging Windows Forms controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0dc01-116">参考</span><span class="sxs-lookup"><span data-stu-id="0dc01-116">Reference</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <span data-ttu-id="0dc01-117">提供关于 <xref:System.Windows.Forms.TableLayoutPanel> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="0dc01-117">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <span data-ttu-id="0dc01-118">提供关于 <xref:System.Windows.Forms.FlowLayoutPanel> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="0dc01-118">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc01-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="0dc01-119">See Also</span></span>  
 [<span data-ttu-id="0dc01-120">如何：在 FlowLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="0dc01-120">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [<span data-ttu-id="0dc01-121">如何：在 TableLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="0dc01-121">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="0dc01-122">如何：设计非常适合本地化的 Windows 窗体布局</span><span class="sxs-lookup"><span data-stu-id="0dc01-122">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [<span data-ttu-id="0dc01-123">TableLayoutPanel 控件中的自动调整大小行为</span><span class="sxs-lookup"><span data-stu-id="0dc01-123">AutoSize Behavior in the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/autosize-behavior-in-the-tablelayoutpanel-control.md)
