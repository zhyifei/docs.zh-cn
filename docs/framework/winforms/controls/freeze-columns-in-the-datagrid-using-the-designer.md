---
title: 如何：冻结使用设计器在 Windows 窗体 DataGridView 控件中的列
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
ms.openlocfilehash: e3581390a56e2dfd19ed0d760a618993ec124bfb
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716837"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="d8274-102">如何：冻结使用设计器在 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="d8274-102">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="d8274-103">用户查看 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件中显示的数据时，有时需要频繁地引用单个列或列集。</span><span class="sxs-lookup"><span data-stu-id="d8274-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="d8274-104">例如，显示客户信息，其中包含许多列的表，请时很有用，以便在所有时间的同时使其他列的可见区域外滚动显示客户名称。</span><span class="sxs-lookup"><span data-stu-id="d8274-104">For example, when you display a table of customer information that contains many columns, it is useful for you to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>  
  
 <span data-ttu-id="d8274-105">若要实现此行为，可冻结控件中的列。</span><span class="sxs-lookup"><span data-stu-id="d8274-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="d8274-106">冻结列时，也将冻结其左侧（在从右到左的语言脚本中为右侧）的所有列。</span><span class="sxs-lookup"><span data-stu-id="d8274-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="d8274-107">冻结的列保持不变，而所有其他列可以滚动。</span><span class="sxs-lookup"><span data-stu-id="d8274-107">Frozen columns remain in place while all other columns can scroll.</span></span> <span data-ttu-id="d8274-108">如果启用了列重新排序，冻结的列被视为一组不同于未冻结的列。</span><span class="sxs-lookup"><span data-stu-id="d8274-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="d8274-109">用户可重新定位任一组中的列，但不能将列从一个组移到另一组。</span><span class="sxs-lookup"><span data-stu-id="d8274-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>  
  
 <span data-ttu-id="d8274-110">下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="d8274-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d8274-111">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="d8274-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8274-112">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="d8274-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d8274-113">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="d8274-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d8274-114">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="d8274-114">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-freeze-a-column-using-the-designer"></a><span data-ttu-id="d8274-115">若要冻结的列使用设计器</span><span class="sxs-lookup"><span data-stu-id="d8274-115">To freeze a column using the designer</span></span>  
  
1.  <span data-ttu-id="d8274-116">单击智能标记标志符号 (![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 上的右上角<xref:System.Windows.Forms.DataGridView>控件，然后选择**编辑列**。</span><span class="sxs-lookup"><span data-stu-id="d8274-116">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="d8274-117">选择一列从**选定列**列表。</span><span class="sxs-lookup"><span data-stu-id="d8274-117">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="d8274-118">在中**列属性**网格中，设置<xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="d8274-118">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8274-119">通过选择添加时，还可以冻结列**冻结**框中**添加列**对话框。</span><span class="sxs-lookup"><span data-stu-id="d8274-119">You can also freeze a column when adding it by selecting the **Frozen** box in the **Add Column** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8274-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8274-120">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d8274-121">如何：添加和使用设计器在 Windows 窗体 DataGridView 控件中删除列</span><span class="sxs-lookup"><span data-stu-id="d8274-121">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="d8274-122">如何：启用列重新排序中使用设计器在 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="d8274-122">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](enable-column-reordering-in-the-datagrid-using-the-designer.md)
- <span data-ttu-id="d8274-123">[如何：为全球化 Windows 窗体中显示从右到左文本](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d8274-123">[How to: Display Right-to-Left Text in Windows Forms for Globalization](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))</span></span>
- [<span data-ttu-id="d8274-124">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="d8274-124">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="d8274-125">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="d8274-125">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
