---
title: "Windows 窗体控件中的边距和填充"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Padding property [Windows Forms]
- layout [Windows Forms], margins and padding
- Windows Forms, layout
- Margin property [Windows Forms]
ms.assetid: 3781b5a1-3085-4072-bed0-44670c23ffdc
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 28092704d3c7eaa4820bf6dcbc1678f806ac213e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="margin-and-padding-in-windows-forms-controls"></a><span data-ttu-id="a2e7e-102">Windows 窗体控件中的边距和填充</span><span class="sxs-lookup"><span data-stu-id="a2e7e-102">Margin and Padding in Windows Forms Controls</span></span>
<span data-ttu-id="a2e7e-103">在窗体上精确地放置控件对于许多应用程序而言是高优先级。</span><span class="sxs-lookup"><span data-stu-id="a2e7e-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="a2e7e-104"><xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间给你提供许多布局功能来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="a2e7e-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout features to accomplish this.</span></span> <span data-ttu-id="a2e7e-105">其中两个最重要的功能是 <xref:System.Windows.Forms.Control.Margin%2A> 和 <xref:System.Windows.Forms.Control.Padding%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="a2e7e-105">Two of the most important are the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties.</span></span>  
  
 <span data-ttu-id="a2e7e-106"><xref:System.Windows.Forms.Control.Margin%2A> 属性定义控件周围的空间，该空间使其他控件与该控件的边框保持指定的距离。</span><span class="sxs-lookup"><span data-stu-id="a2e7e-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="a2e7e-107"><xref:System.Windows.Forms.Control.Padding%2A> 属性定义控件内部的空间，该空间使控件的内容（例如，其 <xref:System.Windows.Forms.Control.Text%2A> 属性的值）与该控件的边框保持指定的距离。</span><span class="sxs-lookup"><span data-stu-id="a2e7e-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="a2e7e-108">下图显示控件上的 <xref:System.Windows.Forms.Control.Padding%2A> 和 <xref:System.Windows.Forms.Control.Margin%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="a2e7e-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>  
  
 <span data-ttu-id="a2e7e-109">![填充和边距适用于 Windows 窗体控件](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span><span class="sxs-lookup"><span data-stu-id="a2e7e-109">![Padding And Margin for Windows Forms Controls](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span></span>  
  
 <span data-ttu-id="a2e7e-110">Visual Studio 中具有对此功能的设计时支持。</span><span class="sxs-lookup"><span data-stu-id="a2e7e-110">There is design-time support for this feature in Visual Studio.</span></span>  <span data-ttu-id="a2e7e-111">另请参阅[演练： 设计出 Windows 窗体控件与 Padding、 Margins 和 AutoSize 属性](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="a2e7e-111">Also see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2e7e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2e7e-112">See Also</span></span>  
 <xref:System.Windows.Forms.Control.AutoSize%2A>  
 <xref:System.Windows.Forms.Control.Margin%2A>  
 <xref:System.Windows.Forms.Control.Padding%2A>  
 <xref:System.Windows.Forms.Control.LayoutEngine%2A>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>
