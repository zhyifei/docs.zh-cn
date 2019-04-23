---
title: 如何：在 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件中添加或移除项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- combo boxes [Windows Forms], adding items
- list boxes [Windows Forms], removing items
- ComboBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], adding and removing items
- list boxes [Windows Forms], adding items
- combo boxes [Windows Forms], removing items
- CheckedListBox control [Windows Forms], adding and removing items
ms.assetid: 7224c8d2-4118-443e-ae1e-d7c17d1e69ee
ms.openlocfilehash: bd6614c76c63a44a7367ac7c7113c4db260c9a02
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322727"
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="9ef12-102">如何：在 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件中添加或移除项</span><span class="sxs-lookup"><span data-stu-id="9ef12-102">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="9ef12-103">项可以添加到 Windows 窗体组合框中，列表框中，或检查列表框中有许多种情况下，因为这些控件可以绑定到各种数据源。</span><span class="sxs-lookup"><span data-stu-id="9ef12-103">Items can be added to a Windows Forms combo box, list box, or checked list box in a variety of ways, because these controls can be bound to a variety of data sources.</span></span> <span data-ttu-id="9ef12-104">但是，本主题演示了最简单方法，并且不需要数据绑定。</span><span class="sxs-lookup"><span data-stu-id="9ef12-104">However, this topic demonstrates the simplest method and requires no data binding.</span></span> <span data-ttu-id="9ef12-105">显示的项通常是字符串;但是，可以使用任何对象。</span><span class="sxs-lookup"><span data-stu-id="9ef12-105">The items displayed are usually strings; however, any object can be used.</span></span> <span data-ttu-id="9ef12-106">在控件中显示的文本是由该对象返回的值`ToString`方法。</span><span class="sxs-lookup"><span data-stu-id="9ef12-106">The text that is displayed in the control is the value returned by the object's `ToString` method.</span></span>  
  
### <a name="to-add-items"></a><span data-ttu-id="9ef12-107">若要添加项目</span><span class="sxs-lookup"><span data-stu-id="9ef12-107">To add items</span></span>  
  
1. <span data-ttu-id="9ef12-108">通过使用添加到列表的字符串或对象`Add`方法的`ObjectCollection`类。</span><span class="sxs-lookup"><span data-stu-id="9ef12-108">Add the string or object to the list by using the `Add` method of the `ObjectCollection` class.</span></span> <span data-ttu-id="9ef12-109">使用引用集合`Items`属性：</span><span class="sxs-lookup"><span data-stu-id="9ef12-109">The collection is referenced using the `Items` property:</span></span>  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - <span data-ttu-id="9ef12-110">或 -</span><span class="sxs-lookup"><span data-stu-id="9ef12-110">or -</span></span>  
  
2. <span data-ttu-id="9ef12-111">在使用列表中的所需点处插入字符串或对象`Insert`方法：</span><span class="sxs-lookup"><span data-stu-id="9ef12-111">Insert the string or object at the desired point in the list with the `Insert` method:</span></span>  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - <span data-ttu-id="9ef12-112">或 -</span><span class="sxs-lookup"><span data-stu-id="9ef12-112">or -</span></span>  
  
3. <span data-ttu-id="9ef12-113">分配到整个数组`Items`集合：</span><span class="sxs-lookup"><span data-stu-id="9ef12-113">Assign an entire array to the `Items` collection:</span></span>  
  
    ```vb  
    Dim ItemObject(9) As System.Object  
    Dim i As Integer  
       For i = 0 To 9  
       ItemObject(i) = "Item" & i  
    Next i  
    ListBox1.Items.AddRange(ItemObject)  
    ```  
  
    ```csharp  
    System.Object[] ItemObject = new System.Object[10];  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = "Item" + i;  
    }  
    listBox1.Items.AddRange(ItemObject);  
    ```  
  
    ```cpp  
    Array<System::Object^>^ ItemObject = gcnew Array<System::Object^>(10);  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = String::Concat("Item", i.ToString());  
    }  
    listBox1->Items->AddRange(ItemObject);  
    ```  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="9ef12-114">若要删除项</span><span class="sxs-lookup"><span data-stu-id="9ef12-114">To remove an item</span></span>  
  
1. <span data-ttu-id="9ef12-115">调用`Remove`或`RemoveAt`方法来删除项。</span><span class="sxs-lookup"><span data-stu-id="9ef12-115">Call the `Remove` or `RemoveAt` method to delete items.</span></span>  
  
     <span data-ttu-id="9ef12-116">`Remove` 有一个参数，指定要移除的项。`RemoveAt`</span><span class="sxs-lookup"><span data-stu-id="9ef12-116">`Remove` has one argument that specifies the item to remove.`RemoveAt`</span></span> <span data-ttu-id="9ef12-117">移除具有指定的索引号的项。</span><span class="sxs-lookup"><span data-stu-id="9ef12-117">removes the item with the specified index number.</span></span>  
  
    ```vb  
    ' To remove item with index 0:  
    ComboBox1.Items.RemoveAt(0)  
    ' To remove currently selected item:  
    ComboBox1.Items.Remove(ComboBox1.SelectedItem)  
    ' To remove "Tokyo" item:  
    ComboBox1.Items.Remove("Tokyo")  
    ```  
  
    ```csharp  
    // To remove item with index 0:  
    comboBox1.Items.RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1.Items.Remove(comboBox1.SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1.Items.Remove("Tokyo");  
    ```  
  
    ```cpp  
    // To remove item with index 0:  
    comboBox1->Items->RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1->Items->Remove(comboBox1->SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1->Items->Remove("Tokyo");  
    ```  
  
### <a name="to-remove-all-items"></a><span data-ttu-id="9ef12-118">若要删除的所有项</span><span class="sxs-lookup"><span data-stu-id="9ef12-118">To remove all items</span></span>  
  
1. <span data-ttu-id="9ef12-119">调用`Clear`方法从集合中移除所有项：</span><span class="sxs-lookup"><span data-stu-id="9ef12-119">Call the `Clear` method to remove all items from the collection:</span></span>  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9ef12-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ef12-120">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="9ef12-121">如何：排序的内容的 Windows 窗体 ComboBox、 ListBox 或 CheckedListBox 控件</span><span class="sxs-lookup"><span data-stu-id="9ef12-121">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="9ef12-122">何时使用 Windows 窗体 ComboBox 而非 ListBox</span><span class="sxs-lookup"><span data-stu-id="9ef12-122">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="9ef12-123">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="9ef12-123">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
