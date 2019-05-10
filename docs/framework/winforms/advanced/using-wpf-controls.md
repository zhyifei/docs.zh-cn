---
title: 使用 WPF 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: 149a2da1303e6b801a439494254a416a38b145a7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211313"
---
# <a name="use-wpf-controls"></a><span data-ttu-id="c2a8e-102">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="c2a8e-102">Use WPF controls</span></span>

<span data-ttu-id="c2a8e-103">基于 Windows 窗体的应用程序中，可以使用 Windows Presentation Foundation (WPF) 控件。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="c2a8e-104">尽管这些是两个不同的视图技术，则它们平稳地相互操作。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-104">Although these are two different view technologies, they interoperate smoothly.</span></span>

<span data-ttu-id="c2a8e-105">Visual Studio 中的 Windows 窗体设计器提供了用于承载 Windows Presentation Foundation 控件的可视化设计环境。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-105">The Windows Forms Designer in Visual Studio provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="c2a8e-106">由名为的特殊 Windows 窗体控件承载 WPF 控件<xref:System.Windows.Forms.Integration.ElementHost>。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="c2a8e-107">此控件，WPF 控件来参与窗体的布局并接收键盘和鼠标消息。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="c2a8e-108">在设计时，可以安排<xref:System.Windows.Forms.Integration.ElementHost>控制就像对待任何 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>

<span data-ttu-id="c2a8e-109">此外可以基于 WPF 的应用程序中使用 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="c2a8e-110">有关详细信息，请参阅[Visual Studio 中设计 XAML](/visualstudio/designers/designing-xaml-in-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-110">For more information, see [Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c2a8e-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="c2a8e-111">In This Section</span></span>

<span data-ttu-id="c2a8e-112">[如何：复制并粘贴 ElementHost 控件在设计时](how-to-copy-and-paste-an-elementhost-control-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="c2a8e-112">[How to: Copy and Paste an ElementHost Control at Design Time](how-to-copy-and-paste-an-elementhost-control-at-design-time.md)\\</span></span>
<span data-ttu-id="c2a8e-113">演示如何将复制在 Windows 窗体上的 Windows Presentation Foundation 控件。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>

<span data-ttu-id="c2a8e-114">[演练：在设计时排列 Windows 窗体上的 WPF 内容](walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="c2a8e-114">[Walkthrough: Arranging WPF Content on Windows Forms at Design Time](walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="c2a8e-115">演示如何使用 Windows 窗体布局功能，例如锚定和对齐线，排列 Windows Presentation Foundation 控件。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>

<span data-ttu-id="c2a8e-116">[演练：在设计时在 Windows 窗体上创建新的 WPF 内容](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="c2a8e-116">[Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="c2a8e-117">演示如何创建基于 Windows 窗体的应用程序中使用的 Windows Presentation Foundation 控件。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-117">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>

<span data-ttu-id="c2a8e-118">[演练：在设计时分配在 Windows 窗体上的 WPF 内容](walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="c2a8e-118">[Walkthrough: Assigning WPF Content on Windows Forms at Design Time](walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="c2a8e-119">演示如何选择想要显示窗体上的 Windows Presentation Foundation 控件类型。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-119">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>

<span data-ttu-id="c2a8e-120">[演练：WPF 内容的样式](walkthrough-styling-wpf-content.md)\\</span><span class="sxs-lookup"><span data-stu-id="c2a8e-120">[Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md)\\</span></span>
<span data-ttu-id="c2a8e-121">显示 Windows 窗体设计器之间的工作流和[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]用于将样式应用到 Windows Presentation Foundation 控件。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-121">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>

## <a name="reference"></a><span data-ttu-id="c2a8e-122">参考</span><span class="sxs-lookup"><span data-stu-id="c2a8e-122">Reference</span></span>

<xref:System.Windows.Forms.Integration.ElementHost>\
<span data-ttu-id="c2a8e-123">介绍可以承载 Windows Presentation Foundation 控件使用基于 Windows 窗体的应用程序中的类。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-123">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>

<xref:System.Windows.Forms.Integration.WindowsFormsHost>\
<span data-ttu-id="c2a8e-124">介绍可用于在基于 Windows Presentation Foundation 的应用程序中承载 Windows 窗体控件的类。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-124">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>

## <a name="related-sections"></a><span data-ttu-id="c2a8e-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="c2a8e-125">Related sections</span></span>

<span data-ttu-id="c2a8e-126">[迁移和互操作性](../../wpf/advanced/migration-and-interoperability.md)\\</span><span class="sxs-lookup"><span data-stu-id="c2a8e-126">[Migration and Interoperability](../../wpf/advanced/migration-and-interoperability.md)\\</span></span>
<span data-ttu-id="c2a8e-127">介绍 Windows Presentation Foundation 和 Windows 窗体技术之间的互操作。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-127">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>

<span data-ttu-id="c2a8e-128">[在 Visual Studio 中的 XAML 设计](/visualstudio/designers/designing-xaml-in-visual-studio)\\</span><span class="sxs-lookup"><span data-stu-id="c2a8e-128">[Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)\\</span></span>
<span data-ttu-id="c2a8e-129">介绍如何设计在 Visual Studio 中的 Windows Presentation Foundation 控件。</span><span class="sxs-lookup"><span data-stu-id="c2a8e-129">Describes how to design Windows Presentation Foundation controls in Visual Studio.</span></span>
