---
title: "如何：在 DataRepeater 控件中显示未绑定的控件 (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3e96219f0ea8b8198967e9fa3c6e5afb824352db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a>如何：在 DataRepeater 控件中显示未绑定的控件 (Visual Studio)
除了绑定控件，你可能想要添加到其他控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>，如静态标签或图像，它在每个项重复<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
> [!NOTE]
>  你还必须具有至少一个绑定的控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>或执行任何操作将在运行时显示。  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a>向 DataRepeater 添加未绑定的控件  
  
1.  拖动<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。  
  
2.  拖动调整大小和位置的句柄到大小以及定位该控件。  
  
     您还可以调整大小和通过更改定位该控件**大小**和**位置**属性窗口中的属性。  
  
3.  至少一个数据绑定将控件添加到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 有关详细信息，请参阅[如何： 在 DataRepeater 控件中显示绑定数据](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)。  
  
4.  拖动某个控件从**工具箱**拖动的项模板区域到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
     请注意该控件具有两个矩形区域。 内部区域是*项模板*; 将每个项中重复添加到模板控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件在运行时。 外部区域是*视区*，其中的项将显示; 添加到此区域的控件将不会显示在运行时。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [如何：在 DataRepeater 控件中显示绑定数据](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [如何： 使用两个 DataRepeater 控件 (Visual Studio) 中创建主/从窗体](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [如何：更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
