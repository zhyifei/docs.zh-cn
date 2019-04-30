---
title: Splitter 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 0477f68aaf67d4b29c491052999ff7784e736669
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009703"
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="2eac8-102">Splitter 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="2eac8-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="2eac8-103">尽管<xref:System.Windows.Forms.SplitContainer>替换并添加了功能<xref:System.Windows.Forms.Splitter>的早期版本中，控制<xref:System.Windows.Forms.Splitter>如果选择保留向后兼容性和将来使用。</span><span class="sxs-lookup"><span data-stu-id="2eac8-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="2eac8-104">Windows 窗体<xref:System.Windows.Forms.Splitter>控制用于在运行时调整停靠的控件的大小。</span><span class="sxs-lookup"><span data-stu-id="2eac8-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="2eac8-105"><xref:System.Windows.Forms.Splitter>通常具有的数据来展示，如 Windows 资源管理器，它的数据窗格包含不同的宽度的信息在不同的时间长度可变的控件与窗体上使用控件。</span><span class="sxs-lookup"><span data-stu-id="2eac8-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="2eac8-106">使用拆分器控件</span><span class="sxs-lookup"><span data-stu-id="2eac8-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="2eac8-107">当用户将鼠标指针指向未停靠的控件可调整大小的拆分器控件的边缘时，指针将更改其外观，以指示该控件可以调整大小。</span><span class="sxs-lookup"><span data-stu-id="2eac8-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="2eac8-108">拆分器控件后，用户可以调整大小的停靠的控件的紧前面。</span><span class="sxs-lookup"><span data-stu-id="2eac8-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="2eac8-109">因此，若要允许用户调整停靠的控件的大小在运行时，停靠控件要调整大小的容器的边缘，然后将拆分器控件停靠到该容器在同一端。</span><span class="sxs-lookup"><span data-stu-id="2eac8-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eac8-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="2eac8-110">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="2eac8-111">如何：在 Windows 窗体上停靠控件</span><span class="sxs-lookup"><span data-stu-id="2eac8-111">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="2eac8-112">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="2eac8-112">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
