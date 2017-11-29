---
title: "如何：在 DataRepeater 控件中搜索数据 (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, implementing search
- DataRepeater, searching data
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a3ed7138c142a83584ecd19ccaebe0e31e421ce3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-search-data-in-a-datarepeater-control-visual-studio"></a>如何：在 DataRepeater 控件中搜索数据 (Visual Studio)
如果要使用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>包含多个记录，你可能想让的用户搜索特定记录的控件。 而不是在该控件本身中搜索数据，你可以通过查询基础实现搜索<xref:System.Windows.Forms.BindingSource>。 如果找到该项，则可以使用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A>属性选择的项并滚动到视图。  
  
### <a name="to-implement-search"></a>若要实现搜索  
  
1.  拖动<xref:System.Windows.Forms.TextBox>控件从**工具箱**拖到窗体包含<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
2.  在属性窗口中，更改**名称**属性**SearchTextBox**。  
  
3.  拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖到窗体包含<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
4.  在属性窗口中，更改**名称**属性**SearchButton**。 更改**文本**属性**搜索**。  
  
5.  双击 <xref:System.Windows.Forms.Button> 控件打开代码编辑器，并将以下代码添加到 `SearchButton_Click` 事件处理程序中。  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     替换*ProductsBindingSource*同名的<xref:System.Windows.Forms.BindingSource>为你<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>，并将*ProductID*替换为你想要搜索的字段的名称。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [如何：更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
