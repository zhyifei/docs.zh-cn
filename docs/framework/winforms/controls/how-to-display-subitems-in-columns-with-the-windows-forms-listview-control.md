---
title: "如何：使用 Windows 窗体 ListView 控件在列中显示子项"
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
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be1b055c8ea0e7a7c6466033735431a17ecc32f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a><span data-ttu-id="a63f9-102">如何：使用 Windows 窗体 ListView 控件在列中显示子项</span><span class="sxs-lookup"><span data-stu-id="a63f9-102">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>
<span data-ttu-id="a63f9-103">Windows 窗体<xref:System.Windows.Forms.ListView>控件可以显示的附加文本或子项的详细信息视图中每个项。</span><span class="sxs-lookup"><span data-stu-id="a63f9-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display additional text, or subitems, for each item in the Details view.</span></span> <span data-ttu-id="a63f9-104">第一列显示项文本，如雇员编号。</span><span class="sxs-lookup"><span data-stu-id="a63f9-104">The first column displays the item text, for example an employee number.</span></span> <span data-ttu-id="a63f9-105">第二、 第三个和后续列显示第一、 第二，并随后的关联子项。</span><span class="sxs-lookup"><span data-stu-id="a63f9-105">The second, third, and subsequent columns display the first, second, and subsequent associated subitems.</span></span>  
  
### <a name="to-add-subitems-to-a-list-item"></a><span data-ttu-id="a63f9-106">要添加到列表项的子项</span><span class="sxs-lookup"><span data-stu-id="a63f9-106">To add subitems to a list item</span></span>  
  
1.  <span data-ttu-id="a63f9-107">添加所需的任何列。</span><span class="sxs-lookup"><span data-stu-id="a63f9-107">Add any columns needed.</span></span> <span data-ttu-id="a63f9-108">因为第一列将显示项的<xref:System.Windows.Forms.ListView.Text%2A>属性，你需要一列不是有子项。</span><span class="sxs-lookup"><span data-stu-id="a63f9-108">Because the first column will display the item's <xref:System.Windows.Forms.ListView.Text%2A> property, you need one more column than there are subitems.</span></span> <span data-ttu-id="a63f9-109">添加列的详细信息，请参阅[如何： 向 Windows 窗体 ListView 控件添加列](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="a63f9-109">For more information on adding columns, see [How to: Add Columns to the Windows Forms ListView Control](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).</span></span>  
  
2.  <span data-ttu-id="a63f9-110">调用<xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A>方法返回的集合<xref:System.Windows.Forms.ListViewItem.SubItems%2A>项属性。</span><span class="sxs-lookup"><span data-stu-id="a63f9-110">Call the <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.ListViewItem.SubItems%2A> property of an item.</span></span> <span data-ttu-id="a63f9-111">下面的代码示例设置的雇员姓名和部门的列表项。</span><span class="sxs-lookup"><span data-stu-id="a63f9-111">The code example below sets the employee name and department for a list item.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="a63f9-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a63f9-112">See Also</span></span>  
 [<span data-ttu-id="a63f9-113">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="a63f9-113">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="a63f9-114">如何：使用 Windows 窗体 ListView 控件添加和删除项</span><span class="sxs-lookup"><span data-stu-id="a63f9-114">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="a63f9-115">如何：向 Windows 窗体 ListView 控件添加列</span><span class="sxs-lookup"><span data-stu-id="a63f9-115">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="a63f9-116">如何：显示 Windows 窗体 ListView 控件的图标</span><span class="sxs-lookup"><span data-stu-id="a63f9-116">How to: Display Icons for the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="a63f9-117">如何：向 TreeView 或 ListView 控件（Windows 窗体）添加自定义信息</span><span class="sxs-lookup"><span data-stu-id="a63f9-117">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
