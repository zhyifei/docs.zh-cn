---
title: "如何：更改 DataRepeater 控件的外观 (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, customizing
- DataRepeater, changing run time appearance
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 585ff4c942185f3199fe6e9e47a4ebd9f1f0a478
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-a-datarepeater-control-visual-studio"></a>如何：更改 DataRepeater 控件的外观 (Visual Studio)
你可以更改的外观<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件在设计时通过设置属性或在运行时通过处理<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件。  
  
 在选中的项目模板部分的控件的设计时设置的属性将为每个重复<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>在运行时。 将属性与外观相关的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件本身将在运行时仍将容器的一部分，仅当发现了可见 (例如，如果<xref:System.Windows.Forms.Control.Padding%2A>属性设置为较大的值)。  
  
 在运行时，与外观相关的属性可以基于设置条件。 例如，在日程安排的应用程序，你可能会更改要逾期未付项时，用户则发出警告的项的背景色。 在<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件处理程序，如果条件语句中设置一个属性如`If…Then`，还必须使用`Else`子句用于指定当不满足条件的外观。  
  
### <a name="to-change-the-appearance-at-design-time"></a>若要更改在设计时的外观  
  
1.  在 Windows 窗体设计器中，选择的项模板 （上部） 区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
2.  在属性窗口中，选择属性，并将值更改。 影响外观的常见属性包括<xref:System.Windows.Forms.Control.BackColor%2A>， <xref:System.Windows.Forms.Control.BackgroundImage%2A>， <xref:System.Windows.Forms.Panel.BorderStyle%2A>，和<xref:System.Windows.Forms.Control.ForeColor%2A>。  
  
### <a name="to-change-the-appearance-at-run-time"></a>若要更改在运行时的外观  
  
1.  在代码编辑器中，在事件下拉列表中，单击**DrawItem**。  
  
2.  在<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件处理程序添加代码以设置的属性：  
  
     [!code-csharp[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="example"></a>示例  
 一些常见的自定义项<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件包括在交替颜色和更改基于条件的字段的颜色显示行。 下面的示例演示如何执行这些自定义设置。 此示例假定你有<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>绑定到 Northwind 数据库中的产品表的控件。  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.vb)]
 [!code-csharp[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.cs)]  
  
 请注意，对于这两个自定义，必须提供代码以设置条件的双方的属性。 如果不指定`Else`条件，你将在运行时中看到意外的结果。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>  
 [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [如何：在 DataRepeater 控件中显示绑定数据](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [如何：在 DataRepeater 控件中显示未绑定的控件](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [如何：在 DataRepeater 控件中显示项标题](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
