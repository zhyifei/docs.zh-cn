---
title: "如何：对 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件的内容排序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0e43a23d632b397889721373471a8fa165052d7f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="06236-102">如何：对 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件的内容排序</span><span class="sxs-lookup"><span data-stu-id="06236-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="06236-103">在数据绑定时，Windows 窗体控件不进行排序。</span><span class="sxs-lookup"><span data-stu-id="06236-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="06236-104">若要显示已排序的数据，使用支持排序的数据源，然后对它进行排序的数据源。</span><span class="sxs-lookup"><span data-stu-id="06236-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="06236-105">支持排序的数据源是： 数据视图，数据查看管理器，并已排序数组。</span><span class="sxs-lookup"><span data-stu-id="06236-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="06236-106">如果控件不是数据绑定，可以对它进行排序。</span><span class="sxs-lookup"><span data-stu-id="06236-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="06236-107">若要对列表进行排序</span><span class="sxs-lookup"><span data-stu-id="06236-107">To sort the list</span></span>  
  
1.  <span data-ttu-id="06236-108">将 `Sorted` 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="06236-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="06236-109">此设置将按排序顺序重新定位所有现有列表项。</span><span class="sxs-lookup"><span data-stu-id="06236-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06236-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06236-110">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 <xref:System.Windows.Forms.CheckedListBox>  
 [<span data-ttu-id="06236-111">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="06236-111">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="06236-112">如何：在 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件中添加和删除项</span><span class="sxs-lookup"><span data-stu-id="06236-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [<span data-ttu-id="06236-113">何时使用 Windows 窗体 ComboBox 而非 ListBox</span><span class="sxs-lookup"><span data-stu-id="06236-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [<span data-ttu-id="06236-114">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="06236-114">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
