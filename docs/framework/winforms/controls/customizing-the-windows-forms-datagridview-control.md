---
title: "自定义 Windows 窗体 DataGridView 控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d1246a8052af19057f7aa9d6729e34203177f8e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="customizing-the-windows-forms-datagridview-control"></a>自定义 Windows 窗体 DataGridView 控件
`DataGridView`控件提供可用于调整的外观和其单元格、 行和列的基本行为 （外观和感觉） 的多个属性。 如果你有特殊需求，超出的能力<xref:System.Windows.Forms.DataGridViewCellStyle>类中，但是，你也可以实现所有者描述控件或通过创建自定义单元格、 列和行扩展其功能。  
  
 若要绘制的单元格和行自己，可以处理各种`DataGridView`绘制事件。 若要修改现有功能或提供新功能，你可以创建您自己的类型派生自现有`DataGridViewCell`， `DataGridViewColumn`，和`DataGridViewRow`类型。 你还可以通过创建显示的单元格处于编辑模式的时你选择的控件的派生的类型中提供新的编辑功能。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 描述如何处理<xref:System.Windows.Forms.DataGridView.CellPainting>事件，以绘制单元格的手动。  
  
 [如何：自定义 Windows 窗体 DataGridView 控件中行的外观](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 描述如何处理<xref:System.Windows.Forms.DataGridView.RowPrePaint>和<xref:System.Windows.Forms.DataGridView.RowPostPaint>事件绘制自定义的渐变背景的行和内容，以便跨多个列。  
  
 [如何：通过扩展 Windows 窗体 DataGridView 控件中单元格和列的行为和外观进行自定义](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 描述如何创建自定义的类型派生自`DataGridViewCell`和`DataGridViewColumn`以便在鼠标指针停留在它们上时突出显示单元格。  
  
 [如何：在 Windows 窗体 DataGridView 控件的按钮列中禁用按钮](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 描述如何创建自定义的类型派生自<xref:System.Windows.Forms.DataGridViewButtonCell>和<xref:System.Windows.Forms.DataGridViewButtonColumn>为了在按钮列中显示禁用的按钮。  
  
 [如何：在 Windows 窗体 DataGridView 单元格中托管控件](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 描述如何实现`IDataGridViewEditingControl`接口以及如何创建自定义的类型派生自`DataGridViewCell`和`DataGridViewColumn`为了显示<xref:System.Windows.Forms.DateTimePicker>控制时的单元格处于编辑模式。  
  
## <a name="reference"></a>参考  
 <xref:System.Windows.Forms.DataGridView>  
 提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 提供的参考文档<xref:System.Windows.Forms.DataGridViewCell>类。  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 提供的参考文档<xref:System.Windows.Forms.DataGridViewRow>类。  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 提供的参考文档<xref:System.Windows.Forms.DataGridViewColumn>类。  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 提供的参考文档<xref:System.Windows.Forms.IDataGridViewEditingControl>接口。  
  
## <a name="related-sections"></a>相关章节  
 [Windows 窗体 DataGridView 控件中的基本格式和样式设置](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 提供一些主题，描述如何修改该控件的基本外观和单元数据的显示格式。  
  
## <a name="see-also"></a>另请参阅  
 [DataGridView 控件](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Windows 窗体 DataGridView 控件中的列类型](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
