---
title: 使用 WPF 控件
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b8225447e6c0daa7894d622616131febb6ac82b5
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="using-wpf-controls"></a><span data-ttu-id="9201e-102">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="9201e-102">Using WPF Controls</span></span>
<span data-ttu-id="9201e-103">在基于 Windows 窗体的应用程序，可以使用 Windows Presentation Foundation (WPF) 控件。</span><span class="sxs-lookup"><span data-stu-id="9201e-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="9201e-104">尽管这些是两个不同的视图技术，则它们顺利互操作。</span><span class="sxs-lookup"><span data-stu-id="9201e-104">Although these are two different view technologies, they interoperate smoothly.</span></span>  
  
 <span data-ttu-id="9201e-105">Windows 窗体设计器提供用于承载 Windows Presentation Foundation 控件的可视设计环境。</span><span class="sxs-lookup"><span data-stu-id="9201e-105">The Windows Forms Designer provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="9201e-106">由名为的特殊 Windows 窗体控件承载 WPF 控件<xref:System.Windows.Forms.Integration.ElementHost>。</span><span class="sxs-lookup"><span data-stu-id="9201e-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="9201e-107">此控件启用 WPF 控件将参与窗体的布局以及接收键盘和鼠标的消息。</span><span class="sxs-lookup"><span data-stu-id="9201e-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="9201e-108">在设计时，可以排列<xref:System.Windows.Forms.Integration.ElementHost>控制就像任何 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="9201e-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>  
  
 <span data-ttu-id="9201e-109">此外可以基于 WPF 的应用程序中使用 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="9201e-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="9201e-110">有关详细信息，请参阅[WPF 设计器](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)。</span><span class="sxs-lookup"><span data-stu-id="9201e-110">For more information, see [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9201e-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="9201e-111">In This Section</span></span>  
 [<span data-ttu-id="9201e-112">如何：在设计时复制并粘贴 ElementHost 控件</span><span class="sxs-lookup"><span data-stu-id="9201e-112">How to: Copy and Paste an ElementHost Control at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 <span data-ttu-id="9201e-113">演示如何将 Windows 窗体上的 Windows Presentation Foundation 控件复制。</span><span class="sxs-lookup"><span data-stu-id="9201e-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>  
  
 [<span data-ttu-id="9201e-114">演练：在设计时在 Windows 窗体上排列 WPF 内容</span><span class="sxs-lookup"><span data-stu-id="9201e-114">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="9201e-115">演示如何使用 Windows 窗体布局功能，例如锚定和对齐线，排列 Windows Presentation Foundation 控件。</span><span class="sxs-lookup"><span data-stu-id="9201e-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>  
  
 [<span data-ttu-id="9201e-116">演练：在设计时更改托管 WPF 元素的属性</span><span class="sxs-lookup"><span data-stu-id="9201e-116">Walkthrough: Changing Properties of a Hosted WPF Element at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 <span data-ttu-id="9201e-117">显示 Windows 窗体设计器之间的工作流和[!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]更改 WPF 控件的属性。</span><span class="sxs-lookup"><span data-stu-id="9201e-117">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] for changing properties on WPF controls.</span></span>  
  
 [<span data-ttu-id="9201e-118">演练：在设计时在 Windows 窗体上新建 WPF 内容</span><span class="sxs-lookup"><span data-stu-id="9201e-118">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="9201e-119">演示如何在基于 Windows 窗体的应用程序中创建使用 Windows Presentation Foundation 控件。</span><span class="sxs-lookup"><span data-stu-id="9201e-119">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>  
  
 [<span data-ttu-id="9201e-120">演练：将 ElementHost 控件复制并粘贴到各个 Windows 窗体中</span><span class="sxs-lookup"><span data-stu-id="9201e-120">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 <span data-ttu-id="9201e-121">演示如何将 Windows Presentation Foundation 控件从一个 Windows 窗体复制到另一个。</span><span class="sxs-lookup"><span data-stu-id="9201e-121">Shows how to copy a Windows Presentation Foundation control from one Windows Form to another.</span></span>  
  
 [<span data-ttu-id="9201e-122">演练：在设计时在 Windows 窗体上分配 WPF 内容</span><span class="sxs-lookup"><span data-stu-id="9201e-122">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="9201e-123">演示如何选择你想要在窗体上显示的 Windows Presentation Foundation 控件类型。</span><span class="sxs-lookup"><span data-stu-id="9201e-123">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>  
  
 [<span data-ttu-id="9201e-124">演练：设置 WPF 内容的样式</span><span class="sxs-lookup"><span data-stu-id="9201e-124">Walkthrough: Styling WPF Content</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 <span data-ttu-id="9201e-125">显示 Windows 窗体设计器之间的工作流和[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]用于将样式应用到 Windows Presentation Foundation 控件。</span><span class="sxs-lookup"><span data-stu-id="9201e-125">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9201e-126">参考</span><span class="sxs-lookup"><span data-stu-id="9201e-126">Reference</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <span data-ttu-id="9201e-127">介绍可以在基于 Windows 窗体的应用程序中使用到的主机 Windows Presentation Foundation 控件的类。</span><span class="sxs-lookup"><span data-stu-id="9201e-127">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 <span data-ttu-id="9201e-128">介绍可以在基于 Windows Presentation Foundation 的应用程序中使用主机 Windows 窗体控件的类。</span><span class="sxs-lookup"><span data-stu-id="9201e-128">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9201e-129">相关章节</span><span class="sxs-lookup"><span data-stu-id="9201e-129">Related Sections</span></span>  
 [<span data-ttu-id="9201e-130">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="9201e-130">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 <span data-ttu-id="9201e-131">介绍 Windows Presentation Foundation 和 Windows 窗体技术之间的互操作。</span><span class="sxs-lookup"><span data-stu-id="9201e-131">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>  
  
 [<span data-ttu-id="9201e-132">WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="9201e-132">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 <span data-ttu-id="9201e-133">描述如何设计 Visual Studio 中的 Windows Presentation Foundation 控件。</span><span class="sxs-lookup"><span data-stu-id="9201e-133">Describes how to design Windows Presentation Foundation controls in Visual Studio.</span></span>
