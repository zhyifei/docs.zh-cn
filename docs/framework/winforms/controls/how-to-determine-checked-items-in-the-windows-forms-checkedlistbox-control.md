---
title: 确定 CheckedListBox 控件中的选中项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: 5854f7e6be759daeb604458ea8554d3c98ed39c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743251"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a><span data-ttu-id="a9e61-102">如何：确定 Windows 窗体 CheckedListBox 控件中的选定项</span><span class="sxs-lookup"><span data-stu-id="a9e61-102">How to: Determine Checked Items in the Windows Forms CheckedListBox Control</span></span>
<span data-ttu-id="a9e61-103">在 Windows 窗体 <xref:System.Windows.Forms.CheckedListBox> 控件中显示数据时，可以循环访问 <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> 属性中存储的集合，或使用 <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> 方法单步执行列表，以确定要检查哪些项。</span><span class="sxs-lookup"><span data-stu-id="a9e61-103">When presenting data in a Windows Forms <xref:System.Windows.Forms.CheckedListBox> control, you can either iterate through the collection stored in the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> property, or step through the list using the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method to determine which items are checked.</span></span> <span data-ttu-id="a9e61-104"><xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> 方法采用项索引号作为参数，并返回 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="a9e61-104">The <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method takes an item index number as its argument and returns `true` or `false`.</span></span> <span data-ttu-id="a9e61-105">与您可能期望的不同，<xref:System.Windows.Forms.ListBox.SelectedItems%2A> 和 <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> 属性不确定哪些项已选中;它们确定突出显示的项。</span><span class="sxs-lookup"><span data-stu-id="a9e61-105">Contrary to what you might expect, the <xref:System.Windows.Forms.ListBox.SelectedItems%2A> and <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> properties do not determine which items are checked; they determine which items are highlighted.</span></span>  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a><span data-ttu-id="a9e61-106">确定 CheckedListBox 控件中的选中项</span><span class="sxs-lookup"><span data-stu-id="a9e61-106">To determine checked items in a CheckedListBox control</span></span>  
  
1. <span data-ttu-id="a9e61-107">遍历 <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> 集合，从0开始，因为集合是从零开始的。</span><span class="sxs-lookup"><span data-stu-id="a9e61-107">Iterate through the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> collection, starting at 0 since the collection is zero-based.</span></span> <span data-ttu-id="a9e61-108">请注意，此方法将在选中项目列表中为您指定项目编号，而不是总体列表。</span><span class="sxs-lookup"><span data-stu-id="a9e61-108">Note that this method will give you the item number in the list of checked items, not the overall list.</span></span> <span data-ttu-id="a9e61-109">因此，如果未检查列表中的第一项并且选中第二项，则以下代码将显示类似于 "Checked Item 1 = MyListItem2" 的文本。</span><span class="sxs-lookup"><span data-stu-id="a9e61-109">So if the first item in the list is not checked and the second item is checked, the code below will display text like "Checked Item 1 = MyListItem2".</span></span>  
  
    ```vb  
    ' Determine if there are any items checked.  
    If CheckedListBox1.CheckedItems.Count <> 0 Then  
       ' If so, loop through all checked items and print results.  
       Dim x As Integer  
       Dim s As String = ""  
       For x = 0 To CheckedListBox1.CheckedItems.Count - 1  
          s = s & "Checked Item " & (x + 1).ToString & " = " & CheckedListBox1.CheckedItems(x).ToString & ControlChars.CrLf  
       Next x  
       MessageBox.Show(s)  
    End If  
    ```  
  
    ```csharp  
    // Determine if there are any items checked.  
    if(checkedListBox1.CheckedItems.Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       string s = "";  
       for(int x = 0; x < checkedListBox1.CheckedItems.Count ; x++)  
       {  
          s = s + "Checked Item " + (x+1).ToString() + " = " + checkedListBox1.CheckedItems[x].ToString() + "\n";  
       }  
       MessageBox.Show(s);  
    }  
    ```  
  
    ```cpp  
    // Determine if there are any items checked.  
    if(checkedListBox1->CheckedItems->Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       String ^ s = "";  
       for(int x = 0; x < checkedListBox1->CheckedItems->Count; x++)  
       {  
          s = String::Concat(s, "Checked Item ", (x+1).ToString(),  
             " = ", checkedListBox1->CheckedItems[x]->ToString(),  
             "\n");  
       }  
       MessageBox::Show(s);  
    }  
    ```  
  
     - <span data-ttu-id="a9e61-110">或 -</span><span class="sxs-lookup"><span data-stu-id="a9e61-110">or -</span></span>  
  
2. <span data-ttu-id="a9e61-111">单步执行 <xref:System.Windows.Forms.CheckedListBox.Items%2A> 集合，从0开始，因为集合从零开始，并为每个项调用 <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="a9e61-111">Step through the <xref:System.Windows.Forms.CheckedListBox.Items%2A> collection, starting at 0 since the collection is zero-based, and call the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method for each item.</span></span> <span data-ttu-id="a9e61-112">请注意，此方法将向你显示总体列表中的项编号，因此，如果未检查列表中的第一项并且检查第二项，则会显示类似于 "Item 2 = MyListItem2" 的内容。</span><span class="sxs-lookup"><span data-stu-id="a9e61-112">Note that this method will give you the item number in the overall list, so if the first item in the list is not checked and the second item is checked, it will display something like "Item 2 = MyListItem2".</span></span>  
  
    ```vb  
    Dim i As Integer  
    Dim s As String  
    s = "Checked Items:" & ControlChars.CrLf  
    For i = 0 To (CheckedListBox1.Items.Count - 1)  
       If CheckedListBox1.GetItemChecked(i) = True Then  
          s = s & "Item " & (i + 1).ToString & " = " & CheckedListBox1.Items(i).ToString & ControlChars.CrLf  
       End If  
    Next  
    MessageBox.Show(s)  
    ```  
  
    ```csharp  
    int i;  
    string s;   
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1.Items.Count-1); i++)  
    {  
       if (checkedListBox1.GetItemChecked(i))  
       {  
          s = s + "Item " + (i+1).ToString() + " = " + checkedListBox1.Items[i].ToString() + "\n";  
       }  
    }  
    MessageBox.Show (s);  
    ```  
  
    ```cpp  
    int i;  
    String ^ s;   
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1->Items->Count-1); i++)  
    {  
       if (checkedListBox1->GetItemChecked(i))  
       {  
          s = String::Concat(s, "Item ", (i+1).ToString(), " = ",  
             checkedListBox1->Item[i]->ToString(), "\n");  
       }  
    }  
    MessageBox::Show(s);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a9e61-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9e61-113">See also</span></span>

- [<span data-ttu-id="a9e61-114">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="a9e61-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
