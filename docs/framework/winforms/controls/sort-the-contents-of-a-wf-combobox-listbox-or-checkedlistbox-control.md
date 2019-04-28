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
ms.openlocfilehash: bd26d396c238bfc53858320b8f4487df84b3436a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902988"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="9743a-102">如何：对 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件的内容排序</span><span class="sxs-lookup"><span data-stu-id="9743a-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="9743a-103">Windows 窗体控件不排序操作时它们是数据绑定。</span><span class="sxs-lookup"><span data-stu-id="9743a-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="9743a-104">若要显示已排序的数据，请使用支持排序的数据源，然后对其进行排序的数据源。</span><span class="sxs-lookup"><span data-stu-id="9743a-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="9743a-105">支持排序的数据源是数据的视图，数据查看管理器，并已排序数组。</span><span class="sxs-lookup"><span data-stu-id="9743a-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="9743a-106">如果控件不是数据绑定，您可以对其进行排序。</span><span class="sxs-lookup"><span data-stu-id="9743a-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="9743a-107">若要对列表进行排序</span><span class="sxs-lookup"><span data-stu-id="9743a-107">To sort the list</span></span>  
  
1. <span data-ttu-id="9743a-108">将 `Sorted` 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="9743a-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="9743a-109">此设置按排序顺序重新定位所有现有列表项。</span><span class="sxs-lookup"><span data-stu-id="9743a-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9743a-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="9743a-110">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="9743a-111">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="9743a-111">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="9743a-112">如何：添加和删除项从 Windows 窗体 ComboBox、 ListBox 或 CheckedListBox 控件</span><span class="sxs-lookup"><span data-stu-id="9743a-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="9743a-113">何时使用 Windows 窗体 ComboBox 而非 ListBox</span><span class="sxs-lookup"><span data-stu-id="9743a-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="9743a-114">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="9743a-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
