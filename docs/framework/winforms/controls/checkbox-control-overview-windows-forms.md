---
title: CheckBox 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
ms.openlocfilehash: b42816cf1bc0ce1ab6db0a2a436b17b0d4370d59
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737091"
---
# <a name="checkbox-control-overview-windows-forms"></a>CheckBox 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.CheckBox> 컨트롤은 특정 조건이 설정 또는 해제되었는지를 나타냅니다. 일반적으로 예/아니요 또는 True/False 선택을 사용자에게 제공하는 데 사용됩니다. 확인란 컨트롤을 그룹으로 사용하여 사용자가 하나 이상 선택할 수 있는 여러 선택 항목을 표시할 수 있습니다.  
  
 复选框控件类似于单选按钮控件，其中每个控件用于指示用户所做的选择。 它们的区别在于，一次只能选择一个组中的一个单选按钮。 但对于复选框控件，可能会选择任意数量的复选框。  
  
 可以使用简单的数据绑定将复选框连接到数据库中的元素。 可以使用 <xref:System.Windows.Forms.GroupBox> 控件对多个复选框进行分组。 这对于视觉外观和用户界面设计都很有用，因为可以在窗体设计器上一起移动分组控件。 有关详细信息，请参阅[Windows 窗体数据绑定](../windows-forms-data-binding.md)和[分组框控件](groupbox-control-windows-forms.md)。  
  
 <xref:System.Windows.Forms.CheckBox> 控件具有两个重要属性，<xref:System.Windows.Forms.CheckBox.Checked%2A> 和 <xref:System.Windows.Forms.CheckBox.CheckState%2A>。 <xref:System.Windows.Forms.CheckBox.Checked%2A> 属性返回 `true` 或 `false`。 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 属性返回 <xref:System.Windows.Forms.CheckState.Checked> 或 <xref:System.Windows.Forms.CheckState.Unchecked>;或者，如果 <xref:System.Windows.Forms.CheckBox.ThreeState%2A> 属性设置为 `true`，则 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 也可能返回 <xref:System.Windows.Forms.CheckState.Indeterminate>。 处于不确定状态时，将显示带有一个灰显外观的框，指示该选项不可用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.CheckBox>
- [방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [방법: Windows Forms CheckBox 클릭에 응답](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [CheckBox 컨트롤](checkbox-control-windows-forms.md)
