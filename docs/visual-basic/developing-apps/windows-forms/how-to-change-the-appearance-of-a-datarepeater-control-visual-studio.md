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
# <a name="how-to-change-the-appearance-of-a-datarepeater-control-visual-studio"></a>如何：更改 DataRepeater 控件 (Visual Studio) 的外观
您可以更改的外观<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件在设计时通过设置属性或在运行时处理<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件。  
  
 在选中项模板部分的控件的设计时设置的属性将为每个重复<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>在运行时。 与外观相关的属性<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件本身会显示在仅当容器的一部分保留为已发现的运行时 (例如，如果<xref:System.Windows.Forms.Control.Padding%2A>属性设置为较大的值)。  
  
 在运行时，与外观相关的属性可以基于设置的条件。 例如，在计划的应用程序，可能会更改来警告用户，当某项已过截止日期的项的背景色。 在中<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件处理程序，如果在条件语句中设置属性等`If…Then`，则还必须使用`Else`子句来指定不满足条件时的外观。  
  
### <a name="to-change-the-appearance-at-design-time"></a>若要更改在设计时外观  
  
1.  在 Windows 窗体设计器中选择的项模板 （上限） 区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
2.  在属性窗口中选择属性并更改值。 影响外观的常见属性包括<xref:System.Windows.Forms.Control.BackColor%2A>， <xref:System.Windows.Forms.Control.BackgroundImage%2A>， <xref:System.Windows.Forms.Panel.BorderStyle%2A>，和<xref:System.Windows.Forms.Control.ForeColor%2A>。  
  
### <a name="to-change-the-appearance-at-run-time"></a>若要在运行时更改外观  
  
1.  在代码编辑器中，在事件下拉列表中，单击**DrawItem**。  
  
2.  在<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件处理程序添加代码以设置属性：  
  
     [!code-csharp[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="example"></a>示例  
 一些常见的自定义项<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件包括显示中交替颜色和更改基于条件的字段的颜色的行。 下面的示例演示如何执行这些自定义。 此示例假定你拥有<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件绑定到 Northwind 数据库中的产品表。  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.vb)]
 [!code-csharp[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.cs)]  
  
 请注意，对于这两个自定义，你必须提供代码来设置条件的双方的属性。 如果未指定`Else`条件，您将在运行时看到意外的结果。  
  
## <a name="see-also"></a>请参阅
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>
- [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [如何：DataRepeater 控件中显示绑定的数据](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [如何：DataRepeater 控件中显示未绑定的控件](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)
- [如何：DataRepeater 控件中显示项标头](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
