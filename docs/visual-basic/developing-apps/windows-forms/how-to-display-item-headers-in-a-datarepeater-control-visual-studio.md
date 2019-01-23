---
title: 如何：DataRepeater 控件 (Visual Studio) 中显示项标头
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, item headers
- DataRepeater, selection indicators
ms.assetid: 37321447-0ffa-43e1-bdc9-0480e392b90f
ms.openlocfilehash: eccac1b3b02da41a34d47072be267f6c51a7d490
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504556"
---
# <a name="how-to-display-item-headers-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="0d57e-102">如何：DataRepeater 控件 (Visual Studio) 中显示项标头</span><span class="sxs-lookup"><span data-stu-id="0d57e-102">How to: Display Item Headers in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="0d57e-103">中的项标头<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件提供可视的指示器时<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="0d57e-103">The item header in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control provides a visual indicator when a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> is selected.</span></span> <span data-ttu-id="0d57e-104">当<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>属性设置为<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical>（默认值），每个项的左边显示项标头。</span><span class="sxs-lookup"><span data-stu-id="0d57e-104">When the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> (the default), the item header is displayed to the left of each item.</span></span> <span data-ttu-id="0d57e-105">当<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>属性设置为<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>，在每个项的顶部显示的项标头。</span><span class="sxs-lookup"><span data-stu-id="0d57e-105">When the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>, the item header is displayed at the top of each item.</span></span>  
  
 <span data-ttu-id="0d57e-106">首先选择它后，在由指定的颜色显示项标头<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>显示属性，并有一个白色箭头图标。</span><span class="sxs-lookup"><span data-stu-id="0d57e-106">When it is first selected, the item header is displayed in the color that is specified by the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> property, and a white arrow icon is displayed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d57e-107">如果您设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>到<xref:System.Drawing.Color.White%2A>，选择符号首次选定项时将不可见。</span><span class="sxs-lookup"><span data-stu-id="0d57e-107">If you set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> to <xref:System.Drawing.Color.White%2A>, the selection symbol will not be visible when the item is first selected.</span></span>  
  
 <span data-ttu-id="0d57e-108">中的字段时<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>具有焦点的项标头更改颜色<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>背景颜色和箭头图标更改为黑色。</span><span class="sxs-lookup"><span data-stu-id="0d57e-108">When a field in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> has focus, the color of the item header changes to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> background color and the arrow icon changes to black.</span></span> <span data-ttu-id="0d57e-109">如果数据已更改，铅笔符号显示项标头中。</span><span class="sxs-lookup"><span data-stu-id="0d57e-109">If data is changed, a pencil symbol is displayed in the item header.</span></span>  
  
 <span data-ttu-id="0d57e-110">默认宽度 (或高度时<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>属性设置为<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>) 项的标头是 15 个像素。</span><span class="sxs-lookup"><span data-stu-id="0d57e-110">The default width (or height when the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>) of the item header is 15 pixels.</span></span> <span data-ttu-id="0d57e-111">您可以通过设置更改宽度<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0d57e-111">You can change the width by setting the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d57e-112">如果<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>属性设置为小于 11 的值，将不会显示项标头中的指示符符号。</span><span class="sxs-lookup"><span data-stu-id="0d57e-112">If the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> property is set to a value that is less than 11, the indicator symbols in the item header will not be displayed.</span></span>  
  
 <span data-ttu-id="0d57e-113">可以通过设置隐藏的项标头<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A>属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="0d57e-113">You can hide the item headers by setting the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> property to **False**.</span></span> <span data-ttu-id="0d57e-114">当<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A>设置为**False**，选择项的唯一指示是周围的点线<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>。</span><span class="sxs-lookup"><span data-stu-id="0d57e-114">When <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> is set to **False**, the only indication that an item is selected is a dotted line around the perimeter of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d57e-115">此外可以通过监视提供您自己选择指示器<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>的属性<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>中<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="0d57e-115">You can also provide your own selection indicator by monitoring the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> property of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="0d57e-116">有关详细信息，请参阅 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>。</span><span class="sxs-lookup"><span data-stu-id="0d57e-116">For more information, see <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.</span></span>  
  
