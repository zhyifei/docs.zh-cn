---
title: DataRepeater 控件简介 (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- repeating data
- DataRepeater, overview
- DataRepeater
ms.assetid: 78a52a1d-65f0-4ecb-97ff-53bc114300c5
ms.openlocfilehash: fc0cf9c358faf3e738eb3b24ec61577b88dbce4a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485711"
---
# <a name="introduction-to-the-datarepeater-control-visual-studio"></a>DataRepeater 控件简介 (Visual Studio)
Visual Basic Power Pack <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件是一个可滚动的控件容器，用于显示重复数据，例如数据库表中的行。 当你需要对数据布局具有更多控制权限时，可用它替代 <xref:System.Windows.Forms.DataGridView> 控件。 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> "重复"的一组相关控件通过滚动视图中创建多个实例。 这样用户就可以同时查看多个记录。  
  
## <a name="overview"></a>概述  
 在设计时<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件包含两个部分。 外部部分是*视区*、 滚动数据在运行时的显示。 内部 （顶级） 部分，称为*项模板*，是放置位置，将在运行时，通常一个控件对应的数据源中的每个字段的重复的控件。 属性和项模板中的控件封装在<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>属性。  
  
 在运行时，<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>复制到的虚拟<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>用于在每个记录滚动到视图时显示数据的对象。 您可以自定义的单个记录中显示<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件，例如，突出显示基于它所包含的值的字段。 有关详细信息，请参阅[如何： 更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)。  
  
 最常用于<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件将显示从数据库表或其他绑定的数据源的数据。 除了[!INCLUDE[vstecado](~/includes/vstecado-md.md)]数据对象<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件可以绑定到的任何类都实现<xref:System.Collections.IList>接口 （包括数组），任何实现类都<xref:System.ComponentModel.IListSource>接口，实现任何类<xref:System.ComponentModel.IBindingList>接口或实现任何类<xref:System.ComponentModel.IBindingListView>接口。  
  
### <a name="data-binding"></a>数据绑定  
 通常情况下，通过拖动字段来完成数据绑定**数据源**窗口拖到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 有关详细信息，请参阅[如何： 在 DataRepeater 控件中显示绑定数据](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)。  
  
 在使用大量的数据，可以设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>属性设置为`True`以显示可用数据的子集。 虚拟模式下需要从其的数据缓存实现<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>填充的并且您必须在运行时控制与数据缓存的所有交互。 有关详细信息，请参阅[DataRepeater 控件中的虚拟模式](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md)。  
  
 此外可以显示未绑定的控件上<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 例如，您可以对每个项显示重复的图像。 有关详细信息，请参阅[如何： 在 DataRepeater 控件中显示未绑定控件](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)。  
  
### <a name="events"></a>事件  
 有关最重要的事件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控制是在<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件，当新项滚动到视图时引发，和<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>事件，当选择了某项时引发。 可以使用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件以更改项的外观。 例如，可以突出显示负值。 使用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>事件以选择项时访问控件的值。  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件公开所有标准的控件事件在代码编辑器中。 但是，一些事件不应使用。 键盘和鼠标事件，如`KeyDown`， `Click`，并`MouseDown`将不会引发运行时由于<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件本身永远不会有焦点。  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>不在设计时公开的事件，因为仅在运行时创建。 如果你想要处理键盘和鼠标事件，您可以添加<xref:System.Windows.Forms.Panel>控制对<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>在设计时，然后处理的事件<xref:System.Windows.Forms.Panel>。 有关详细信息，请参阅[DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)。  
  
### <a name="customizations"></a>自定义  
 有很多种自定义外观和行为<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控制，请在运行时和设计时。 属性可以设置要更改颜色、 隐藏或修改项标头，将方向从垂直改为水平，以及更多。 有关详细信息，请参阅[如何： 更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)，[如何： 在 DataRepeater 控件中显示项标头](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)，和[如何： 更改的布局DataRepeater 控件](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)。  
  
 请注意，某些属性适用于<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件自身，而其他人仅适用于<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>。 请确保已选中，然后才能设置属性的控件的正确部分。 有关详细信息，请参阅[如何： 更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)。  
  
 其他自定义项包括控制能够添加或删除记录、 添加搜索功能和母版和详细信息的格式显示相关的数据。 有关详细信息，请参阅[如何： 禁用添加和删除 DataRepeater 项](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)，[如何： 在 DataRepeater 控件中搜索数据](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)，和[如何： 创建母版/详细信息窗体通过使用两个DataRepeater 控件 (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)。  
  
## <a name="see-also"></a>请参阅  
 [DataRepeater 控件](../../../visual-basic/developing-apps/windows-forms/datarepeater-control-visual-studio.md)  
 [演练：在 DataRepeater 控件中显示数据](../../../visual-basic/developing-apps/windows-forms/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio.md)  
 [DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
