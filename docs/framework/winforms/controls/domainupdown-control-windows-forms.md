---
title: DomainUpDown 컨트롤
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: b538350a84e341d6b2759a7db28f8799f3777a86
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745838"
---
# <a name="domainupdown-control-windows-forms"></a>DomainUpDown 컨트롤(Windows Forms)
Windows 窗体 <xref:System.Windows.Forms.DomainUpDown> 控件看起来像是一个文本框和一对按钮的组合，用于在列表中上下移动。 控件显示并设置选项列表中的文本字符串。 用户可以通过单击 "上移" 和 "下移" 按钮在列表中移动、按向上键和向下键或键入与列表中的项匹配的字符串，来选择字符串。 此控件的一种可能用途是从按字母顺序排序的名称列表中选择项。 （若要对列表进行排序，请将 <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> 属性设置为 `true`。）此控件的功能非常类似于列表框或组合框，但占用的空间非常少。  
  
 控件的键属性为 <xref:System.Windows.Forms.DomainUpDown.Items%2A>、<xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>和 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>。 <xref:System.Windows.Forms.DomainUpDown.Items%2A> 属性包含其文本值显示在控件中的对象的列表。 如果 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> 设置为 `false`，则控件会自动完成用户键入的文本，并将其与列表中的某个值相匹配。 如果 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> 设置为 `true`，则在最后一项之后滚动会转到列表中的第一项，反之亦然。 控件的主要方法是 <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> 和 <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>。  
  
 此控件只显示文本字符串。 如果需要显示数值的控件，请使用 <xref:System.Windows.Forms.NumericUpDown> 控件。 有关详细信息，请参阅[NumericUpDown 控件](numericupdown-control-windows-forms.md)。  
  
## <a name="in-this-section"></a>섹션 내용  
 [DomainUpDown 컨트롤 개요](domainupdown-control-overview-windows-forms.md)  
 介绍 <xref:System.Windows.Forms.DomainUpDown> 控件的一般概念，该控件允许用户浏览文本字符串列表并从中进行选择。  
  
 [방법: 프로그래밍 방식으로 Windows Forms DomainUpDown 컨트롤에 항목 추가](how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 介绍如何指定 <xref:System.Windows.Forms.DomainUpDown> 控件应显示的文本字符串。  
  
 [방법: Windows Forms DomainUpDown 컨트롤에서 항목 제거](how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 描述如何在代码中删除 <xref:System.Windows.Forms.DomainUpDown> 控件中的项。  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.DomainUpDown>  
 이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 描述此类，并提供指向其所有成员的链接。  
  
## <a name="related-sections"></a>관련 섹션  
 [Windows Forms에서 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)  
 사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.
