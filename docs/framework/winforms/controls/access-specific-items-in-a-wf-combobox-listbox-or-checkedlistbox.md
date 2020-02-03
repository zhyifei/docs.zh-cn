---
title: 访问 ComboBox、ListBox 或 CheckedListBox 控件中的特定项
ms.date: 03/30/2017
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
ms.openlocfilehash: 67673ec7f136f1466d4fd091e691324c53e7de06
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746321"
---
# <a name="how-to-access-specific-items-in-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="78897-102">如何：访问 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件中的特定项</span><span class="sxs-lookup"><span data-stu-id="78897-102">How to: Access Specific Items in a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="78897-103">访问 Windows 窗体组合框、列表框或选中列表框中的特定项是一项重要任务。</span><span class="sxs-lookup"><span data-stu-id="78897-103">Accessing specific items in a Windows Forms combo box, list box, or checked list box is an essential task.</span></span> <span data-ttu-id="78897-104">它使您能够以编程方式确定列表中任意给定位置的内容。</span><span class="sxs-lookup"><span data-stu-id="78897-104">It enables you to programmatically determine what is in a list, at any given position.</span></span>  
  
### <a name="to-access-a-specific-item"></a><span data-ttu-id="78897-105">访问特定项</span><span class="sxs-lookup"><span data-stu-id="78897-105">To access a specific item</span></span>  
  
1. <span data-ttu-id="78897-106">使用特定项的索引查询 `Items` 集合：</span><span class="sxs-lookup"><span data-stu-id="78897-106">Query the `Items` collection using the index of the specific item:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="78897-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78897-107">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="78897-108">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="78897-108">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
