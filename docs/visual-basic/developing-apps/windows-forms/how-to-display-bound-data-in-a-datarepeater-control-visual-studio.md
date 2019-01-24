---
title: 如何：DataRepeater 控件 (Visual Studio) 中显示绑定的数据
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
ms.openlocfilehash: dbcd814edb78c54ce5629a1a8761142674fe6135
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684614"
---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="f74f3-102">如何：DataRepeater 控件 (Visual Studio) 中显示绑定的数据</span><span class="sxs-lookup"><span data-stu-id="f74f3-102">How to: Display Bound Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="f74f3-103">最常用的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件将显示从数据库或其他数据源绑定的数据。</span><span class="sxs-lookup"><span data-stu-id="f74f3-103">The most common use of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control is to display bound data from a database or other data source.</span></span>  
  
 <span data-ttu-id="f74f3-104">除了绑定控件，您可能想要添加其他控件，如静态标签或图像中每个项重复<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="f74f3-104">In addition to bound controls, you may want to add other controls, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="f74f3-105">有关详细信息，请参阅[如何：DataRepeater 控件中的控件显示未绑定](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="f74f3-105">For more information, see [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
 <span data-ttu-id="f74f3-106">此外可以绑定到数据源在运行时通过设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>属性设置为`True`并将分配到的数据源<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="f74f3-106">You can also bind to a data source at run time by setting the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> property to `True` and assigning a data source to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> property.</span></span> <span data-ttu-id="f74f3-107">在这种情况下，需要管理与数据源的所有交互。</span><span class="sxs-lookup"><span data-stu-id="f74f3-107">In this case, you will need to manage all interaction with the data source.</span></span> <span data-ttu-id="f74f3-108">有关详细信息，请参阅[DataRepeater 控件中的虚拟模式](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="f74f3-108">For more information, see [Virtual Mode in the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a><span data-ttu-id="f74f3-109">若要创建数据绑定 DataRepeater</span><span class="sxs-lookup"><span data-stu-id="f74f3-109">To create a data-bound DataRepeater</span></span>  
  
1.  <span data-ttu-id="f74f3-110">拖动<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。</span><span class="sxs-lookup"><span data-stu-id="f74f3-110">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="f74f3-111">拖动调整大小和位置的句柄到大小和定位控件。</span><span class="sxs-lookup"><span data-stu-id="f74f3-111">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="f74f3-112">请注意，该控件有两个矩形区域。</span><span class="sxs-lookup"><span data-stu-id="f74f3-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="f74f3-113">上半部分区域是*项模板*; 控件添加到模板中将重复在每个项中<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件在运行时。</span><span class="sxs-lookup"><span data-stu-id="f74f3-113">The upper region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="f74f3-114">较低的区域是*视区*，其中将显示的项目。</span><span class="sxs-lookup"><span data-stu-id="f74f3-114">The lower region is the *viewport*, where the items will be displayed.</span></span>  
  
     <span data-ttu-id="f74f3-115">您还可以调整大小和定位控件或项模板通过更改**大小**并**位置**属性窗口中的属性。</span><span class="sxs-lookup"><span data-stu-id="f74f3-115">You can also size and position the control or the item template by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="f74f3-116">在 **“数据”** 菜单上，单击 **“显示数据源”**。</span><span class="sxs-lookup"><span data-stu-id="f74f3-116">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f74f3-117">如果**数据源**窗口为空，则向其添加数据源。</span><span class="sxs-lookup"><span data-stu-id="f74f3-117">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="f74f3-118">有关详细信息，请参阅[添加新数据源](/visualstudio/data-tools/add-new-data-sources)。</span><span class="sxs-lookup"><span data-stu-id="f74f3-118">For more information, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="f74f3-119">在中**数据源**窗口中，选择包含你想要绑定的数据的表的顶级节点。</span><span class="sxs-lookup"><span data-stu-id="f74f3-119">In the **Data Sources** window, select the top-level node for the table that contains the data that you want to bind.</span></span>  
  
5.  <span data-ttu-id="f74f3-120">将表拖放类型更改`Details`通过单击`Details`表节点上的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="f74f3-120">Change the drop type of the table to `Details` by clicking `Details` in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="f74f3-121">选择表节点，并将其拖动到项模板区域的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="f74f3-121">Select the table node and drag it onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="f74f3-122">您可以指定哪些类型的控件将显示为每个字段。</span><span class="sxs-lookup"><span data-stu-id="f74f3-122">You can specify which types of controls are displayed for each field.</span></span> <span data-ttu-id="f74f3-123">有关详细信息，请参阅[设置从数据源窗口中拖动时创建的控件](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window)。</span><span class="sxs-lookup"><span data-stu-id="f74f3-123">For more information, see [Set the control to be created when dragging from the Data Sources window](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f74f3-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="f74f3-124">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [<span data-ttu-id="f74f3-125">DataRepeater 控件简介</span><span class="sxs-lookup"><span data-stu-id="f74f3-125">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="f74f3-126">如何：DataRepeater 控件中显示未绑定的控件</span><span class="sxs-lookup"><span data-stu-id="f74f3-126">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="f74f3-127">如何：使用两个 DataRepeater 控件 (Visual Studio) 创建母版/详细信息窗体</span><span class="sxs-lookup"><span data-stu-id="f74f3-127">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
- [<span data-ttu-id="f74f3-128">如何：更改 DataRepeater 控件的外观</span><span class="sxs-lookup"><span data-stu-id="f74f3-128">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="f74f3-129">DataRepeater 控件疑难解答</span><span class="sxs-lookup"><span data-stu-id="f74f3-129">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
