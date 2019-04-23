---
title: 如何：使用设计器设置 Windows 窗体 DataGridView 控件的交替行样式
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: fb338a3616bc20542ec940db5977c4ffdab9654c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335623"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="287a4-102">如何：使用设计器设置 Windows 窗体 DataGridView 控件的交替行样式</span><span class="sxs-lookup"><span data-stu-id="287a4-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="287a4-103">表格数据通常显示其中的交替行具有不同的背景色以类似帐目的格式。</span><span class="sxs-lookup"><span data-stu-id="287a4-103">Tabular data is often presented in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="287a4-104">这种格式使用户可以更轻松地分辨每一行的单元格，尤其是有多列的宽表。</span><span class="sxs-lookup"><span data-stu-id="287a4-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>  
  
 <span data-ttu-id="287a4-105">借助 <xref:System.Windows.Forms.DataGridView> 控件，可为交替行指定完整的样式信息。</span><span class="sxs-lookup"><span data-stu-id="287a4-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="287a4-106">可以使用如前景色和字体、 背景色以及样式特征来区分交替行。</span><span class="sxs-lookup"><span data-stu-id="287a4-106">You can use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span> <span data-ttu-id="287a4-107">有关详细信息，请参阅[Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="287a4-107">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="287a4-108">下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="287a4-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="287a4-109">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="287a4-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="287a4-110">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="287a4-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="287a4-111">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="287a4-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="287a4-112">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="287a4-112">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="define-styles-for-alternating-rows"></a><span data-ttu-id="287a4-113">定义的交替行样式</span><span class="sxs-lookup"><span data-stu-id="287a4-113">Define styles for alternating rows</span></span>  
  
1. <span data-ttu-id="287a4-114">选择<xref:System.Windows.Forms.DataGridView>控件在设计器中的。</span><span class="sxs-lookup"><span data-stu-id="287a4-114">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>  
  
2. <span data-ttu-id="287a4-115">在中**属性**窗口中，单击省略号按钮 (![VisualStudioEllipsesButton 屏幕快照](../media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="287a4-115">In the **Properties** window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> property.</span></span>  
  
3. <span data-ttu-id="287a4-116">在中**CellStyle 生成器**对话框中，通过设置属性，定义样式，并使用**预览**窗格，以确认所做的选择。</span><span class="sxs-lookup"><span data-stu-id="287a4-116">In the **CellStyle Builder** dialog box, define the style by setting the properties, and use the **Preview** pane to confirm your choices.</span></span> <span data-ttu-id="287a4-117">您指定的样式用于在控件中，从第二个显示的所有其他行。</span><span class="sxs-lookup"><span data-stu-id="287a4-117">The styles you specify are used for every other row displayed in the control, starting with the second one.</span></span>  
  
4. <span data-ttu-id="287a4-118">若要定义的剩余行的样式，请重复步骤 2 和 3 使用<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="287a4-118">To define styles for the remaining rows, repeat steps 2 and 3 using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="287a4-119">单元格的显示使用继承自多个属性的样式。</span><span class="sxs-lookup"><span data-stu-id="287a4-119">Cells are displayed using styles inherited from multiple properties.</span></span> <span data-ttu-id="287a4-120">有关样式继承的详细信息，请参阅[Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="287a4-120">For more information about style inheritance, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="287a4-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="287a4-121">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="287a4-122">Windows 窗体 DataGridView 控件中的单元格样式</span><span class="sxs-lookup"><span data-stu-id="287a4-122">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="287a4-123">Windows 窗体 DataGridView 控件中的基本格式和样式设置</span><span class="sxs-lookup"><span data-stu-id="287a4-123">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="287a4-124">将设计器与 Windows 窗体 DataGridView 控件结合使用</span><span class="sxs-lookup"><span data-stu-id="287a4-124">Using the Designer with the Windows Forms DataGridView Control</span></span>](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="287a4-125">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="287a4-125">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="287a4-126">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="287a4-126">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
