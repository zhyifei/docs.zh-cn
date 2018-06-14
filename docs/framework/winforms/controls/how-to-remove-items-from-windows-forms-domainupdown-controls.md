---
title: 如何：从 Windows 窗体 DomainUpDown 控件移除项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: 702e5e2180148758c4b3775a5cc96a1365703166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532156"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a>如何：从 Windows 窗体 DomainUpDown 控件移除项
你可以从 Windows 窗体中移除项<xref:System.Windows.Forms.DomainUpDown>通过调用控件<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>或<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>方法<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>类。 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>方法中删除特定项，而<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>方法中移除一个项按其位置。  
  
### <a name="to-remove-an-item"></a>若要移除一个项  
  
-   使用<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>方法<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>类可按名称移除一个项。  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     -或-  
  
-   使用<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>方法来删除按其位置的项。  
  
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
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DomainUpDown>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>  
 [DomainUpDown 控件](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)  
 [DomainUpDown 控件概述](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)
