---
title: 如何：DataRepeater 控件 (Visual Studio) 中显示未绑定的控件
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
ms.openlocfilehash: a20e1ba83d1963bc3d4c135817767ee02fcbdeda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730784"
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="4be81-102">如何：DataRepeater 控件 (Visual Studio) 中显示未绑定的控件</span><span class="sxs-lookup"><span data-stu-id="4be81-102">How to: Display Unbound Controls in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="4be81-103">除了绑定控件，您可能想要添加到其他控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>，如静态标签或图像中每个项重复<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="4be81-103">In addition to bound controls, you may want to add other controls to a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4be81-104">您还必须具有至少一个绑定的控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>或执行任何操作将在运行时显示。</span><span class="sxs-lookup"><span data-stu-id="4be81-104">You must also have at least one bound control on the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> or nothing will be displayed at run time.</span></span>  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a><span data-ttu-id="4be81-105">向 DataRepeater 添加未绑定的控件</span><span class="sxs-lookup"><span data-stu-id="4be81-105">To add unbound controls to a DataRepeater</span></span>  
  
1.  <span data-ttu-id="4be81-106">拖动<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。</span><span class="sxs-lookup"><span data-stu-id="4be81-106">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="4be81-107">拖动调整大小和位置的句柄到大小和定位控件。</span><span class="sxs-lookup"><span data-stu-id="4be81-107">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="4be81-108">您还可以调整大小和定位该控件通过更改**大小**并**位置**属性窗口中的属性。</span><span class="sxs-lookup"><span data-stu-id="4be81-108">You can also size and position the control by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="4be81-109">添加至少一个数据绑定控件绑定到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="4be81-109">Add at least one data-bound control to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="4be81-110">有关详细信息，请参阅[如何：显示在 DataRepeater 控件中绑定数据](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="4be81-110">For more information, see [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
4.  <span data-ttu-id="4be81-111">将控件从**工具箱**上的项模板区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="4be81-111">Drag a control from the **Toolbox** onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="4be81-112">请注意，该控件有两个矩形区域。</span><span class="sxs-lookup"><span data-stu-id="4be81-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="4be81-113">内部区域是*项模板*; 控件添加到模板中将重复在每个项中<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件在运行时。</span><span class="sxs-lookup"><span data-stu-id="4be81-113">The inner region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="4be81-114">是外部的区域*视区*，其中将显示的项目; 添加到此区域的控件将不会显示在运行时。</span><span class="sxs-lookup"><span data-stu-id="4be81-114">The outer region is the *viewport*, where the items will be displayed; controls that are added to this region will not be displayed at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4be81-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="4be81-115">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [<span data-ttu-id="4be81-116">DataRepeater 控件简介</span><span class="sxs-lookup"><span data-stu-id="4be81-116">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="4be81-117">DataRepeater 控件疑难解答</span><span class="sxs-lookup"><span data-stu-id="4be81-117">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="4be81-118">如何：DataRepeater 控件中显示绑定的数据</span><span class="sxs-lookup"><span data-stu-id="4be81-118">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="4be81-119">如何：使用两个 DataRepeater 控件 (Visual Studio) 创建母版/详细信息窗体</span><span class="sxs-lookup"><span data-stu-id="4be81-119">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
- [<span data-ttu-id="4be81-120">如何：更改 DataRepeater 控件的外观</span><span class="sxs-lookup"><span data-stu-id="4be81-120">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
