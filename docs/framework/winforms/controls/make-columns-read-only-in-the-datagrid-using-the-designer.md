---
title: 使用设计器使 DataGridView 控件中的列成为只读
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 51d9488ef83f7d2c1c01c9ffd756edf8944d738d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744974"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="91b8b-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정</span><span class="sxs-lookup"><span data-stu-id="91b8b-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="91b8b-103">默认情况下，用户可以修改 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件中显示的文本和数字数据。</span><span class="sxs-lookup"><span data-stu-id="91b8b-103">By default, users can modify text and numerical data displayed in the Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="91b8b-104">如果要显示不用于修改的数据，则必须将包含数据的列设置为只读。</span><span class="sxs-lookup"><span data-stu-id="91b8b-104">If you want to display data that is not meant for modification, you must make the columns that contain the data read-only.</span></span> <span data-ttu-id="91b8b-105">有关如何使控件完全成为只读控件的信息，请参阅[如何：使用设计器防止 Windows 窗体 DataGridView 控件中添加和删除行](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="91b8b-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span></span>

 <span data-ttu-id="91b8b-106">下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.DataGridView> 控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="91b8b-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="91b8b-107">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="91b8b-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-make-a-column-read-only-by-using-the-designer"></a><span data-ttu-id="91b8b-108">使用设计器使列成为只读的</span><span class="sxs-lookup"><span data-stu-id="91b8b-108">To make a column read-only by using the designer</span></span>

1. <span data-ttu-id="91b8b-109">单击 <xref:System.Windows.Forms.DataGridView> 控件右上角的智能标记标志符号（![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")），然后选择 "**编辑列**"。</span><span class="sxs-lookup"><span data-stu-id="91b8b-109">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="91b8b-110">从 "**选定的列**" 列表中选择一列。</span><span class="sxs-lookup"><span data-stu-id="91b8b-110">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="91b8b-111">在 "**列属性**" 网格中，将 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="91b8b-111">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="91b8b-112">您还可以通过在 "**添加列**" 对话框中选中 "**只读**" 复选框来添加列，以使其成为只读列。</span><span class="sxs-lookup"><span data-stu-id="91b8b-112">You can also make a column read-only when you add it by selecting the **Read Only** check box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="91b8b-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91b8b-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="91b8b-114">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="91b8b-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="91b8b-115">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지</span><span class="sxs-lookup"><span data-stu-id="91b8b-115">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="91b8b-116">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="91b8b-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="91b8b-117">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="91b8b-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
