---
title: 如何：在 TableLayoutPanel 控件中编辑行和列
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: 820d2f98290650bfaf377bd2d4b863dfb2e6e704
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500779"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="e5650-102">如何：在 TableLayoutPanel 控件中编辑行和列</span><span class="sxs-lookup"><span data-stu-id="e5650-102">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>
<span data-ttu-id="e5650-103">可以使用的集合编辑器<xref:System.Windows.Forms.TableLayoutPanel>控件，调用**列和行样式**对话框中，若要编辑的行和列的控件。</span><span class="sxs-lookup"><span data-stu-id="e5650-103">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5650-104">如果你想要跨多个行或列的控件，设置`RowSpan`和`ColumnSpan`控件上的属性。</span><span class="sxs-lookup"><span data-stu-id="e5650-104">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="e5650-105">有关详细信息，请参阅 [演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)。</span><span class="sxs-lookup"><span data-stu-id="e5650-105">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="e5650-106">如果你想要对齐控件中某一单元，或者如果你想要在单元格中拉伸的控件，使用控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e5650-106">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="e5650-107">有关详细信息，请参阅 [演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)。</span><span class="sxs-lookup"><span data-stu-id="e5650-107">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="e5650-108">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="e5650-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e5650-109">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="e5650-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e5650-110">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="e5650-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-edit-rows-and-columns"></a><span data-ttu-id="e5650-111">若要编辑行和列</span><span class="sxs-lookup"><span data-stu-id="e5650-111">To edit rows and columns</span></span>  
  
1.  <span data-ttu-id="e5650-112">拖动<xref:System.Windows.Forms.TableLayoutPanel>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="e5650-112">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="e5650-113">单击<xref:System.Windows.Forms.TableLayoutPanel>控件的智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))，然后选择**编辑行和列**打开**列和行样式**对话框。</span><span class="sxs-lookup"><span data-stu-id="e5650-113">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="e5650-114">也可以右键单击<xref:System.Windows.Forms.TableLayoutPanel>控件，然后选择**编辑行和列**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="e5650-114">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="e5650-115">若要添加或删除列，请选择**列**从**成员类型**下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="e5650-115">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>  
  
4.  <span data-ttu-id="e5650-116">若要添加或删除的行，请选择**行**从**成员类型**下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="e5650-116">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>  
  
5.  <span data-ttu-id="e5650-117">单击**外**按钮以将行或列添加到末尾**成员**列表。</span><span class="sxs-lookup"><span data-stu-id="e5650-117">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>  
  
6.  <span data-ttu-id="e5650-118">单击**插入**按钮在列表中添加行或当前所选的项之前的列。</span><span class="sxs-lookup"><span data-stu-id="e5650-118">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>  
  
7.  <span data-ttu-id="e5650-119">如果要添加的行或列，选择**大小类型**新行或列。</span><span class="sxs-lookup"><span data-stu-id="e5650-119">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="e5650-120">有关详细信息，请参阅<xref:System.Windows.Forms.SizeType>。</span><span class="sxs-lookup"><span data-stu-id="e5650-120">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>  
  
8.  <span data-ttu-id="e5650-121">若要删除的行或列，请单击**删除**按钮以删除当前选定的项中**成员**列表。</span><span class="sxs-lookup"><span data-stu-id="e5650-121">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5650-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5650-122">See Also</span></span>  
 <xref:System.Windows.Forms.SizeType>  
 [<span data-ttu-id="e5650-123">TableLayoutPanel 控件</span><span class="sxs-lookup"><span data-stu-id="e5650-123">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
