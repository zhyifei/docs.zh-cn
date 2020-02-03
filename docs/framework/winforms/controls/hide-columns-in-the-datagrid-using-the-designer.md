---
title: 使用设计器在 DataGridView 控件中隐藏列
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: 3c9a6bdeacbeb5929488e6af0054403db73c4239
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738654"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="d7ef6-102">如何：使用设计器隐藏 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="d7ef6-102">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="d7ef6-103">有时，你会想仅显示在 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件中可用的某些列。</span><span class="sxs-lookup"><span data-stu-id="d7ef6-103">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d7ef6-104">例如，你可能希望向具有管理凭据的用户显示员工薪金列，同时将其与其他用户隐藏。</span><span class="sxs-lookup"><span data-stu-id="d7ef6-104">For example, you may want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="d7ef6-105">或者，您可能想要将该控件绑定到包含多个列的数据源，其中只包含您要显示的部分列。</span><span class="sxs-lookup"><span data-stu-id="d7ef6-105">Alternately, you may want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="d7ef6-106">在这种情况下，通常会删除不想要显示的列，而不是隐藏它们。</span><span class="sxs-lookup"><span data-stu-id="d7ef6-106">In this case, you will typically remove the columns you are not interested in displaying rather than hiding them.</span></span> <span data-ttu-id="d7ef6-107">有关详细信息，请参阅[如何：使用设计器在 Windows 窗体 DataGridView 控件中添加和删除列](add-and-remove-columns-in-the-datagrid-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="d7ef6-107">For more information, see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>

 <span data-ttu-id="d7ef6-108">下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.DataGridView> 控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="d7ef6-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d7ef6-109">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="d7ef6-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-hide-a-column-using-the-designer"></a><span data-ttu-id="d7ef6-110">使用设计器隐藏列</span><span class="sxs-lookup"><span data-stu-id="d7ef6-110">To hide a column using the designer</span></span>

1. <span data-ttu-id="d7ef6-111">单击 <xref:System.Windows.Forms.DataGridView> 控件右上角的智能标记标志符号（![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")），然后选择 "**编辑列**"。</span><span class="sxs-lookup"><span data-stu-id="d7ef6-111">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="d7ef6-112">从 "**选定的列**" 列表中选择一列。</span><span class="sxs-lookup"><span data-stu-id="d7ef6-112">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="d7ef6-113">在 "**列属性**" 网格中，将 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> 属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="d7ef6-113">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property to `false`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d7ef6-114">还可以通过清除 "**添加列**" 对话框中的 "**可见**" 复选框来添加列。</span><span class="sxs-lookup"><span data-stu-id="d7ef6-114">You can also hide a column when adding it by clearing the **Visible** check box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7ef6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7ef6-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d7ef6-116">如何：使用设计器在 Windows 窗体 DataGridView 控件中添加和删除列</span><span class="sxs-lookup"><span data-stu-id="d7ef6-116">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="d7ef6-117">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="d7ef6-117">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="d7ef6-118">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="d7ef6-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
