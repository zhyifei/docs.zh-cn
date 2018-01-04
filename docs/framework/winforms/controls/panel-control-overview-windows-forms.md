---
title: "Panel 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a8855c88a0ec60cd0d44d73046e44c9614347d90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="panel-control-overview-windows-forms"></a><span data-ttu-id="80fd4-102">Panel 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="80fd4-102">Panel Control Overview (Windows Forms)</span></span>
<span data-ttu-id="80fd4-103">Windows 窗体<xref:System.Windows.Forms.Panel>控件用于提供其他控件可识别分组。</span><span class="sxs-lookup"><span data-stu-id="80fd4-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to provide an identifiable grouping for other controls.</span></span> <span data-ttu-id="80fd4-104">通常，你可以使用面板函数细分窗体。</span><span class="sxs-lookup"><span data-stu-id="80fd4-104">Typically, you use panels to subdivide a form by function.</span></span> <span data-ttu-id="80fd4-105">例如，你可以指定邮件的选项，如使用哪夜间运输工具订购窗体。</span><span class="sxs-lookup"><span data-stu-id="80fd4-105">For example, you may have an order form that specifies mailing options such as which overnight carrier to use.</span></span> <span data-ttu-id="80fd4-106">分组在面板中的所有选项为用户提供一个逻辑的视觉提示。</span><span class="sxs-lookup"><span data-stu-id="80fd4-106">Grouping all options in a panel gives the user a logical visual cue.</span></span> <span data-ttu-id="80fd4-107">在设计时所有可以轻松地移动控件 — 当您移动<xref:System.Windows.Forms.Panel>控制，所有其所含的控件移动，太。</span><span class="sxs-lookup"><span data-stu-id="80fd4-107">At design time all the controls can be moved easily — when you move the <xref:System.Windows.Forms.Panel> control, all its contained controls move, too.</span></span> <span data-ttu-id="80fd4-108">在一个面板中分组控件可以通过其<xref:System.Windows.Forms.Control.Controls%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="80fd4-108">The controls grouped in a panel can be accessed through its <xref:System.Windows.Forms.Control.Controls%2A> property.</span></span> <span data-ttu-id="80fd4-109">此属性返回的集合<xref:System.Windows.Forms.Control>实例，因此你通常需要强制转换控件检索到它的特定类型的这种方式。</span><span class="sxs-lookup"><span data-stu-id="80fd4-109">This property returns a collection of <xref:System.Windows.Forms.Control> instances, so you will typically need to cast a control retrieved this way to its specific type.</span></span>  
  
## <a name="panel-versus-groupbox"></a><span data-ttu-id="80fd4-110">与组合框的面板</span><span class="sxs-lookup"><span data-stu-id="80fd4-110">Panel Versus GroupBox</span></span>  
 <span data-ttu-id="80fd4-111"><xref:System.Windows.Forms.Panel>控件是类似于<xref:System.Windows.Forms.GroupBox>控制; 但是，仅<xref:System.Windows.Forms.Panel>控件可以具有滚动条仅和<xref:System.Windows.Forms.GroupBox>控件显示的标题。</span><span class="sxs-lookup"><span data-stu-id="80fd4-111">The <xref:System.Windows.Forms.Panel> control is similar to the <xref:System.Windows.Forms.GroupBox> control; however, only the <xref:System.Windows.Forms.Panel> control can have scroll bars, and only the <xref:System.Windows.Forms.GroupBox> control displays a caption.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="80fd4-112">键属性</span><span class="sxs-lookup"><span data-stu-id="80fd4-112">Key Properties</span></span>  
 <span data-ttu-id="80fd4-113">若要显示滚动条，设置<xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="80fd4-113">To display scroll bars, set the <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> property to `true`.</span></span> <span data-ttu-id="80fd4-114">此外可以自面板的外观定义通过设置<xref:System.Windows.Forms.Control.BackColor%2A>， <xref:System.Windows.Forms.Control.BackgroundImage%2A>，和<xref:System.Windows.Forms.Panel.BorderStyle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="80fd4-114">You can also customize the appearance of the panel by setting the <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, and <xref:System.Windows.Forms.Panel.BorderStyle%2A> properties.</span></span> <span data-ttu-id="80fd4-115">有关详细信息<xref:System.Windows.Forms.Control.BackColor%2A>和<xref:System.Windows.Forms.Control.BackgroundImage%2A>属性，请参阅[如何： 设置面板的背景](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)。</span><span class="sxs-lookup"><span data-stu-id="80fd4-115">For more information on the <xref:System.Windows.Forms.Control.BackColor%2A> and <xref:System.Windows.Forms.Control.BackgroundImage%2A> properties, see [How to: Set the Background of a Panel](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md).</span></span> <span data-ttu-id="80fd4-116"><xref:System.Windows.Forms.Panel.BorderStyle%2A>属性确定是否为无可视边框概述面板 (<xref:System.Windows.Forms.BorderStyle.None>)，纯行 (<xref:System.Windows.Forms.BorderStyle.FixedSingle>)，或隐藏的行 (<xref:System.Windows.Forms.BorderStyle.Fixed3D>)。</span><span class="sxs-lookup"><span data-stu-id="80fd4-116">The <xref:System.Windows.Forms.Panel.BorderStyle%2A> property determines if the panel is outlined with no visible border (<xref:System.Windows.Forms.BorderStyle.None>), a plain line (<xref:System.Windows.Forms.BorderStyle.FixedSingle>), or a shadowed line (<xref:System.Windows.Forms.BorderStyle.Fixed3D>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80fd4-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="80fd4-117">See Also</span></span>  
 <xref:System.Windows.Forms.Panel>  
 [<span data-ttu-id="80fd4-118">GroupBox 控件</span><span class="sxs-lookup"><span data-stu-id="80fd4-118">GroupBox Control</span></span>](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)  
 [<span data-ttu-id="80fd4-119">如何：使用设计器用 Windows 窗体 Panel 控件对控件进行分组</span><span class="sxs-lookup"><span data-stu-id="80fd4-119">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)  
 [<span data-ttu-id="80fd4-120">如何：使用设计器设置 Windows 窗体 Panel 控件的背景</span><span class="sxs-lookup"><span data-stu-id="80fd4-120">How to: Set the Background of a Windows Forms Panel Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
