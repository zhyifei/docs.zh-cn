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
# <a name="how-to-display-item-headers-in-a-datarepeater-control-visual-studio"></a>如何：DataRepeater 控件 (Visual Studio) 中显示项标头
中的项标头<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件提供可视的指示器时<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>处于选中状态。 当<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>属性设置为<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical>（默认值），每个项的左边显示项标头。 当<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>属性设置为<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>，在每个项的顶部显示的项标头。  
  
 首先选择它后，在由指定的颜色显示项标头<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>显示属性，并有一个白色箭头图标。  
  
> [!NOTE]
>  如果您设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>到<xref:System.Drawing.Color.White%2A>，选择符号首次选定项时将不可见。  
  
 中的字段时<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>具有焦点的项标头更改颜色<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>背景颜色和箭头图标更改为黑色。 如果数据已更改，铅笔符号显示项标头中。  
  
 默认宽度 (或高度时<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>属性设置为<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>) 项的标头是 15 个像素。 您可以通过设置更改宽度<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>属性。  
  
> [!NOTE]
>  如果<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>属性设置为小于 11 的值，将不会显示项标头中的指示符符号。  
  
 可以通过设置隐藏的项标头<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A>属性设置为**False**。 当<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A>设置为**False**，选择项的唯一指示是周围的点线<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>。  
  
> [!NOTE]
>  此外可以通过监视提供您自己选择指示器<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>的属性<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>中<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 有关详细信息，请参阅 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>。  
  
### <a name="to-change-the-appearance-of-item-headers"></a>若要更改项标题的外观  
  
1.  在 Windows 窗体设计器中选择的下半部分区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
    > [!NOTE]
    >  您必须选择控件的较低的区域。 如果选择项模板部分中，在属性窗口中将显示一组不同的属性。  
  
2.  在属性窗口中，使用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>要更改项标题的颜色属性。  
  
    > [!NOTE]
    >  如果您设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>到<xref:System.Drawing.Color.White%2A>，选择符号首次选定项时将不可见。  
  
3.  使用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>属性来更改项标题的宽度 （或高度）。  
  
    > [!NOTE]
    >  如果<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>属性设置为小于 11 的值，将不会显示项标头中的指示符符号。  
  
### <a name="to-hide-item-headers"></a>若要隐藏项标头  
  
1.  在 Windows 窗体设计器中选择的下半部分区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
    > [!NOTE]
    >  您必须选择控件的较低的区域。 如果选择项模板部分中，在属性窗口中将显示一组不同的属性。  
  
2.  在属性窗口中设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A>属性设置为**False**。  
  
     中的项后<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>是选择，唯一的指示将周围的点线<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>。  
  
## <a name="see-also"></a>请参阅
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [如何：更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [如何：更改 DataRepeater 控件的布局](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)
- [DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
