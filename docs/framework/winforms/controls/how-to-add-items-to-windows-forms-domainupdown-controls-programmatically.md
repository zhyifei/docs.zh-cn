---
title: 以编程方式向 DomainUpDown 控件添加项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 2e9f51fa051bf9b62e95f289db97bffd83450036
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745589"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a>如何：以编程方式向 Windows 窗体 DomainUpDown 控件添加项
您可以在代码中向 Windows 窗体 <xref:System.Windows.Forms.DomainUpDown> 控件添加项。 调用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 类的 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 或 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 方法，将项添加到控件的 <xref:System.Windows.Forms.DomainUpDown.Items%2A> 属性。 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 方法将项添加到集合的末尾，而 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 方法在指定位置添加项。  
  
### <a name="to-add-a-new-item"></a>添加新项  
  
1. 使用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 方法将项添加到项列表的末尾。  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     或  
  
2. 使用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 方法可在列表中的指定位置插入项。  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [DomainUpDown 控件](domainupdown-control-windows-forms.md)
- [DomainUpDown 控件概述](domainupdown-control-overview-windows-forms.md)
