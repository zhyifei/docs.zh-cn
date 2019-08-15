---
title: 如何：使用设计器冻结 Windows 窗体 DataGridView 控件中的列
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
ms.openlocfilehash: d38c8d73bc70e7e521b476ca78c8f102d003c538
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040337"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="1c1de-102">如何：使用设计器冻结 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="1c1de-102">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="1c1de-103">用户查看 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件中显示的数据时，有时需要频繁地引用单个列或列集。</span><span class="sxs-lookup"><span data-stu-id="1c1de-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="1c1de-104">例如, 当你显示包含多个列的客户信息表时, 你可以在任何时候显示客户名称, 同时允许其他列在可见区域外滚动。</span><span class="sxs-lookup"><span data-stu-id="1c1de-104">For example, when you display a table of customer information that contains many columns, it is useful for you to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>

 <span data-ttu-id="1c1de-105">若要实现此行为，可冻结控件中的列。</span><span class="sxs-lookup"><span data-stu-id="1c1de-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="1c1de-106">冻结列时，也将冻结其左侧（在从右到左的语言脚本中为右侧）的所有列。</span><span class="sxs-lookup"><span data-stu-id="1c1de-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="1c1de-107">冻结的列保持不变，而所有其他列可以滚动。</span><span class="sxs-lookup"><span data-stu-id="1c1de-107">Frozen columns remain in place while all other columns can scroll.</span></span> <span data-ttu-id="1c1de-108">如果启用了列重新排序，冻结的列被视为一组不同于未冻结的列。</span><span class="sxs-lookup"><span data-stu-id="1c1de-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="1c1de-109">用户可重新定位任一组中的列，但不能将列从一个组移到另一组。</span><span class="sxs-lookup"><span data-stu-id="1c1de-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>

 <span data-ttu-id="1c1de-110">下面的过程需要一个**Windows 应用程序**项目, 该项目具有<xref:System.Windows.Forms.DataGridView>包含控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="1c1de-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="1c1de-111">有关设置此类项目的信息, 请参阅[如何:创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)以及[如何:将控件添加到](how-to-add-controls-to-windows-forms.md)Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="1c1de-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-freeze-a-column-using-the-designer"></a><span data-ttu-id="1c1de-112">使用设计器冻结列</span><span class="sxs-lookup"><span data-stu-id="1c1de-112">To freeze a column using the designer</span></span>

1. <span data-ttu-id="1c1de-113">单击<xref:System.Windows.Forms.DataGridView>控件右上角的智能标记标志符号 (![智能标记字形](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), 然后选择 "**编辑列**"。</span><span class="sxs-lookup"><span data-stu-id="1c1de-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="1c1de-114">从 "**选定的列**" 列表中选择一列。</span><span class="sxs-lookup"><span data-stu-id="1c1de-114">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="1c1de-115">在 "**列属性**" 网格中, <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A>将属性`true`设置为。</span><span class="sxs-lookup"><span data-stu-id="1c1de-115">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property to `true`.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="1c1de-116">您还可以通过在 "**添加列**" 对话框中选择**冻结**框来添加该列。</span><span class="sxs-lookup"><span data-stu-id="1c1de-116">You can also freeze a column when adding it by selecting the **Frozen** box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c1de-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c1de-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1c1de-118">如何：使用设计器在 Windows 窗体 DataGridView 控件中添加和移除列</span><span class="sxs-lookup"><span data-stu-id="1c1de-118">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="1c1de-119">如何：使用设计器在 Windows 窗体 DataGridView 控件中启用列重新排序</span><span class="sxs-lookup"><span data-stu-id="1c1de-119">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](enable-column-reordering-in-the-datagrid-using-the-designer.md)
- <span data-ttu-id="1c1de-120">[如何：在 Windows 窗体中为全球化显示从右到左的文本](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1c1de-120">[How to: Display Right-to-Left Text in Windows Forms for Globalization](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))</span></span>
- [<span data-ttu-id="1c1de-121">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="1c1de-121">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="1c1de-122">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="1c1de-122">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
