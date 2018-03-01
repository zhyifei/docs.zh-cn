---
title: "如何： 使用两个 DataRepeater 控件 (Visual Studio) 创建主 / 从窗体"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f17cb86c3ea0ea056291a51becd7ecf9f73d0a73
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a>如何：使用两个 DataRepeater 控件创建主/详细信息窗体 (Visual Studio)
你可以使用两个或多个显示相关的数据<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件创建主/从窗体。 例如，你可能想要一个中显示一个客户列表<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>，并当用户选择某个客户，在第二个中显示的该客户的订单列表<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>。  
  
 你可以通过将共享相同的主表节点从的详细信息项显示相关的数据**数据源**窗口拖到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 例如，如果你有了 Customers 表和相关的 Orders 表的数据源，你看到这两个表为在树视图中的顶级节点**数据源**窗口。 展开客户节点，以便可以查看的列。 请注意，在列表中的最后一列表示 Orders 表的可展开节点。 此节点表示客户的相关的订单。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a>若要在两个 DataRepeater 控件中显示相关的数据  
  
1.  将两个<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。  
  
2.  拖动调整大小和位置手柄以调整控件大小，并将它们放置并排显示。  
  
3.  在 **“数据”** 菜单上，单击 **“显示数据源”**。  
  
    > [!NOTE]
    >  如果**数据源**窗口为空，将数据源添加到它。 有关详细信息，请参阅[添加新数据源](/visualstudio/data-tools/add-new-data-sources)。  
  
4.  在**数据源**窗口中，选择主表的顶级节点。  
  
5.  将主表的拖放类型更改为详细信息，通过单击**详细信息**表节点上的下拉列表中。  
  
6.  将主表节点拖到第一个项模板区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
7.  展开主表节点并选择相关表的详细信息节点。  
  
8.  将详细信息表的拖放类型更改为详细信息，通过单击**详细信息**表节点上的下拉列表中。  
  
9. 选择此表节点，然后将其拖到第二个项模板区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [如何：在 DataRepeater 控件中显示绑定数据](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [如何：在 Windows 窗体应用程序中显示相关数据](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [如何：更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
