---
title: 如何： 使用两个 DataRepeater 控件 (Visual Studio) 创建母版-详细信息窗体
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
ms.openlocfilehash: 84639a5d49a3fa4a8c6845793c39fc8a67c31e02
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245516"
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a><span data-ttu-id="e202f-102">如何：使用两个 DataRepeater 控件创建主/详细信息窗体 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="e202f-102">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>
<span data-ttu-id="e202f-103">可以使用两个或多个显示相关的数据<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件创建大纲/细节窗体。</span><span class="sxs-lookup"><span data-stu-id="e202f-103">You can display related data by using two or more <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls to create a master/detail form.</span></span> <span data-ttu-id="e202f-104">例如，你可能想要一个中显示客户列表<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>，并当用户选择某个客户，在一秒内显示该客户的订单列表的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>。</span><span class="sxs-lookup"><span data-stu-id="e202f-104">For example, you might want to display a list of customers in one <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and when the user selects a customer, display a list of that customer's orders in a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
 <span data-ttu-id="e202f-105">可以通过将共享中的相同主表节点的详细信息项显示相关的数据**数据源**窗口拖到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="e202f-105">You can display related data by dragging detail items that share the same master table node from the **Data Sources** window onto a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="e202f-106">例如，如果必须具有对 Customers 表和相关的 Orders 表的数据源，你看到这两个表为中的树视图中的顶级节点**数据源**窗口。</span><span class="sxs-lookup"><span data-stu-id="e202f-106">For example, if you have a data source that has a Customers table and a related Orders table, you see both tables as top-level nodes in the tree view in the **Data Sources** window.</span></span> <span data-ttu-id="e202f-107">展开的客户节点，以便您可以看到的列。</span><span class="sxs-lookup"><span data-stu-id="e202f-107">Expand the Customers node so that you can see the columns.</span></span> <span data-ttu-id="e202f-108">请注意，在列表中的最后一列表示订单表的可展开节点。</span><span class="sxs-lookup"><span data-stu-id="e202f-108">Notice that the last column in the list is an expandable node that represents the Orders table.</span></span> <span data-ttu-id="e202f-109">此节点表示客户的相关的订单。</span><span class="sxs-lookup"><span data-stu-id="e202f-109">This node represents the related orders for a customer.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a><span data-ttu-id="e202f-110">若要在两个 DataRepeater 控件中显示相关的数据</span><span class="sxs-lookup"><span data-stu-id="e202f-110">To display related data in two DataRepeater controls</span></span>  
  
1.  <span data-ttu-id="e202f-111">将两个<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。</span><span class="sxs-lookup"><span data-stu-id="e202f-111">Drag two <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="e202f-112">拖动调整大小和位置图柄以调整控件大小，并将它们置于由并行。</span><span class="sxs-lookup"><span data-stu-id="e202f-112">Drag the sizing and position handles to size the controls and position them side-by-side.</span></span>  
  
3.  <span data-ttu-id="e202f-113">在 **“数据”** 菜单上，单击 **“显示数据源”**。</span><span class="sxs-lookup"><span data-stu-id="e202f-113">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e202f-114">如果**数据源**窗口为空，则向其添加数据源。</span><span class="sxs-lookup"><span data-stu-id="e202f-114">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="e202f-115">有关详细信息，请参阅[添加新数据源](/visualstudio/data-tools/add-new-data-sources)。</span><span class="sxs-lookup"><span data-stu-id="e202f-115">For more information, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="e202f-116">在中**数据源**窗口中，选择主表的顶级节点。</span><span class="sxs-lookup"><span data-stu-id="e202f-116">In the **Data Sources** window, select the top-level node for the master table.</span></span>  
  
5.  <span data-ttu-id="e202f-117">通过单击主表的拖放类型更改为详细信息**详细信息**表节点上的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="e202f-117">Change the drop type of the master table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="e202f-118">主表节点拖到第一个项模板区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="e202f-118">Drag the master table node onto the item template region of the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
7.  <span data-ttu-id="e202f-119">展开主表节点并选择相关表的详细信息节点。</span><span class="sxs-lookup"><span data-stu-id="e202f-119">Expand the master table node and select the detail node for the related table.</span></span>  
  
8.  <span data-ttu-id="e202f-120">通过单击详细信息表的拖放类型更改为详细信息**详细信息**表节点上的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="e202f-120">Change the drop type of the detail table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
9. <span data-ttu-id="e202f-121">选择此表节点，然后将其拖到第二个项模板区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="e202f-121">Select this table node and drag it onto the item template region of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e202f-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="e202f-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="e202f-123">DataRepeater 控件简介</span><span class="sxs-lookup"><span data-stu-id="e202f-123">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="e202f-124">如何：在 DataRepeater 控件中显示绑定数据</span><span class="sxs-lookup"><span data-stu-id="e202f-124">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="e202f-125">如何：在 Windows 窗体应用程序中显示相关数据</span><span class="sxs-lookup"><span data-stu-id="e202f-125">How to: Display Related Data in a Windows Forms Application</span></span>](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [<span data-ttu-id="e202f-126">如何：更改 DataRepeater 控件的外观</span><span class="sxs-lookup"><span data-stu-id="e202f-126">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="e202f-127">DataRepeater 控件疑难解答</span><span class="sxs-lookup"><span data-stu-id="e202f-127">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
