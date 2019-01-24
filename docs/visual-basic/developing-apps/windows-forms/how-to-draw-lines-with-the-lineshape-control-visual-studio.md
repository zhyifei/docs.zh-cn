---
title: 如何：使用 LineShape 控件 (Visual Studio) 绘制直线
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
ms.openlocfilehash: 46360c01dfaf2c6fe199725a9ecfba2248c72d6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596223"
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a>如何：使用 LineShape 控件 (Visual Studio) 绘制直线
可以使用<xref:Microsoft.VisualBasic.PowerPacks.LineShape>控件在设计时和运行时窗体或容器上绘制水平线、 垂直线或对角线的线条。  
  
 **请注意**您的计算机可能会显示不同的名称或位置的某些 Visual Studio 用户界面元素中的以下说明进行操作。 这些元素取决于你所使用的 Visual Studio 版本和你所使用的设置。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-draw-a-line-at-design-time"></a>若要在设计时绘制线条  
  
1.  拖动<xref:Microsoft.VisualBasic.PowerPacks.LineShape>控件从**Visual Basic PowerPacks**选项卡中**工具箱**拖动到窗体或容器控件。  
  
2.  拖动调整大小并移动图柄来调整大小和位置的行。  
  
     您还可以调整大小和更改来定位行`X1`， `X2`， `Y1`，和`Y2`中的属性**属性**窗口。  
  
3.  在中**属性**窗口中，根据需要设置其他属性等`BorderStyle`或`BorderColor`来更改行的外观。  
  
### <a name="to-draw-a-line-at-run-time"></a>若要在运行时绘制线条  
  
1.  在“项目”菜单上，单击“添加引用”。  
  
2.  在中**添加引用**对话框中，选择**Microsoft.VisualBasic.PowerPacks.VS**，然后单击**确定**。  
  
3.  在中**代码编辑器**，添加`Imports`或`using`模块顶部的语句：  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  在 `Event` 过程中添加以下代码：  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a>请参阅
- <xref:Microsoft.VisualBasic.PowerPacks.LineShape>
- [Line 和 Shape 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
- [如何：使用 OvalShape 和 RectangleShape 控件绘制形状](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
