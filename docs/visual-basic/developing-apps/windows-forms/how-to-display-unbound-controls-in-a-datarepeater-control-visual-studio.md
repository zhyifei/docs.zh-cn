---
title: 如何：DataRepeater 控件 (Visual Studio) 中显示未绑定的控件
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
ms.openlocfilehash: a20e1ba83d1963bc3d4c135817767ee02fcbdeda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730784"
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a>如何：DataRepeater 控件 (Visual Studio) 中显示未绑定的控件
除了绑定控件，您可能想要添加到其他控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>，如静态标签或图像中每个项重复<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
> [!NOTE]
>  您还必须具有至少一个绑定的控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>或执行任何操作将在运行时显示。  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a>向 DataRepeater 添加未绑定的控件  
  
1.  拖动<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。  
  
2.  拖动调整大小和位置的句柄到大小和定位控件。  
  
     您还可以调整大小和定位该控件通过更改**大小**并**位置**属性窗口中的属性。  
  
3.  添加至少一个数据绑定控件绑定到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 有关详细信息，请参阅[如何：显示在 DataRepeater 控件中绑定数据](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)。  
  
4.  将控件从**工具箱**上的项模板区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
     请注意，该控件有两个矩形区域。 内部区域是*项模板*; 控件添加到模板中将重复在每个项中<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件在运行时。 是外部的区域*视区*，其中将显示的项目; 添加到此区域的控件将不会显示在运行时。  
  
## <a name="see-also"></a>请参阅
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [如何：DataRepeater 控件中显示绑定的数据](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [如何：使用两个 DataRepeater 控件 (Visual Studio) 创建母版/详细信息窗体](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
- [如何：更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
