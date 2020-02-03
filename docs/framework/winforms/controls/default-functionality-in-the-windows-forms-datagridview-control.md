---
title: DataGridView 控件中的默认功能
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: b695883ac7ec3fb0c459adb66214b0eceab3a128
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746131"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="35e07-102">Windows 窗体 DataGridView 控件中的默认功能</span><span class="sxs-lookup"><span data-stu-id="35e07-102">Default Functionality in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="35e07-103">Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件可为用户提供大量的默认功能。</span><span class="sxs-lookup"><span data-stu-id="35e07-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control provides users with a significant amount of default functionality.</span></span>  
  
## <a name="default-functionality"></a><span data-ttu-id="35e07-104">默认功能</span><span class="sxs-lookup"><span data-stu-id="35e07-104">Default Functionality</span></span>  
 <span data-ttu-id="35e07-105">默认情况下，<xref:System.Windows.Forms.DataGridView> 控件：</span><span class="sxs-lookup"><span data-stu-id="35e07-105">By default, a <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
- <span data-ttu-id="35e07-106">当表垂直滚动时，自动显示列标题和行标题保持可见。</span><span class="sxs-lookup"><span data-stu-id="35e07-106">Automatically displays column headers and row headers that remain visible as the table scrolls vertically.</span></span>  
  
- <span data-ttu-id="35e07-107">有一个行标题，其中包含当前行的选择指示器。</span><span class="sxs-lookup"><span data-stu-id="35e07-107">Has a row header that contains a selection indicator for the current row.</span></span>  
  
- <span data-ttu-id="35e07-108">在第一个单元格中有一个选择矩形。</span><span class="sxs-lookup"><span data-stu-id="35e07-108">Has a selection rectangle in the first cell.</span></span>  
  
- <span data-ttu-id="35e07-109">具有当用户双击列分隔符时可自动调整大小的列。</span><span class="sxs-lookup"><span data-stu-id="35e07-109">Has columns that can be automatically resized when the user double-clicks the column dividers.</span></span>  
  
- <span data-ttu-id="35e07-110">从应用程序的 `Main` 方法调用 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 方法时，会自动支持 Windows XP 和 Windows Server 2003 家族上的视觉样式。</span><span class="sxs-lookup"><span data-stu-id="35e07-110">Automatically supports visual styles on Windows XP and the Windows Server 2003 family when the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method is called from the application's `Main` method.</span></span>  
  
 <span data-ttu-id="35e07-111">此外，默认情况下可以编辑 <xref:System.Windows.Forms.DataGridView> 控件的内容：</span><span class="sxs-lookup"><span data-stu-id="35e07-111">Additionally, the contents of a <xref:System.Windows.Forms.DataGridView> control can be edited by default:</span></span>  
  
- <span data-ttu-id="35e07-112">如果用户在单元格中双击或按 F2，则控件会自动将该单元格置于编辑模式，并在用户键入内容时更新该单元格的内容。</span><span class="sxs-lookup"><span data-stu-id="35e07-112">If the user double-clicks or presses F2 in a cell, the control automatically puts the cell into edit mode and updates the contents of the cell as the user types.</span></span>  
  
- <span data-ttu-id="35e07-113">如果用户滚动到网格的末尾，用户将看到用于添加新记录的行。</span><span class="sxs-lookup"><span data-stu-id="35e07-113">If the user scrolls to the end of the grid, the user will see that a row for adding new records is present.</span></span> <span data-ttu-id="35e07-114">当用户单击此行时，将使用默认值将新行添加到 <xref:System.Windows.Forms.DataGridView> 控件中。</span><span class="sxs-lookup"><span data-stu-id="35e07-114">When the user clicks this row, a new row is added to the <xref:System.Windows.Forms.DataGridView> control, with default values.</span></span> <span data-ttu-id="35e07-115">当用户按 ESC 键时，此新行将消失。</span><span class="sxs-lookup"><span data-stu-id="35e07-115">When the user presses ESC, this new row disappears.</span></span>  
  
- <span data-ttu-id="35e07-116">如果用户单击行标题，则会选择整个行。</span><span class="sxs-lookup"><span data-stu-id="35e07-116">If the user clicks a row header, the whole row is selected.</span></span>  
  
 <span data-ttu-id="35e07-117">通过设置 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 属性将 <xref:System.Windows.Forms.DataGridView> 控件绑定到数据源时，控件：</span><span class="sxs-lookup"><span data-stu-id="35e07-117">When you bind a <xref:System.Windows.Forms.DataGridView> control to a data source by setting its <xref:System.Windows.Forms.DataGridView.DataSource%2A> property, the control:</span></span>  
  
- <span data-ttu-id="35e07-118">自动使用数据源的列的名称作为列标题文本。</span><span class="sxs-lookup"><span data-stu-id="35e07-118">Automatically uses the names of the data source's columns as the column header text.</span></span>  
  
- <span data-ttu-id="35e07-119">用数据源的内容进行填充。</span><span class="sxs-lookup"><span data-stu-id="35e07-119">Is populated with the contents of the data source.</span></span> <span data-ttu-id="35e07-120">将为数据源中的每个列自动创建 <xref:System.Windows.Forms.DataGridView> 列。</span><span class="sxs-lookup"><span data-stu-id="35e07-120"><xref:System.Windows.Forms.DataGridView> columns are automatically created for each column in the data source.</span></span>  
  
- <span data-ttu-id="35e07-121">为表中的每个可见行创建一行。</span><span class="sxs-lookup"><span data-stu-id="35e07-121">Creates a row for each visible row in the table.</span></span>  
  
- <span data-ttu-id="35e07-122">用户单击列标题时，将基于基础数据自动对行进行排序。</span><span class="sxs-lookup"><span data-stu-id="35e07-122">Automatically sorts the rows based on the underlying data when the user clicks a column header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35e07-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35e07-123">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="35e07-124">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="35e07-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
