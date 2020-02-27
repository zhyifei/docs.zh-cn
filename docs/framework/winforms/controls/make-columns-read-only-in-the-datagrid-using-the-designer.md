---
title: 使用设计器使 DataGridView 控件中的列成为只读
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 2dd3f8bfcad39ca3d530c79a6e6a8170585f7adf
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627950"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="0189f-102">如何：使用设计器使 Windows 窗体 DataGridView 控件中的列成为只读</span><span class="sxs-lookup"><span data-stu-id="0189f-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="0189f-103">默认情况下，用户可以修改 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件中显示的文本和数字数据。</span><span class="sxs-lookup"><span data-stu-id="0189f-103">By default, users can modify text and numerical data displayed in the Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0189f-104">如果要显示不用于修改的数据，则必须将包含数据的列设置为只读。</span><span class="sxs-lookup"><span data-stu-id="0189f-104">If you want to display data that is not meant for modification, you must make the columns that contain the data read-only.</span></span> <span data-ttu-id="0189f-105">有关如何使控件完全成为只读控件的信息，请参阅[如何：使用设计器防止 Windows 窗体 DataGridView 控件中添加和删除行](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="0189f-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span></span>

 <span data-ttu-id="0189f-106">下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.DataGridView> 控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="0189f-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0189f-107">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="0189f-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-make-a-column-read-only-by-using-the-designer"></a><span data-ttu-id="0189f-108">使用设计器使列成为只读的</span><span class="sxs-lookup"><span data-stu-id="0189f-108">To make a column read-only by using the designer</span></span>

1. <span data-ttu-id="0189f-109">单击 <xref:System.Windows.Forms.DataGridView> 控件右上角的设计器操作标志符号（![小号黑色箭头](./media/designer-actions-glyph.gif)），然后选择 "**编辑列**"。</span><span class="sxs-lookup"><span data-stu-id="0189f-109">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="0189f-110">从 "**选定的列**" 列表中选择一列。</span><span class="sxs-lookup"><span data-stu-id="0189f-110">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="0189f-111">在 "**列属性**" 网格中，将 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="0189f-111">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0189f-112">您还可以通过在 "**添加列**" 对话框中选中 "**只读**" 复选框来添加列，以使其成为只读列。</span><span class="sxs-lookup"><span data-stu-id="0189f-112">You can also make a column read-only when you add it by selecting the **Read Only** check box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="0189f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0189f-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0189f-114">如何：使用设计器在 Windows 窗体 DataGridView 控件中添加和删除列</span><span class="sxs-lookup"><span data-stu-id="0189f-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="0189f-115">如何：使用设计器防止在 Windows 窗体 DataGridView 控件中添加和删除行</span><span class="sxs-lookup"><span data-stu-id="0189f-115">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="0189f-116">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="0189f-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="0189f-117">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="0189f-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
