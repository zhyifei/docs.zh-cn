---
title: Windows 窗体 DataGridView 控件中的默认功能
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: 0c0d24111a2fdf856ff1f4ce154ec85afbbd61ee
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719658"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="1e6ed-102">Windows 窗体 DataGridView 控件中的默认功能</span><span class="sxs-lookup"><span data-stu-id="1e6ed-102">Default Functionality in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1e6ed-103">Windows 窗体<xref:System.Windows.Forms.DataGridView>控件为用户提供了大量的默认功能。</span><span class="sxs-lookup"><span data-stu-id="1e6ed-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control provides users with a significant amount of default functionality.</span></span>  
  
## <a name="default-functionality"></a><span data-ttu-id="1e6ed-104">默认功能</span><span class="sxs-lookup"><span data-stu-id="1e6ed-104">Default Functionality</span></span>  
 <span data-ttu-id="1e6ed-105">默认情况下，<xref:System.Windows.Forms.DataGridView>控件：</span><span class="sxs-lookup"><span data-stu-id="1e6ed-105">By default, a <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <span data-ttu-id="1e6ed-106">会自动显示列标题和行标题的垂直滚动表时保持可见。</span><span class="sxs-lookup"><span data-stu-id="1e6ed-106">Automatically displays column headers and row headers that remain visible as the table scrolls vertically.</span></span>  
  
-   <span data-ttu-id="1e6ed-107">具有行标题，其中包含当前行的选择指示器。</span><span class="sxs-lookup"><span data-stu-id="1e6ed-107">Has a row header that contains a selection indicator for the current row.</span></span>  
  
-   <span data-ttu-id="1e6ed-108">第一个单元格中具有选择矩形。</span><span class="sxs-lookup"><span data-stu-id="1e6ed-108">Has a selection rectangle in the first cell.</span></span>  
  
-   <span data-ttu-id="1e6ed-109">包含可以自动调整大小以当用户双击的列分隔条的列。</span><span class="sxs-lookup"><span data-stu-id="1e6ed-109">Has columns that can be automatically resized when the user double-clicks the column dividers.</span></span>  
  
-   <span data-ttu-id="1e6ed-110">自动支持在 Windows XP 和 Windows Server 2003 系列上的视觉样式时<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>方法从应用程序的调用`Main`方法。</span><span class="sxs-lookup"><span data-stu-id="1e6ed-110">Automatically supports visual styles on Windows XP and the Windows Server 2003 family when the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method is called from the application's `Main` method.</span></span>  
  
 <span data-ttu-id="1e6ed-111">此外的内容<xref:System.Windows.Forms.DataGridView>默认情况下，可以编辑控件：</span><span class="sxs-lookup"><span data-stu-id="1e6ed-111">Additionally, the contents of a <xref:System.Windows.Forms.DataGridView> control can be edited by default:</span></span>  
  
-   <span data-ttu-id="1e6ed-112">如果用户双击或按 F2 单元中的，该控件将自动使单元格进入编辑模式，并更新的单元格的内容与用户类型。</span><span class="sxs-lookup"><span data-stu-id="1e6ed-112">If the user double-clicks or presses F2 in a cell, the control automatically puts the cell into edit mode and updates the contents of the cell as the user types.</span></span>  
  
-   <span data-ttu-id="1e6ed-113">如果用户滚动到网格的末尾时，用户将看到用于添加新记录的行是否存在。</span><span class="sxs-lookup"><span data-stu-id="1e6ed-113">If the user scrolls to the end of the grid, the user will see that a row for adding new records is present.</span></span> <span data-ttu-id="1e6ed-114">当用户单击此行时，新行添加到<xref:System.Windows.Forms.DataGridView>控件，具有默认值。</span><span class="sxs-lookup"><span data-stu-id="1e6ed-114">When the user clicks this row, a new row is added to the <xref:System.Windows.Forms.DataGridView> control, with default values.</span></span> <span data-ttu-id="1e6ed-115">当用户按 esc 键时，此新行将消失。</span><span class="sxs-lookup"><span data-stu-id="1e6ed-115">When the user presses ESC, this new row disappears.</span></span>  
  
-   <span data-ttu-id="1e6ed-116">如果用户单击行标题，则选择整个行。</span><span class="sxs-lookup"><span data-stu-id="1e6ed-116">If the user clicks a row header, the whole row is selected.</span></span>  
  
 <span data-ttu-id="1e6ed-117">当绑定<xref:System.Windows.Forms.DataGridView>控件与数据源通过设置其<xref:System.Windows.Forms.DataGridView.DataSource%2A>属性、 控件：</span><span class="sxs-lookup"><span data-stu-id="1e6ed-117">When you bind a <xref:System.Windows.Forms.DataGridView> control to a data source by setting its <xref:System.Windows.Forms.DataGridView.DataSource%2A> property, the control:</span></span>  
  
-   <span data-ttu-id="1e6ed-118">自动使用的数据源的列的名称作为列标题文本。</span><span class="sxs-lookup"><span data-stu-id="1e6ed-118">Automatically uses the names of the data source's columns as the column header text.</span></span>  
  
-   <span data-ttu-id="1e6ed-119">使用数据源的内容填充。</span><span class="sxs-lookup"><span data-stu-id="1e6ed-119">Is populated with the contents of the data source.</span></span> <span data-ttu-id="1e6ed-120"><xref:System.Windows.Forms.DataGridView> 对于每个列的数据源中自动创建列。</span><span class="sxs-lookup"><span data-stu-id="1e6ed-120"><xref:System.Windows.Forms.DataGridView> columns are automatically created for each column in the data source.</span></span>  
  
-   <span data-ttu-id="1e6ed-121">在表中创建每个可见行的行。</span><span class="sxs-lookup"><span data-stu-id="1e6ed-121">Creates a row for each visible row in the table.</span></span>  
  
-   <span data-ttu-id="1e6ed-122">自动对基于对基础数据，当用户单击列标题的行进行排序。</span><span class="sxs-lookup"><span data-stu-id="1e6ed-122">Automatically sorts the rows based on the underlying data when the user clicks a column header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e6ed-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e6ed-123">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="1e6ed-124">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="1e6ed-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
