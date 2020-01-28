---
title: 使用设计器更改 DataGridView 列的类型
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 976f257d38dc7be5c904e63da47c61486bd3301c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737133"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="9756d-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤의 형식 변경</span><span class="sxs-lookup"><span data-stu-id="9756d-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="9756d-103">有时，您将需要更改已添加到 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件的列的类型。</span><span class="sxs-lookup"><span data-stu-id="9756d-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="9756d-104">例如，你可能想要修改在将控件绑定到数据源时自动生成的某些列的类型。</span><span class="sxs-lookup"><span data-stu-id="9756d-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="9756d-105">当所显示的表中的列包含对相关表中的行的外键时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="9756d-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="9756d-106">在这种情况下，您可能需要将显示这些外键的文本框列替换为组合框列，这些列显示了来自相关表的更有意义的值。</span><span class="sxs-lookup"><span data-stu-id="9756d-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>

 <span data-ttu-id="9756d-107">下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.DataGridView> 控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="9756d-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="9756d-108">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="9756d-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="9756d-109">使用设计器更改列的类型</span><span class="sxs-lookup"><span data-stu-id="9756d-109">To change the type of a column using the designer</span></span>

1. <span data-ttu-id="9756d-110">单击 <xref:System.Windows.Forms.DataGridView> 控件右上角的智能标记标志符号（![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")），然后选择 "**编辑列**"。</span><span class="sxs-lookup"><span data-stu-id="9756d-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="9756d-111">从 "**选定的列**" 列表中选择一列。</span><span class="sxs-lookup"><span data-stu-id="9756d-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="9756d-112">在 "**列属性**" 网格中，将 "`ColumnType`" 属性设置为新的列类型。</span><span class="sxs-lookup"><span data-stu-id="9756d-112">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9756d-113">`ColumnType` 属性是一个仅限设计时的属性，该属性指示表示列类型的类。</span><span class="sxs-lookup"><span data-stu-id="9756d-113">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="9756d-114">它不是列类中定义的实际属性。</span><span class="sxs-lookup"><span data-stu-id="9756d-114">It is not an actual property defined in a column class.</span></span>

## <a name="see-also"></a><span data-ttu-id="9756d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9756d-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [<span data-ttu-id="9756d-116">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="9756d-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="9756d-117">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="9756d-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
