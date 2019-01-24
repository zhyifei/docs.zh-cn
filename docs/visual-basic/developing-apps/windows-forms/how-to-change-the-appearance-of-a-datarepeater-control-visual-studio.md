---
title: 如何：更改 DataRepeater 控件 (Visual Studio) 的外观
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, customizing
- DataRepeater, changing run time appearance
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
ms.openlocfilehash: e5508329ba716b53eff0c9e1bfe13e190fa1fd85
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716630"
---
# <a name="how-to-change-the-appearance-of-a-datarepeater-control-visual-studio"></a><span data-ttu-id="bd036-102">如何：更改 DataRepeater 控件 (Visual Studio) 的外观</span><span class="sxs-lookup"><span data-stu-id="bd036-102">How to: Change the Appearance of a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="bd036-103">您可以更改的外观<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件在设计时通过设置属性或在运行时处理<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件。</span><span class="sxs-lookup"><span data-stu-id="bd036-103">You can change the appearance of a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at design time by setting properties or at run time by handling the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event.</span></span>  
  
 <span data-ttu-id="bd036-104">在选中项模板部分的控件的设计时设置的属性将为每个重复<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>在运行时。</span><span class="sxs-lookup"><span data-stu-id="bd036-104">Properties that you set at design time when the item template section of the control is selected will be repeated for each <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> at run time.</span></span> <span data-ttu-id="bd036-105">与外观相关的属性<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件本身会显示在仅当容器的一部分保留为已发现的运行时 (例如，如果<xref:System.Windows.Forms.Control.Padding%2A>属性设置为较大的值)。</span><span class="sxs-lookup"><span data-stu-id="bd036-105">Appearance-related properties of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control itself will be visible at run time only if a part of the container is left uncovered (for example, if the <xref:System.Windows.Forms.Control.Padding%2A> property is set to a large value).</span></span>  
  
 <span data-ttu-id="bd036-106">在运行时，与外观相关的属性可以基于设置的条件。</span><span class="sxs-lookup"><span data-stu-id="bd036-106">At run time, appearance-related properties can be set based on conditions.</span></span> <span data-ttu-id="bd036-107">例如，在计划的应用程序，可能会更改来警告用户，当某项已过截止日期的项的背景色。</span><span class="sxs-lookup"><span data-stu-id="bd036-107">For example, in a scheduling application, you might change the background color of an item to warn users when an item is past due.</span></span> <span data-ttu-id="bd036-108">在中<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件处理程序，如果在条件语句中设置属性等`If…Then`，则还必须使用`Else`子句来指定不满足条件时的外观。</span><span class="sxs-lookup"><span data-stu-id="bd036-108">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, if you set a property in a conditional statement such as `If…Then`, you must also use an `Else` clause to specify the appearance when the condition is not met.</span></span>  
  
### <a name="to-change-the-appearance-at-design-time"></a><span data-ttu-id="bd036-109">若要更改在设计时外观</span><span class="sxs-lookup"><span data-stu-id="bd036-109">To change the appearance at design time</span></span>  
  
1.  <span data-ttu-id="bd036-110">在 Windows 窗体设计器中选择的项模板 （上限） 区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="bd036-110">In the Windows Forms Designer, select the item template (upper) region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="bd036-111">在属性窗口中选择属性并更改值。</span><span class="sxs-lookup"><span data-stu-id="bd036-111">In the Properties window, select a property and change the value.</span></span> <span data-ttu-id="bd036-112">影响外观的常见属性包括<xref:System.Windows.Forms.Control.BackColor%2A>， <xref:System.Windows.Forms.Control.BackgroundImage%2A>， <xref:System.Windows.Forms.Panel.BorderStyle%2A>，和<xref:System.Windows.Forms.Control.ForeColor%2A>。</span><span class="sxs-lookup"><span data-stu-id="bd036-112">Common properties that affect appearance include <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A>, and <xref:System.Windows.Forms.Control.ForeColor%2A>.</span></span>  
  
### <a name="to-change-the-appearance-at-run-time"></a><span data-ttu-id="bd036-113">若要在运行时更改外观</span><span class="sxs-lookup"><span data-stu-id="bd036-113">To change the appearance at run time</span></span>  
  
1.  <span data-ttu-id="bd036-114">在代码编辑器中，在事件下拉列表中，单击**DrawItem**。</span><span class="sxs-lookup"><span data-stu-id="bd036-114">In the Code Editor, in the Event drop-down list, click **DrawItem**.</span></span>  
  
2.  <span data-ttu-id="bd036-115">在<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件处理程序添加代码以设置属性：</span><span class="sxs-lookup"><span data-stu-id="bd036-115">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add code to set the properties:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="bd036-116">示例</span><span class="sxs-lookup"><span data-stu-id="bd036-116">Example</span></span>  
 <span data-ttu-id="bd036-117">一些常见的自定义项<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件包括显示中交替颜色和更改基于条件的字段的颜色的行。</span><span class="sxs-lookup"><span data-stu-id="bd036-117">Some common customizations for the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control include displaying the rows in alternating colors and changing the color of a field based on a condition.</span></span> <span data-ttu-id="bd036-118">下面的示例演示如何执行这些自定义。</span><span class="sxs-lookup"><span data-stu-id="bd036-118">The following example shows how to perform these customizations.</span></span> <span data-ttu-id="bd036-119">此示例假定你拥有<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件绑定到 Northwind 数据库中的产品表。</span><span class="sxs-lookup"><span data-stu-id="bd036-119">This example assumes that you have a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control that is bound to the Products table in the Northwind database.</span></span>  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.vb)]
 [!code-csharp[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.cs)]  
  
 <span data-ttu-id="bd036-120">请注意，对于这两个自定义，你必须提供代码来设置条件的双方的属性。</span><span class="sxs-lookup"><span data-stu-id="bd036-120">Note that for both of these customizations, you must provide code to set the properties for both sides of the condition.</span></span> <span data-ttu-id="bd036-121">如果未指定`Else`条件，您将在运行时看到意外的结果。</span><span class="sxs-lookup"><span data-stu-id="bd036-121">If you do not specify the `Else` condition, you will see unexpected results at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd036-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd036-122">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>
- [<span data-ttu-id="bd036-123">DataRepeater 控件简介</span><span class="sxs-lookup"><span data-stu-id="bd036-123">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="bd036-124">DataRepeater 控件疑难解答</span><span class="sxs-lookup"><span data-stu-id="bd036-124">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="bd036-125">如何：DataRepeater 控件中显示绑定的数据</span><span class="sxs-lookup"><span data-stu-id="bd036-125">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="bd036-126">如何：DataRepeater 控件中显示未绑定的控件</span><span class="sxs-lookup"><span data-stu-id="bd036-126">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="bd036-127">如何：DataRepeater 控件中显示项标头</span><span class="sxs-lookup"><span data-stu-id="bd036-127">How to: Display Item Headers in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
