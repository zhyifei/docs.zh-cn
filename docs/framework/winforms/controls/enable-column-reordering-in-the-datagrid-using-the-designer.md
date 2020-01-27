---
title: 使用设计器在 DataGridView 控件中启用列重新排序
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 823c0064b2710ab5dfd0f67edf95374590d4490b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745842"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="e2e2b-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용</span><span class="sxs-lookup"><span data-stu-id="e2e2b-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="e2e2b-103">查看 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件中显示的数据时，用户有时需要比较特定列中的值。</span><span class="sxs-lookup"><span data-stu-id="e2e2b-103">When viewing data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, users sometimes want to compare the values in specific columns.</span></span> <span data-ttu-id="e2e2b-104">如果在控件中广泛地分隔列，则这会很不方便，尤其是在用户必须水平来回滚动以便查看他们感兴趣的所有列时。</span><span class="sxs-lookup"><span data-stu-id="e2e2b-104">This can be inconvenient if the columns are widely separated in the control, especially if users must scroll back and forth horizontally in order to see all the columns they are interested in.</span></span> <span data-ttu-id="e2e2b-105">您可以通过使您的用户能够对列进行重新排序，使比较列值的任务变得更容易。</span><span class="sxs-lookup"><span data-stu-id="e2e2b-105">You can make the task of comparing column values easier by enabling your users to reorder the columns.</span></span> <span data-ttu-id="e2e2b-106">启用列重新排序后，用户可以通过用鼠标拖动列标题来将列移动到新位置。</span><span class="sxs-lookup"><span data-stu-id="e2e2b-106">When you enable column reordering, users can move a column to a new position by dragging the column header with the mouse.</span></span>

 <span data-ttu-id="e2e2b-107">下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.DataGridView> 控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="e2e2b-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="e2e2b-108">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="e2e2b-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-enable-column-reordering"></a><span data-ttu-id="e2e2b-109">启用列重新排序</span><span class="sxs-lookup"><span data-stu-id="e2e2b-109">To enable column reordering</span></span>

- <span data-ttu-id="e2e2b-110">单击 <xref:System.Windows.Forms.DataGridView> 控件右上角的智能标记标志符号（![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")），然后选择 "**启用列重新排序**"。</span><span class="sxs-lookup"><span data-stu-id="e2e2b-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Enable Column Reordering**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2e2b-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2e2b-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e2e2b-112">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 고정</span><span class="sxs-lookup"><span data-stu-id="e2e2b-112">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="e2e2b-113">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="e2e2b-113">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="e2e2b-114">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="e2e2b-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
