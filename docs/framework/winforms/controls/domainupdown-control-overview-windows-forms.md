---
title: "DomainUpDown 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5a86dc6c56c3afff8d8a3a4ca2c5d5efa8eac1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="domainupdown-control-overview-windows-forms"></a>DomainUpDown 控件概述（Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.DomainUpDown>控件是实质上是一个文本框的组合以及一对用于访问列表上移或下移按钮。 该控件显示，并设置从选项列表中的文本字符串。 用户可以选择字符串，通过单击向上和向下按钮来浏览列表，按向上和向下箭头键，或通过键入与列表中的项匹配的字符串。 对于此控件的可能用途之一是用于从名称按字母顺序排序列表中选择项。  
  
> [!NOTE]
>  若要对列表进行排序，将设置<xref:System.Windows.Forms.DomainUpDown.Sorted%2A>属性`true`。  
  
 此控件的功能是非常类似于列表框或组合框中，但其占用很少的空间。  
  
## <a name="key-properties"></a>键属性  
 控件的主要属性包括<xref:System.Windows.Forms.DomainUpDown.Items%2A>， <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>，和<xref:System.Windows.Forms.DomainUpDown.Wrap%2A>。 <xref:System.Windows.Forms.DomainUpDown.Items%2A>属性包含的控件中显示其文本值的对象的列表。 如果<xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>设置为`false`，该控件自动完成用户键入，并与列表中的值进行匹配的文本。 如果<xref:System.Windows.Forms.DomainUpDown.Wrap%2A>设置为`true`，滚过最后一项将转到第一项在列表中，反之亦然。 控件的主要方法是<xref:System.Windows.Forms.DomainUpDown.UpButton%2A>和<xref:System.Windows.Forms.DomainUpDown.DownButton%2A>。  
  
 此控件显示仅文本字符串。 如果你希望显示数字值的控件，使用<xref:System.Windows.Forms.NumericUpDown>控件。 有关详细信息，请参阅[NumericUpDown 控件概述](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DomainUpDown>  
 [DomainUpDown 控件](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)
