---
title: 如何：更改 Windows 窗体 ToolTip 组件的延迟
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: cf257cccd272c16c3d7c3d403456265444fc8ac8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59345477"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a><span data-ttu-id="8b50f-102">如何：更改 Windows 窗体 ToolTip 组件的延迟</span><span class="sxs-lookup"><span data-stu-id="8b50f-102">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>
<span data-ttu-id="8b50f-103">有多个可以设置为 Windows 窗体的延迟值<xref:System.Windows.Forms.ToolTip>组件。</span><span class="sxs-lookup"><span data-stu-id="8b50f-103">There are multiple delay values that you can set for a Windows Forms <xref:System.Windows.Forms.ToolTip> component.</span></span> <span data-ttu-id="8b50f-104">所有这些属性的度量单位为毫秒。</span><span class="sxs-lookup"><span data-stu-id="8b50f-104">The unit of measure for all these properties is milliseconds.</span></span> <span data-ttu-id="8b50f-105"><xref:System.Windows.Forms.ToolTip.InitialDelay%2A>属性确定多长时间，用户必须指向的关联控件的要显示的工具提示字符串。</span><span class="sxs-lookup"><span data-stu-id="8b50f-105">The <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> property determines how long the user must point at the associated control for the ToolTip string to appear.</span></span> <span data-ttu-id="8b50f-106"><xref:System.Windows.Forms.ToolTip.ReshowDelay%2A>属性设置的后续工具提示字符串，以显示当鼠标从一个工具提示相关联的控件移到另一个所需的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="8b50f-106">The <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> property sets the number of milliseconds it takes for subsequent ToolTip strings to appear as the mouse moves from one ToolTip-associated control to another.</span></span> <span data-ttu-id="8b50f-107"><xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A>属性确定在显示工具提示字符串的时间长度。</span><span class="sxs-lookup"><span data-stu-id="8b50f-107">The <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> property determines the length of time the ToolTip string is shown.</span></span> <span data-ttu-id="8b50f-108">单个或通过设置的值可以设置这些值<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>属性; 属性根据分配给的值设置的其他延迟<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="8b50f-108">You can set these values individually, or by setting the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property; the other delay properties are set based on the value assigned to the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property.</span></span> <span data-ttu-id="8b50f-109">例如，当<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>设置为的值为 N，<xref:System.Windows.Forms.ToolTip.InitialDelay%2A>设置为 N，<xref:System.Windows.Forms.ToolTip.ReshowDelay%2A>设置的值为<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>除以 5 （或 N/5），并<xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A>设置为五次的值的值为<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>属性 （或 5N）。</span><span class="sxs-lookup"><span data-stu-id="8b50f-109">For example, when <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> is set to a value N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> is set to N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> is set to the value of <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> divided by five (or N/5), and <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> is set to a value that is five times the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property (or 5N).</span></span>  
  
### <a name="to-set-the-delay"></a><span data-ttu-id="8b50f-110">若要设置延迟</span><span class="sxs-lookup"><span data-stu-id="8b50f-110">To set the delay</span></span>  
  
1. <span data-ttu-id="8b50f-111">在此示例中所示设置以下属性。</span><span class="sxs-lookup"><span data-stu-id="8b50f-111">Set the following properties as shown in this example.</span></span>  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8b50f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b50f-112">See also</span></span>

- [<span data-ttu-id="8b50f-113">ToolTip 组件概述</span><span class="sxs-lookup"><span data-stu-id="8b50f-113">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="8b50f-114">如何：在设计时为 Windows 窗体上的控件设置 ToolTip</span><span class="sxs-lookup"><span data-stu-id="8b50f-114">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [<span data-ttu-id="8b50f-115">ToolTip 组件</span><span class="sxs-lookup"><span data-stu-id="8b50f-115">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
