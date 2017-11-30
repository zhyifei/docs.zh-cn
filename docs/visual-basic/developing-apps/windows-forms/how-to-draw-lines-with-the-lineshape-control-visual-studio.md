---
title: "如何：使用 LineShape 控件绘制直线 (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f170250dde2f6db31ed68908936c0e9714a7e846
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a>如何：使用 LineShape 控件绘制直线 (Visual Studio)
你可以使用<xref:Microsoft.VisualBasic.PowerPacks.LineShape>控件在设计时和运行时窗体或容器上绘制水平线、 垂直线或对角线行。  
  
 **请注意**你的计算机中出现可能会不同名称或位置的某些 Visual Studio 用户界面元素下面的说明。 这些元素取决于你所使用的 Visual Studio 版本和你所使用的设置。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-draw-a-line-at-design-time"></a>若要在设计时绘制线条  
  
1.  拖动<xref:Microsoft.VisualBasic.PowerPacks.LineShape>控件从**Visual Basic PowerPacks**选项卡中**工具箱**将拖动到窗体或容器的控件。  
  
2.  拖动调整大小并移动图柄大小和位置的行。  
  
     您还可以调整大小和通过更改定位直线`X1`， `X2`， `Y1`，和`Y2`中的属性**属性**窗口。  
  
3.  在**属性**窗口中，根据需要设置其他属性如`BorderStyle`或`BorderColor`若要更改的行的外观。  
  
### <a name="to-draw-a-line-at-run-time"></a>若要在运行时绘制线条  
  
1.  在“项目”菜单上，单击“添加引用”。  
  
2.  在**添加引用**对话框中，选择**Microsoft.VisualBasic.PowerPacks.VS**，然后单击**确定**。  
  
3.  在**代码编辑器**，添加`Imports`或`using`语句模块的顶部：  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  在 `Event` 过程中添加以下代码：  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>  
 [Line 和 Shape 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [如何：使用 OvalShape 和 RectangleShape 控件绘制形状](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
