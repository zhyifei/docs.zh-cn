---
title: 如何：在 DataRepeater 控件中显示绑定数据 (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
ms.openlocfilehash: b96fb33a0dcf80a86d1fcb6e219e5f35b1f7351c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589862"
---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a>如何：在 DataRepeater 控件中显示绑定数据 (Visual Studio)
最常见的用途<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件将显示从数据库或其他数据源绑定的数据。  
  
 除了绑定控件，你可能想要添加其他控件，如静态标签或图像，它将于每个项目重复<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 有关详细信息，请参阅[如何： 在 DataRepeater 控件中显示未绑定控件](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)。  
  
 此外可以绑定到数据源在运行时通过设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>属性`True`并分配到的数据源<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A>属性。 在这种情况下，你将需要以管理与数据源的所有交互。 有关详细信息，请参阅[DataRepeater 控件中的虚拟模式](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md)。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a>若要创建数据绑定 DataRepeater  
  
1.  拖动<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。  
  
2.  拖动调整大小和位置的句柄到大小以及定位该控件。  
  
     请注意该控件具有两个矩形区域。 上半部分区域是*项模板*; 将每个项中重复添加到模板控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件在运行时。 较低的区域是*视区*、 的项将显示。  
  
     您还可以调整大小和更改来定位控件或项模板**大小**和**位置**属性窗口中的属性。  
  
3.  在 **“数据”** 菜单上，单击 **“显示数据源”**。  
  
    > [!NOTE]
    >  如果**数据源**窗口为空，将数据源添加到它。 有关详细信息，请参阅[添加新数据源](/visualstudio/data-tools/add-new-data-sources)。  
  
4.  在**数据源**窗口中，选择包含你想要绑定的数据的表的顶级节点。  
  
5.  将该表拖放类型更改`Details`通过单击`Details`表节点上的下拉列表中。  
  
6.  选择表节点，然后将其拖到的项模板区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
     你可以指定哪些类型的控件将显示为每个字段。 有关详细信息，请参阅[设置从数据源窗口拖动时创建的控件](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window)。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [如何：在 DataRepeater 控件中显示未绑定的控件](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [如何： 使用两个 DataRepeater 控件 (Visual Studio) 中创建主/从窗体](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [如何：更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
