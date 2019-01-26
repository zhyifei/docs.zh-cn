---
title: 如何：DataRepeater 控件 (Visual Studio) 中搜索数据
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, implementing search
- DataRepeater, searching data
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
ms.openlocfilehash: 514e72afc9570071f57e385574456ff7d716bad7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654381"
---
# <a name="how-to-search-data-in-a-datarepeater-control-visual-studio"></a>如何：DataRepeater 控件 (Visual Studio) 中搜索数据
当使用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>包含很多条记录，你可能希望允许的用户搜索的特定记录的控件。 而不是控件本身中搜索数据，您可以通过查询基础实现搜索<xref:System.Windows.Forms.BindingSource>。 如果找到该项，则可以使用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A>属性选择的项，并滚动到视图。  
  
### <a name="to-implement-search"></a>若要实现搜索  
  
1.  拖动<xref:System.Windows.Forms.TextBox>控件从**工具箱**拖到窗体包含<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
2.  在属性窗口中更改**名称**属性设置为**SearchTextBox**。  
  
3.  拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖到窗体包含<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
4.  在属性窗口中更改**名称**属性设置为**SearchButton**。 更改**文本**属性设置为**搜索**。  
  
5.  双击 <xref:System.Windows.Forms.Button> 控件打开代码编辑器，并将以下代码添加到 `SearchButton_Click` 事件处理程序中。  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     替换*ProductsBindingSource*的名称<xref:System.Windows.Forms.BindingSource>为你<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>，并替换*ProductID*具有你想要搜索的字段的名称。  
  
## <a name="see-also"></a>请参阅
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [如何：更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
