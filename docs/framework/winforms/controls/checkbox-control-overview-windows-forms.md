---
title: "CheckBox 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a154a3f639102e3f3e2acd62626379e12bbd1344
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="checkbox-control-overview-windows-forms"></a>CheckBox 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.CheckBox> 控件指示特定条件处于打开开始关闭状态。 通常用于向用户显示 Yes/No 或 True/False 选项。 可以使用组中的复选框控件来显示用户可从中选择一个或多选的多个选项。  
  
 复选框控件的类似于单选按钮控件，在于每个用于指示用户所做的选择。 它们与组中的只有一个单选按钮在一次，可以选择的。 使用复选框控件，但是，任意数量的复选框可以选择。  
  
 复选框可能连接到数据库使用简单数据绑定中的元素。 可使用组合多个复选框<xref:System.Windows.Forms.GroupBox>控件。 这很有用的可视外观以及用户界面设计的因为分组的控件可以一起移动窗体设计器上。 有关详细信息，请参阅[Windows 窗体数据绑定](../../../../docs/framework/winforms/windows-forms-data-binding.md)和[GroupBox 控件](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)。  
  
 <xref:System.Windows.Forms.CheckBox>控件具有两个重要属性，<xref:System.Windows.Forms.CheckBox.Checked%2A>和<xref:System.Windows.Forms.CheckBox.CheckState%2A>。 <xref:System.Windows.Forms.CheckBox.Checked%2A>属性返回`true`或`false`。 <xref:System.Windows.Forms.CheckBox.CheckState%2A>属性返回<xref:System.Windows.Forms.CheckState.Checked>或<xref:System.Windows.Forms.CheckState.Unchecked>; 或者，如果<xref:System.Windows.Forms.CheckBox.ThreeState%2A>属性设置为`true`，<xref:System.Windows.Forms.CheckBox.CheckState%2A>也可能返回<xref:System.Windows.Forms.CheckState.Indeterminate>。 在不确定状态下，将显示带有框灰显的外观，以指示选项将不可用。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.CheckBox>  
 [如何：使用 Windows 窗体 CheckBox 控件设置选项](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [如何：响应 Windows 窗体 CheckBox 控件单击](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [CheckBox 控件](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
