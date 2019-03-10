---
title: 如何：使列成为只读使用设计器在 Windows 窗体 DataGridView 控件中
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 0219f0cf50d9cce630dc44a37dd3c16d26874012
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718553"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="aec23-102">如何：使列成为只读使用设计器在 Windows 窗体 DataGridView 控件中</span><span class="sxs-lookup"><span data-stu-id="aec23-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="aec23-103">默认情况下，用户可以修改文本和在 Windows 窗体中显示的数字数据<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="aec23-103">By default, users can modify text and numerical data displayed in the Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="aec23-104">如果你想要显示不希望修改的数据，必须进行包含只读数据的列。</span><span class="sxs-lookup"><span data-stu-id="aec23-104">If you want to display data that is not meant for modification, you must make the columns that contain the data read-only.</span></span> <span data-ttu-id="aec23-105">有关如何使控件完全只读的信息，请参阅[如何：防止行中添加和删除 Windows 窗体 DataGridView 控件使用设计器](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="aec23-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span></span>  
  
 <span data-ttu-id="aec23-106">下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="aec23-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="aec23-107">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="aec23-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aec23-108">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="aec23-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="aec23-109">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="aec23-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="aec23-110">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="aec23-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-make-a-column-read-only-by-using-the-designer"></a><span data-ttu-id="aec23-111">若要使用设计器使列成为只读</span><span class="sxs-lookup"><span data-stu-id="aec23-111">To make a column read-only by using the designer</span></span>  
  
1.  <span data-ttu-id="aec23-112">单击智能标记标志符号 (![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 上的右上角<xref:System.Windows.Forms.DataGridView>控件，然后选择**编辑列**。</span><span class="sxs-lookup"><span data-stu-id="aec23-112">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="aec23-113">选择一列从**选定列**列表。</span><span class="sxs-lookup"><span data-stu-id="aec23-113">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="aec23-114">在中**列属性**网格中，设置<xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="aec23-114">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aec23-115">您还可以列只读时通过选择添加**Read Only**中的复选框**添加列**对话框。</span><span class="sxs-lookup"><span data-stu-id="aec23-115">You can also make a column read-only when you add it by selecting the **Read Only** check box in the **Add Column** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aec23-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="aec23-116">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="aec23-117">如何：添加和使用设计器在 Windows 窗体 DataGridView 控件中删除列</span><span class="sxs-lookup"><span data-stu-id="aec23-117">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="aec23-118">如何：防止添加和使用设计器在 Windows 窗体 DataGridView 控件中的删除行</span><span class="sxs-lookup"><span data-stu-id="aec23-118">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="aec23-119">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="aec23-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="aec23-120">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="aec23-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
