---
title: 使用设计器冻结 DataGridView 控件中的列
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
ms.openlocfilehash: af8e07d7b1b0524e33688fd9d879818aa13be041
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745677"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="a4206-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 고정</span><span class="sxs-lookup"><span data-stu-id="a4206-102">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="a4206-103">사용자가 Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시된 데이터를 볼 때 단일 열이나 열 집합을 자주 참조해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4206-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="a4206-104">例如，当你显示包含多个列的客户信息表时，你可以在任何时候显示客户名称，同时允许其他列在可见区域外滚动。</span><span class="sxs-lookup"><span data-stu-id="a4206-104">For example, when you display a table of customer information that contains many columns, it is useful for you to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>

 <span data-ttu-id="a4206-105">이 동작을 얻기 위해 컨트롤에서 열을 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4206-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="a4206-106">열을 고정하는 경우 왼쪽(또는 오른쪽에서 왼쪽 언어 스크립트의 경우 오른쪽)에 있는 모든 열도 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4206-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="a4206-107">다른 모든 열을 스크롤할 수 있는 동안 고정된 열은 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4206-107">Frozen columns remain in place while all other columns can scroll.</span></span> <span data-ttu-id="a4206-108">열 다시 정렬을 사용하는 경우 고정된 열은 고정되지 않은 열과 별개인 그룹으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4206-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="a4206-109">사용자는 각 그룹에서 열의 위치를 변경할 수 있지만 그룹 간에 열을 이동할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4206-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>

 <span data-ttu-id="a4206-110">下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.DataGridView> 控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="a4206-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a4206-111">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="a4206-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-freeze-a-column-using-the-designer"></a><span data-ttu-id="a4206-112">使用设计器冻结列</span><span class="sxs-lookup"><span data-stu-id="a4206-112">To freeze a column using the designer</span></span>

1. <span data-ttu-id="a4206-113">单击 <xref:System.Windows.Forms.DataGridView> 控件右上角的智能标记标志符号（![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")），然后选择 "**编辑列**"。</span><span class="sxs-lookup"><span data-stu-id="a4206-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="a4206-114">从 "**选定的列**" 列表中选择一列。</span><span class="sxs-lookup"><span data-stu-id="a4206-114">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="a4206-115">在 "**列属性**" 网格中，将 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="a4206-115">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a4206-116">您还可以通过在 "**添加列**" 对话框中选择**冻结**框来添加该列。</span><span class="sxs-lookup"><span data-stu-id="a4206-116">You can also freeze a column when adding it by selecting the **Frozen** box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4206-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4206-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a4206-118">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="a4206-118">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="a4206-119">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용</span><span class="sxs-lookup"><span data-stu-id="a4206-119">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](enable-column-reordering-in-the-datagrid-using-the-designer.md)
- <span data-ttu-id="a4206-120">[如何：在 Windows 窗体中为全球化显示从右到左的文本](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a4206-120">[How to: Display Right-to-Left Text in Windows Forms for Globalization](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))</span></span>
- [<span data-ttu-id="a4206-121">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="a4206-121">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="a4206-122">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="a4206-122">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
