---
title: "Windows 窗体 DataGridView 控件中的默认功能"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d6b15085c301f074ef6fcf9e60a75299c4b245b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8e8f1-102">Windows 窗体 DataGridView 控件中的默认功能</span><span class="sxs-lookup"><span data-stu-id="8e8f1-102">Default Functionality in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8e8f1-103">Windows 窗体<xref:System.Windows.Forms.DataGridView>控件向用户提供大量的默认功能。</span><span class="sxs-lookup"><span data-stu-id="8e8f1-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control provides users with a significant amount of default functionality.</span></span>  
  
## <a name="default-functionality"></a><span data-ttu-id="8e8f1-104">默认功能</span><span class="sxs-lookup"><span data-stu-id="8e8f1-104">Default Functionality</span></span>  
 <span data-ttu-id="8e8f1-105">默认情况下，<xref:System.Windows.Forms.DataGridView>控件：</span><span class="sxs-lookup"><span data-stu-id="8e8f1-105">By default, a <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <span data-ttu-id="8e8f1-106">自动显示列标题和垂直滚动表时保持可见的行标题。</span><span class="sxs-lookup"><span data-stu-id="8e8f1-106">Automatically displays column headers and row headers that remain visible as the table scrolls vertically.</span></span>  
  
-   <span data-ttu-id="8e8f1-107">具有行标头，其中包含当前行的选择指示器。</span><span class="sxs-lookup"><span data-stu-id="8e8f1-107">Has a row header that contains a selection indicator for the current row.</span></span>  
  
-   <span data-ttu-id="8e8f1-108">已选择矩形中的第一个单元。</span><span class="sxs-lookup"><span data-stu-id="8e8f1-108">Has a selection rectangle in the first cell.</span></span>  
  
-   <span data-ttu-id="8e8f1-109">具有当用户双击列分隔线可以自动调整的列。</span><span class="sxs-lookup"><span data-stu-id="8e8f1-109">Has columns that can be automatically resized when the user double-clicks the column dividers.</span></span>  
  
-   <span data-ttu-id="8e8f1-110">自动支持在 Windows XP 和 Windows Server 2003 系列上的视觉样式时<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>从应用程序的调用方法`Main`方法。</span><span class="sxs-lookup"><span data-stu-id="8e8f1-110">Automatically supports visual styles on Windows XP and the Windows Server 2003 family when the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method is called from the application's `Main` method.</span></span>  
  
 <span data-ttu-id="8e8f1-111">此外，内容<xref:System.Windows.Forms.DataGridView>控件可以编辑默认情况下：</span><span class="sxs-lookup"><span data-stu-id="8e8f1-111">Additionally, the contents of a <xref:System.Windows.Forms.DataGridView> control can be edited by default:</span></span>  
  
-   <span data-ttu-id="8e8f1-112">如果用户双击或按下 F2 在单元格中，该控件将自动将单元格置于编辑模式，并更新的用户类型作为单元格的内容。</span><span class="sxs-lookup"><span data-stu-id="8e8f1-112">If the user double-clicks or presses F2 in a cell, the control automatically puts the cell into edit mode and updates the contents of the cell as the user types.</span></span>  
  
-   <span data-ttu-id="8e8f1-113">如果用户滚动到网格的结尾时，用户将看到用于添加新记录行是否存在。</span><span class="sxs-lookup"><span data-stu-id="8e8f1-113">If the user scrolls to the end of the grid, the user will see that a row for adding new records is present.</span></span> <span data-ttu-id="8e8f1-114">当用户单击此行时，将新行添加到<xref:System.Windows.Forms.DataGridView>控件，使用默认值。</span><span class="sxs-lookup"><span data-stu-id="8e8f1-114">When the user clicks this row, a new row is added to the <xref:System.Windows.Forms.DataGridView> control, with default values.</span></span> <span data-ttu-id="8e8f1-115">当用户按 ESC 时，此新行将会消失。</span><span class="sxs-lookup"><span data-stu-id="8e8f1-115">When the user presses ESC, this new row disappears.</span></span>  
  
-   <span data-ttu-id="8e8f1-116">如果用户单击行标题，则选择整个行。</span><span class="sxs-lookup"><span data-stu-id="8e8f1-116">If the user clicks a row header, the whole row is selected.</span></span>  
  
 <span data-ttu-id="8e8f1-117">当绑定<xref:System.Windows.Forms.DataGridView>控件添加到数据源通过设置其<xref:System.Windows.Forms.DataGridView.DataSource%2A>属性、 控件：</span><span class="sxs-lookup"><span data-stu-id="8e8f1-117">When you bind a <xref:System.Windows.Forms.DataGridView> control to a data source by setting its <xref:System.Windows.Forms.DataGridView.DataSource%2A> property, the control:</span></span>  
  
-   <span data-ttu-id="8e8f1-118">自动使用数据源的列的名称作为列标题文本。</span><span class="sxs-lookup"><span data-stu-id="8e8f1-118">Automatically uses the names of the data source's columns as the column header text.</span></span>  
  
-   <span data-ttu-id="8e8f1-119">使用数据源的内容填充。</span><span class="sxs-lookup"><span data-stu-id="8e8f1-119">Is populated with the contents of the data source.</span></span> <span data-ttu-id="8e8f1-120"><xref:System.Windows.Forms.DataGridView>为数据源中的每一列自动创建列。</span><span class="sxs-lookup"><span data-stu-id="8e8f1-120"><xref:System.Windows.Forms.DataGridView> columns are automatically created for each column in the data source.</span></span>  
  
-   <span data-ttu-id="8e8f1-121">表中创建每个可见行的行。</span><span class="sxs-lookup"><span data-stu-id="8e8f1-121">Creates a row for each visible row in the table.</span></span>  
  
-   <span data-ttu-id="8e8f1-122">自动对基于基础数据，当用户单击列标题行进行排序。</span><span class="sxs-lookup"><span data-stu-id="8e8f1-122">Automatically sorts the rows based on the underlying data when the user clicks a column header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e8f1-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e8f1-123">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="8e8f1-124">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="8e8f1-124">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
