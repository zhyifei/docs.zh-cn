---
title: 如何：确定 Windows 窗体 CheckedListBox 控件中的选定项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: 10793053934dce0bb83113004a79f1c265f5f267
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316565"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a><span data-ttu-id="5f0e3-102">如何：确定 Windows 窗体 CheckedListBox 控件中的选定项</span><span class="sxs-lookup"><span data-stu-id="5f0e3-102">How to: Determine Checked Items in the Windows Forms CheckedListBox Control</span></span>
<span data-ttu-id="5f0e3-103">在 Windows 窗体中显示数据时<xref:System.Windows.Forms.CheckedListBox>控件，您可以或者循环访问集合中存储<xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A>属性或逐步执行列表使用<xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>方法，以确定未选中的项。</span><span class="sxs-lookup"><span data-stu-id="5f0e3-103">When presenting data in a Windows Forms <xref:System.Windows.Forms.CheckedListBox> control, you can either iterate through the collection stored in the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> property, or step through the list using the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method to determine which items are checked.</span></span> <span data-ttu-id="5f0e3-104"><xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>方法将项索引号作为其参数并返回`true`或`false`。</span><span class="sxs-lookup"><span data-stu-id="5f0e3-104">The <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method takes an item index number as its argument and returns `true` or `false`.</span></span> <span data-ttu-id="5f0e3-105">与您所料，相反<xref:System.Windows.Forms.ListBox.SelectedItems%2A>和<xref:System.Windows.Forms.ListBox.SelectedIndices%2A>属性不用于确定未选中的项; 它们确定哪些项会突出显示。</span><span class="sxs-lookup"><span data-stu-id="5f0e3-105">Contrary to what you might expect, the <xref:System.Windows.Forms.ListBox.SelectedItems%2A> and <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> properties do not determine which items are checked; they determine which items are highlighted.</span></span>  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a><span data-ttu-id="5f0e3-106">若要确定 CheckedListBox 控件中的选中的项</span><span class="sxs-lookup"><span data-stu-id="5f0e3-106">To determine checked items in a CheckedListBox control</span></span>  
  
1. <span data-ttu-id="5f0e3-107">循环访问<xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A>0 开始，因为集合是从零开始的集合。</span><span class="sxs-lookup"><span data-stu-id="5f0e3-107">Iterate through the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> collection, starting at 0 since the collection is zero-based.</span></span> <span data-ttu-id="5f0e3-108">请注意，此方法将向您提供的项编号的列表中选中的项，不是整个列表。</span><span class="sxs-lookup"><span data-stu-id="5f0e3-108">Note that this method will give you the item number in the list of checked items, not the overall list.</span></span> <span data-ttu-id="5f0e3-109">因此，如果未选中列表中的第一个项并选中第二个项，下面的代码将显示类似文本"选中的项 1 = MyListItem2"。</span><span class="sxs-lookup"><span data-stu-id="5f0e3-109">So if the first item in the list is not checked and the second item is checked, the code below will display text like "Checked Item 1 = MyListItem2".</span></span>  
  
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
  
     - <span data-ttu-id="5f0e3-110">或 -</span><span class="sxs-lookup"><span data-stu-id="5f0e3-110">or -</span></span>  
  
2. <span data-ttu-id="5f0e3-111">单步执行<xref:System.Windows.Forms.CheckedListBox.Items%2A>集合，从 0 开始因为集合是从零开始，并调用<xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>方法的每个项。</span><span class="sxs-lookup"><span data-stu-id="5f0e3-111">Step through the <xref:System.Windows.Forms.CheckedListBox.Items%2A> collection, starting at 0 since the collection is zero-based, and call the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method for each item.</span></span> <span data-ttu-id="5f0e3-112">请注意，此方法将向您提供的项编号在总体的列表中，因此如果第一项不会检查列表并选中第二个项，它将显示类似于"项 2 = MyListItem2"。</span><span class="sxs-lookup"><span data-stu-id="5f0e3-112">Note that this method will give you the item number in the overall list, so if the first item in the list is not checked and the second item is checked, it will display something like "Item 2 = MyListItem2".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5f0e3-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f0e3-113">See also</span></span>

- [<span data-ttu-id="5f0e3-114">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="5f0e3-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
