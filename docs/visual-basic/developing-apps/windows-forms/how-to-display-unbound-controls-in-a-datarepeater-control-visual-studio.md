---
title: "如何：在 DataRepeater 控件中显示未绑定的控件 (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3e96219f0ea8b8198967e9fa3c6e5afb824352db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="88b3c-102">如何：在 DataRepeater 控件中显示未绑定的控件 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="88b3c-102">How to: Display Unbound Controls in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="88b3c-103">除了绑定控件，你可能想要添加到其他控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>，如静态标签或图像，它在每个项重复<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="88b3c-103">In addition to bound controls, you may want to add other controls to a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88b3c-104">你还必须具有至少一个绑定的控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>或执行任何操作将在运行时显示。</span><span class="sxs-lookup"><span data-stu-id="88b3c-104">You must also have at least one bound control on the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> or nothing will be displayed at run time.</span></span>  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a><span data-ttu-id="88b3c-105">向 DataRepeater 添加未绑定的控件</span><span class="sxs-lookup"><span data-stu-id="88b3c-105">To add unbound controls to a DataRepeater</span></span>  
  
1.  <span data-ttu-id="88b3c-106">拖动<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。</span><span class="sxs-lookup"><span data-stu-id="88b3c-106">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="88b3c-107">拖动调整大小和位置的句柄到大小以及定位该控件。</span><span class="sxs-lookup"><span data-stu-id="88b3c-107">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="88b3c-108">您还可以调整大小和通过更改定位该控件**大小**和**位置**属性窗口中的属性。</span><span class="sxs-lookup"><span data-stu-id="88b3c-108">You can also size and position the control by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="88b3c-109">至少一个数据绑定将控件添加到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="88b3c-109">Add at least one data-bound control to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="88b3c-110">有关详细信息，请参阅[如何： 在 DataRepeater 控件中显示绑定数据](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="88b3c-110">For more information, see [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
4.  <span data-ttu-id="88b3c-111">拖动某个控件从**工具箱**拖动的项模板区域到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="88b3c-111">Drag a control from the **Toolbox** onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="88b3c-112">请注意该控件具有两个矩形区域。</span><span class="sxs-lookup"><span data-stu-id="88b3c-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="88b3c-113">内部区域是*项模板*; 将每个项中重复添加到模板控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件在运行时。</span><span class="sxs-lookup"><span data-stu-id="88b3c-113">The inner region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="88b3c-114">外部区域是*视区*，其中的项将显示; 添加到此区域的控件将不会显示在运行时。</span><span class="sxs-lookup"><span data-stu-id="88b3c-114">The outer region is the *viewport*, where the items will be displayed; controls that are added to this region will not be displayed at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88b3c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88b3c-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="88b3c-116">DataRepeater 控件简介</span><span class="sxs-lookup"><span data-stu-id="88b3c-116">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="88b3c-117">DataRepeater 控件疑难解答</span><span class="sxs-lookup"><span data-stu-id="88b3c-117">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="88b3c-118">如何：在 DataRepeater 控件中显示绑定数据</span><span class="sxs-lookup"><span data-stu-id="88b3c-118">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="88b3c-119">如何： 使用两个 DataRepeater 控件 (Visual Studio) 中创建主/从窗体</span><span class="sxs-lookup"><span data-stu-id="88b3c-119">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [<span data-ttu-id="88b3c-120">如何：更改 DataRepeater 控件的外观</span><span class="sxs-lookup"><span data-stu-id="88b3c-120">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
