---
title: 如何：对 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件的内容排序
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: 8b8f9c7ad0ad7d3bbb7f3eeffd44e555207b82c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535641"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="28602-102">如何：对 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件的内容排序</span><span class="sxs-lookup"><span data-stu-id="28602-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="28602-103">在数据绑定时，Windows 窗体控件不进行排序。</span><span class="sxs-lookup"><span data-stu-id="28602-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="28602-104">若要显示已排序的数据，使用支持排序的数据源，然后对它进行排序的数据源。</span><span class="sxs-lookup"><span data-stu-id="28602-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="28602-105">支持排序的数据源是： 数据视图，数据查看管理器，并已排序数组。</span><span class="sxs-lookup"><span data-stu-id="28602-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="28602-106">如果控件不是数据绑定，可以对它进行排序。</span><span class="sxs-lookup"><span data-stu-id="28602-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="28602-107">若要对列表进行排序</span><span class="sxs-lookup"><span data-stu-id="28602-107">To sort the list</span></span>  
  
1.  <span data-ttu-id="28602-108">将 `Sorted` 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="28602-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="28602-109">此设置将按排序顺序重新定位所有现有列表项。</span><span class="sxs-lookup"><span data-stu-id="28602-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28602-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="28602-110">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 <xref:System.Windows.Forms.CheckedListBox>  
 [<span data-ttu-id="28602-111">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="28602-111">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="28602-112">如何：在 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件中添加和删除项</span><span class="sxs-lookup"><span data-stu-id="28602-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [<span data-ttu-id="28602-113">何时使用 Windows 窗体 ComboBox 而非 ListBox</span><span class="sxs-lookup"><span data-stu-id="28602-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [<span data-ttu-id="28602-114">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="28602-114">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
