---
title: 如何：向 Windows 窗体 ListView 控件中添加列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: 59137deeb645fd50a7884c196e55317f776d9cf1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103325"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="dbca0-102">如何：向 Windows 窗体 ListView 控件中添加列</span><span class="sxs-lookup"><span data-stu-id="dbca0-102">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="dbca0-103">在详细信息视图中，<xref:System.Windows.Forms.ListView>控件可以显示每个列表项的多个列。</span><span class="sxs-lookup"><span data-stu-id="dbca0-103">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="dbca0-104">列可用于向用户显示多种类型的每个列表项的相关信息。</span><span class="sxs-lookup"><span data-stu-id="dbca0-104">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="dbca0-105">例如，文件的列表可以显示文件名、 文件类型、 大小和文件的上次修改的日期。</span><span class="sxs-lookup"><span data-stu-id="dbca0-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="dbca0-106">有关在创建后填充列的信息，请参阅[如何：在具有 Windows 的列中显示子项窗体 ListView 控件](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="dbca0-106">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="dbca0-107">若要以编程方式添加列</span><span class="sxs-lookup"><span data-stu-id="dbca0-107">To add columns programmatically</span></span>  
  
1.  <span data-ttu-id="dbca0-108">设置控件的<xref:System.Windows.Forms.ListView.View%2A>属性设置为<xref:System.Windows.Forms.View.Details>。</span><span class="sxs-lookup"><span data-stu-id="dbca0-108">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2.  <span data-ttu-id="dbca0-109">使用<xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A>方法的列表视图<xref:System.Windows.Forms.ListView.Columns%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="dbca0-109">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="dbca0-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="dbca0-110">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="dbca0-111">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="dbca0-111">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="dbca0-112">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="dbca0-112">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