### <a name="to-change-the-appearance-of-item-headers"></a><span data-ttu-id="0d57e-117">若要更改项标题的外观</span><span class="sxs-lookup"><span data-stu-id="0d57e-117">To change the appearance of item headers</span></span>  
  
1.  <span data-ttu-id="0d57e-118">在 Windows 窗体设计器中选择的下半部分区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="0d57e-118">In the Windows Forms Designer, select the lower region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d57e-119">您必须选择控件的较低的区域。</span><span class="sxs-lookup"><span data-stu-id="0d57e-119">You must select the lower region of the control.</span></span> <span data-ttu-id="0d57e-120">如果选择项模板部分中，在属性窗口中将显示一组不同的属性。</span><span class="sxs-lookup"><span data-stu-id="0d57e-120">If you select the item template section, a different set of properties will appear in the Properties window.</span></span>  
  
2.  <span data-ttu-id="0d57e-121">在属性窗口中，使用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>要更改项标题的颜色属性。</span><span class="sxs-lookup"><span data-stu-id="0d57e-121">In the Properties window, use the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> property to change the color of the item headers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d57e-122">如果您设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>到<xref:System.Drawing.Color.White%2A>，选择符号首次选定项时将不可见。</span><span class="sxs-lookup"><span data-stu-id="0d57e-122">If you set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> to <xref:System.Drawing.Color.White%2A>, the selection symbol will not be visible when the item is first selected.</span></span>  
  
3.  <span data-ttu-id="0d57e-123">使用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>属性来更改项标题的宽度 （或高度）。</span><span class="sxs-lookup"><span data-stu-id="0d57e-123">Use the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> property to change the width (or height) of the item headers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d57e-124">如果<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>属性设置为小于 11 的值，将不会显示项标头中的指示符符号。</span><span class="sxs-lookup"><span data-stu-id="0d57e-124">If the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> property is set to a value that is less than 11, the indicator symbols in the item header will not be displayed.</span></span>  
  
### <a name="to-hide-item-headers"></a><span data-ttu-id="0d57e-125">若要隐藏项标头</span><span class="sxs-lookup"><span data-stu-id="0d57e-125">To hide item headers</span></span>  
  
1.  <span data-ttu-id="0d57e-126">在 Windows 窗体设计器中选择的下半部分区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="0d57e-126">In the Windows Forms Designer, select the lower region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d57e-127">您必须选择控件的较低的区域。</span><span class="sxs-lookup"><span data-stu-id="0d57e-127">You must select the lower region of the control.</span></span> <span data-ttu-id="0d57e-128">如果选择项模板部分中，在属性窗口中将显示一组不同的属性。</span><span class="sxs-lookup"><span data-stu-id="0d57e-128">If you select the item template section, a different set of properties will appear in the Properties window.</span></span>  
  
2.  <span data-ttu-id="0d57e-129">在属性窗口中设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A>属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="0d57e-129">In the Properties window, set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> property to **False**.</span></span>  
  
     <span data-ttu-id="0d57e-130">中的项后<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>是选择，唯一的指示将周围的点线<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>。</span><span class="sxs-lookup"><span data-stu-id="0d57e-130">When an item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> is selected, the only indication will be a dotted line around the perimeter of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d57e-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="0d57e-131">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [<span data-ttu-id="0d57e-132">DataRepeater 控件简介</span><span class="sxs-lookup"><span data-stu-id="0d57e-132">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="0d57e-133">如何：更改 DataRepeater 控件的外观</span><span class="sxs-lookup"><span data-stu-id="0d57e-133">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="0d57e-134">如何：更改 DataRepeater 控件的布局</span><span class="sxs-lookup"><span data-stu-id="0d57e-134">How to: Change the Layout of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="0d57e-135">DataRepeater 控件疑难解答</span><span class="sxs-lookup"><span data-stu-id="0d57e-135">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
