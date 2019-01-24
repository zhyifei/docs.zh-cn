---
title: 如何：访问特定于 Windows 中的项窗体 ComboBox、 ListBox 或 CheckedListBox 控件
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
ms.openlocfilehash: b6478c24550f9f32ea75899521f7aa610ef12955
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656695"
---
# <a name="how-to-access-specific-items-in-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="f117f-102">如何：访问特定于 Windows 中的项窗体 ComboBox、 ListBox 或 CheckedListBox 控件</span><span class="sxs-lookup"><span data-stu-id="f117f-102">How to: Access Specific Items in a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="f117f-103">访问 Windows 窗体组合框、 列表框中或选中的列表框中的特定项是不可或缺的任务。</span><span class="sxs-lookup"><span data-stu-id="f117f-103">Accessing specific items in a Windows Forms combo box, list box, or checked list box is an essential task.</span></span> <span data-ttu-id="f117f-104">这样，您可以以编程方式确定在列表中，任何给定位置处的内容。</span><span class="sxs-lookup"><span data-stu-id="f117f-104">It enables you to programmatically determine what is in a list, at any given position.</span></span>  
  
### <a name="to-access-a-specific-item"></a><span data-ttu-id="f117f-105">若要访问特定项</span><span class="sxs-lookup"><span data-stu-id="f117f-105">To access a specific item</span></span>  
  
1.  <span data-ttu-id="f117f-106">查询`Items`集合使用的特定项的索引：</span><span class="sxs-lookup"><span data-stu-id="f117f-106">Query the `Items` collection using the index of the specific item:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f117f-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="f117f-107">See also</span></span>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="f117f-108">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="f117f-108">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
