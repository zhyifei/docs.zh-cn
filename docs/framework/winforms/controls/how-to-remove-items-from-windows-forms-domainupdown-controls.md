---
title: 从 DomainUpDown 控件中删除项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: e52af5c5add4fda93e2b51c8afdb90c92e8d2f62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735765"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a>如何：从 Windows 窗体 DomainUpDown 控件移除项
可以通过调用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 类的 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 或 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 方法，从 Windows 窗体 <xref:System.Windows.Forms.DomainUpDown> 控件中删除项。 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 方法删除特定项，而 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 方法按项的位置删除该项。  
  
### <a name="to-remove-an-item"></a>删除项  
  
- 使用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 类的 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 方法，按名称删除项。  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     或  
  
- 使用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 方法按项的位置删除项。  
  
    ```vb  
    ' Removes the first item in the list.  
    DomainUpDown1.Items.RemoveAt(0)  
    ```  
  
    ```csharp  
    // Removes the first item in the list.  
    domainUpDown1.Items.RemoveAt(0);  
    ```  
  
    ```cpp  
    // Removes the first item in the list.  
    domainUpDown1->Items->RemoveAt(0);  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [DomainUpDown 控件](domainupdown-control-windows-forms.md)
- [DomainUpDown 控件概述](domainupdown-control-overview-windows-forms.md)
