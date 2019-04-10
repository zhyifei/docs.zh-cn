---
title: 如何：使用设计器隐藏 Windows 窗体 DataGridView 控件中的列
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: aa81eb7470b818fa2b65200503e5ce65b467c0f2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324443"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="f6f1e-102">如何：使用设计器隐藏 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="f6f1e-102">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="f6f1e-103">有时，你会想仅显示在 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件中可用的某些列。</span><span class="sxs-lookup"><span data-stu-id="f6f1e-103">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f6f1e-104">例如，你可能想要显示某位员工到具有管理凭据，而隐藏的其他用户的用户的工资列。</span><span class="sxs-lookup"><span data-stu-id="f6f1e-104">For example, you may want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="f6f1e-105">或者，你可能想要将控件绑定到包含许多列，其中仅有一些你想要显示的数据源。</span><span class="sxs-lookup"><span data-stu-id="f6f1e-105">Alternately, you may want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="f6f1e-106">在这种情况下，你通常会移除不感兴趣显示，而不是隐藏它们的列。</span><span class="sxs-lookup"><span data-stu-id="f6f1e-106">In this case, you will typically remove the columns you are not interested in displaying rather than hiding them.</span></span> <span data-ttu-id="f6f1e-107">有关详细信息，请参阅[如何：添加和删除列在 Windows 窗体 DataGridView 控件使用设计器](add-and-remove-columns-in-the-datagrid-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="f6f1e-107">For more information, see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
 <span data-ttu-id="f6f1e-108">下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="f6f1e-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f6f1e-109">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="f6f1e-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6f1e-110">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="f6f1e-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f6f1e-111">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="f6f1e-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f6f1e-112">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="f6f1e-112">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-hide-a-column-using-the-designer"></a><span data-ttu-id="f6f1e-113">若要隐藏某一列使用设计器</span><span class="sxs-lookup"><span data-stu-id="f6f1e-113">To hide a column using the designer</span></span>  
  
1. <span data-ttu-id="f6f1e-114">单击智能标记标志符号 (![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 上的右上角<xref:System.Windows.Forms.DataGridView>控件，然后选择**编辑列**。</span><span class="sxs-lookup"><span data-stu-id="f6f1e-114">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2. <span data-ttu-id="f6f1e-115">选择一列从**选定列**列表。</span><span class="sxs-lookup"><span data-stu-id="f6f1e-115">Select a column from the **Selected Columns** list.</span></span>  
  
3. <span data-ttu-id="f6f1e-116">在中**列属性**网格中，设置<xref:System.Windows.Forms.DataGridViewColumn.Visible%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="f6f1e-116">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property to `false`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6f1e-117">您还可以隐藏某一列时将其添加通过清除**Visible**中的复选框**添加列**对话框。</span><span class="sxs-lookup"><span data-stu-id="f6f1e-117">You can also hide a column when adding it by clearing the **Visible** check box in the **Add Column** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6f1e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6f1e-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f6f1e-119">如何：使用设计器添加和移除 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="f6f1e-119">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="f6f1e-120">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="f6f1e-120">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="f6f1e-121">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="f6f1e-121">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
