---
title: 使用设计器为 DataGridView 控件设置交替行样式
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: 74f65d03a359136de943f8a2937ed5e5f1e62519
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743046"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="80198-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="80198-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="80198-103">表格数据通常以类似帐目的格式显示，其中交替行具有不同的背景色。</span><span class="sxs-lookup"><span data-stu-id="80198-103">Tabular data is often presented in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="80198-104">이 형식을 사용하면 특히 많은 열을 포함하는 넓은 테이블에서 사용자가 각 행에 있는 셀을 쉽게 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80198-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>

<span data-ttu-id="80198-105"><xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하여 교대로 반복되는 행에 대한 전체 스타일 정보를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80198-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="80198-106">除了背景色以外，还可以使用样式特征（如前景颜色和字体）来区分交替行。</span><span class="sxs-lookup"><span data-stu-id="80198-106">You can use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span> <span data-ttu-id="80198-107">有关详细信息，请参阅[Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="80198-107">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="80198-108">下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.DataGridView> 控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="80198-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="80198-109">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="80198-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="define-styles-for-alternating-rows"></a><span data-ttu-id="80198-110">定义交替行的样式</span><span class="sxs-lookup"><span data-stu-id="80198-110">Define styles for alternating rows</span></span>

1. <span data-ttu-id="80198-111">在设计器中选择 "<xref:System.Windows.Forms.DataGridView>" 控件。</span><span class="sxs-lookup"><span data-stu-id="80198-111">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>

2. <span data-ttu-id="80198-112">在 "**属性**" 窗口中，单击 "<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>" 属性旁边的省略号按钮（![](./media/visual-studio-ellipsis-button.png)）属性窗口中的省略号按钮（...）。</span><span class="sxs-lookup"><span data-stu-id="80198-112">In the **Properties** window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> property.</span></span>

3. <span data-ttu-id="80198-113">在 " **CellStyle 生成器**" 对话框中，通过设置属性来定义样式，并使用**预览**窗格来确认所做的选择。</span><span class="sxs-lookup"><span data-stu-id="80198-113">In the **CellStyle Builder** dialog box, define the style by setting the properties, and use the **Preview** pane to confirm your choices.</span></span> <span data-ttu-id="80198-114">指定的样式将用于在控件中显示的每个其他行，从第二行开始。</span><span class="sxs-lookup"><span data-stu-id="80198-114">The styles you specify are used for every other row displayed in the control, starting with the second one.</span></span>

4. <span data-ttu-id="80198-115">若要为其余行定义样式，请使用 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> 属性重复步骤2和3。</span><span class="sxs-lookup"><span data-stu-id="80198-115">To define styles for the remaining rows, repeat steps 2 and 3 using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property.</span></span>

    > [!NOTE]
    > <span data-ttu-id="80198-116">使用从多个属性继承的样式显示单元。</span><span class="sxs-lookup"><span data-stu-id="80198-116">Cells are displayed using styles inherited from multiple properties.</span></span> <span data-ttu-id="80198-117">有关样式继承的详细信息，请参阅[Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="80198-117">For more information about style inheritance, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="80198-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80198-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="80198-119">Windows Forms DataGridView 컨트롤의 셀 스타일</span><span class="sxs-lookup"><span data-stu-id="80198-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="80198-120">Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="80198-120">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="80198-121">Windows Forms DataGridView 컨트롤에 디자이너 사용</span><span class="sxs-lookup"><span data-stu-id="80198-121">Using the Designer with the Windows Forms DataGridView Control</span></span>](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="80198-122">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="80198-122">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="80198-123">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="80198-123">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
