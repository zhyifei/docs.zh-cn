---
title: 确定选中列表框中检查的项目
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: 5d93a63e9c1c6aae91ecfe83590c59450a565afe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182195"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>如何：确定 Windows 窗体 CheckedListBox 控件中的选定项
在 Windows 窗体<xref:System.Windows.Forms.CheckedListBox>控件中显示数据时，可以遍遍存储在<xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A>属性中的集合，或者使用<xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>方法单步执行列表以确定检查哪些项。 该方法<xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>以项索引号作为其参数，并返回`true`或`false`。 与您可能期望的相反，和<xref:System.Windows.Forms.ListBox.SelectedItems%2A><xref:System.Windows.Forms.ListBox.SelectedIndices%2A>属性不确定哪些项被检查;相反，属性不会确定哪些项被检查。它们确定突出显示哪些项。  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>确定选中的"检查列表"控件中的已检查项目  
  
1. 迭代集合，<xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A>从 0 开始，因为集合是零基的。 请注意，此方法将为您提供已检查项目列表中的物料编号，而不是整个列表中的项目编号。 因此，如果未选中列表中的第一项，并且检查了第二项，则下面的代码将显示"已检查的项目 1 = MyListItem2"之类的文本。  
  
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
  
     - 或 -  
  
2. 单步执行<xref:System.Windows.Forms.CheckedListBox.Items%2A>集合，从 0 开始，因为集合是零基的，并<xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>调用每个项的方法。 请注意，此方法将为您提供整个列表中的项目编号，因此，如果未选中列表中的第一个项目，并且检查了第二个项目，它将显示类似"项目 2 = MyListItem2"的内容。  
  
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
  
## <a name="see-also"></a>另请参阅

- [用于列出选项的 Windows 窗体控件](windows-forms-controls-used-to-list-options.md)
