---
title: 如何：DataRepeater 控件 (Visual Studio) 中显示绑定的数据
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
ms.openlocfilehash: dbcd814edb78c54ce5629a1a8761142674fe6135
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684614"
---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a>如何：DataRepeater 控件 (Visual Studio) 中显示绑定的数据
最常用的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件将显示从数据库或其他数据源绑定的数据。  
  
 除了绑定控件，您可能想要添加其他控件，如静态标签或图像中每个项重复<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 有关详细信息，请参阅[如何：DataRepeater 控件中的控件显示未绑定](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)。  
  
 此外可以绑定到数据源在运行时通过设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>属性设置为`True`并将分配到的数据源<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A>属性。 在这种情况下，需要管理与数据源的所有交互。 有关详细信息，请参阅[DataRepeater 控件中的虚拟模式](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md)。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a>若要创建数据绑定 DataRepeater  
  
1.  拖动<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。  
  
2.  拖动调整大小和位置的句柄到大小和定位控件。  
  
     请注意，该控件有两个矩形区域。 上半部分区域是*项模板*; 控件添加到模板中将重复在每个项中<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件在运行时。 较低的区域是*视区*，其中将显示的项目。  
  
     您还可以调整大小和定位控件或项模板通过更改**大小**并**位置**属性窗口中的属性。  
  
3.  在 **“数据”** 菜单上，单击 **“显示数据源”**。  
  
    > [!NOTE]
    >  如果**数据源**窗口为空，则向其添加数据源。 有关详细信息，请参阅[添加新数据源](/visualstudio/data-tools/add-new-data-sources)。  
  
4.  在中**数据源**窗口中，选择包含你想要绑定的数据的表的顶级节点。  
  
5.  将表拖放类型更改`Details`通过单击`Details`表节点上的下拉列表中。  
  
6.  选择表节点，并将其拖动到项模板区域的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
     您可以指定哪些类型的控件将显示为每个字段。 有关详细信息，请参阅[设置从数据源窗口中拖动时创建的控件](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window)。  
  
## <a name="see-also"></a>请参阅
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [如何：DataRepeater 控件中显示未绑定的控件](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)
- [如何：使用两个 DataRepeater 控件 (Visual Studio) 创建母版/详细信息窗体](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
- [如何：更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
