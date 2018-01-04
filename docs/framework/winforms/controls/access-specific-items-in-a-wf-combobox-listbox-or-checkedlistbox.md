---
title: "如何：访问 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件中的特定项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ComboBox control [Windows Forms], accessing items
- ListBox control [Windows Forms], returning item information
- list boxes [Windows Forms], accessing items
- ListBox control [Windows Forms], accessing items
- combo boxes [Windows Forms], accessing items
- CheckedListBox control [Windows Forms], accessing items
ms.assetid: 1216742f-bcf9-4ff8-8a62-d7c9053c2b96
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 400e367581ea773d88320e593aa525d812ea0238
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-access-specific-items-in-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="63d8e-102">如何：访问 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件中的特定项</span><span class="sxs-lookup"><span data-stu-id="63d8e-102">How to: Access Specific Items in a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="63d8e-103">访问 Windows 窗体组合框、 列表框中或选中的列表框中的特定项是一项基本任务。</span><span class="sxs-lookup"><span data-stu-id="63d8e-103">Accessing specific items in a Windows Forms combo box, list box, or checked list box is an essential task.</span></span> <span data-ttu-id="63d8e-104">它使您可以以编程方式确定在任何给定位置的列表中的内容。</span><span class="sxs-lookup"><span data-stu-id="63d8e-104">It enables you to programmatically determine what is in a list, at any given position.</span></span>  
  
### <a name="to-access-a-specific-item"></a><span data-ttu-id="63d8e-105">若要访问特定项</span><span class="sxs-lookup"><span data-stu-id="63d8e-105">To access a specific item</span></span>  
  
1.  <span data-ttu-id="63d8e-106">查询`Items`使用特定项的索引集合：</span><span class="sxs-lookup"><span data-stu-id="63d8e-106">Query the `Items` collection using the index of the specific item:</span></span>  
  
    ```vb  
    Private Function GetItemText(i As Integer) As String  
       ' Return the text of the item using the index:  
       Return ComboBox1.Items(i).ToString  
    End Function  
    ```  
  
    ```csharp  
    private string GetItemText(int i)  
    {  
       // Return the text of the item using the index:  
       return (comboBox1.Items[i].ToString());  
    }  
    ```  
  
    ```cpp  
    private:  
       String^ GetItemText(int i)  
       {  
          // Return the text of the item using the index:  
          return (comboBox1->Items->Item[i]->ToString());  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="63d8e-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="63d8e-107">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 <xref:System.Windows.Forms.CheckedListBox>  
 [<span data-ttu-id="63d8e-108">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="63d8e-108">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
