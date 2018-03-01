---
title: "Splitter 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 32d8829e7303ce23a22d0a01f2428a889ce4ae0f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="10164-102">Splitter 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="10164-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="10164-103">尽管<xref:System.Windows.Forms.SplitContainer>替换并添加了功能<xref:System.Windows.Forms.Splitter>的早期版本中，控件<xref:System.Windows.Forms.Splitter>可以选择保留向后兼容性和将来使用。</span><span class="sxs-lookup"><span data-stu-id="10164-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="10164-104">Windows 窗体<xref:System.Windows.Forms.Splitter>控制用于在运行时调整停靠的控件的大小。</span><span class="sxs-lookup"><span data-stu-id="10164-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="10164-105"><xref:System.Windows.Forms.Splitter>控件常用于在与具有数据要呈现，如 Windows 资源管理器，其数据窗格包含不同的宽度的信息在不同时间的长度可变的控件的窗体上。</span><span class="sxs-lookup"><span data-stu-id="10164-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="10164-106">使用拆分器控件</span><span class="sxs-lookup"><span data-stu-id="10164-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="10164-107">当用户将鼠标指针指向由拆分器控件可以调整大小的控件的停靠边缘时，指针将改变其外观，以指示，可以调整控件的大小。</span><span class="sxs-lookup"><span data-stu-id="10164-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="10164-108">使用拆分器控件中，用户可以调整紧接着在它之前的停靠的控件。</span><span class="sxs-lookup"><span data-stu-id="10164-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="10164-109">因此，若要使用户在运行时调整停靠的控件，请停靠到容器的边缘可调整大小的控件，然后将拆分条控件停靠到该容器的同侧。</span><span class="sxs-lookup"><span data-stu-id="10164-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10164-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="10164-110">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 [<span data-ttu-id="10164-111">如何：在 Windows 窗体上停靠控件</span><span class="sxs-lookup"><span data-stu-id="10164-111">How to: Dock Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [<span data-ttu-id="10164-112">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="10164-112">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
