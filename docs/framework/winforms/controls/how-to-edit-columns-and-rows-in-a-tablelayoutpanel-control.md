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
ms.openlocfilehash: 4473b20eea57088104a51eb1b6c080219223d214
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628639"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="0d15f-102">如何：在 TableLayoutPanel 控件中编辑行和列</span><span class="sxs-lookup"><span data-stu-id="0d15f-102">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>

<span data-ttu-id="0d15f-103">您可以使用称为 "**列和行样式**" 对话框的 <xref:System.Windows.Forms.TableLayoutPanel> 控件的集合编辑器来编辑控件的行和列。</span><span class="sxs-lookup"><span data-stu-id="0d15f-103">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>

> [!NOTE]
> <span data-ttu-id="0d15f-104">如果希望控件跨多个行或列，请设置控件的 "`RowSpan`" 和 "`ColumnSpan`" 属性。</span><span class="sxs-lookup"><span data-stu-id="0d15f-104">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="0d15f-105">有关详细信息，请参阅 [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)。</span><span class="sxs-lookup"><span data-stu-id="0d15f-105">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>
>
> <span data-ttu-id="0d15f-106">如果要在单元格中对齐控件，或者希望控件在单元格内伸展，请使用控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="0d15f-106">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="0d15f-107">有关详细信息，请参阅 [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)。</span><span class="sxs-lookup"><span data-stu-id="0d15f-107">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>

## <a name="to-edit-rows-and-columns"></a><span data-ttu-id="0d15f-108">编辑行和列</span><span class="sxs-lookup"><span data-stu-id="0d15f-108">To edit rows and columns</span></span>

1. <span data-ttu-id="0d15f-109">从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="0d15f-109">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="0d15f-110">单击 <xref:System.Windows.Forms.TableLayoutPanel> 控件的设计器操作标志符号（![小型黑色箭头](./media/designer-actions-glyph.gif)），然后选择 "**编辑行和列**" 以打开 "**列和行样式**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="0d15f-110">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="0d15f-111">您还可以右键单击 "<xref:System.Windows.Forms.TableLayoutPanel>" 控件，然后从快捷菜单中选择 "**编辑行和列**"。</span><span class="sxs-lookup"><span data-stu-id="0d15f-111">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>

3. <span data-ttu-id="0d15f-112">若要添加或删除列，请从 "**成员类型**" 下拉列表框中选择 "**列**"。</span><span class="sxs-lookup"><span data-stu-id="0d15f-112">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>

4. <span data-ttu-id="0d15f-113">若要添加或删除行，请从 "**成员类型**" 下拉列表框中选择 "**行**"。</span><span class="sxs-lookup"><span data-stu-id="0d15f-113">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>

5. <span data-ttu-id="0d15f-114">单击 "**添加**" 按钮可向**成员列表**的末尾添加行或列。</span><span class="sxs-lookup"><span data-stu-id="0d15f-114">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>

6. <span data-ttu-id="0d15f-115">单击 "**插入**" 按钮，在列表中当前选定的项之前添加行或列。</span><span class="sxs-lookup"><span data-stu-id="0d15f-115">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>

7. <span data-ttu-id="0d15f-116">如果要添加行或列，请选择新行或列的**大小类型**。</span><span class="sxs-lookup"><span data-stu-id="0d15f-116">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="0d15f-117">有关详细信息，请参阅 <xref:System.Windows.Forms.SizeType>。</span><span class="sxs-lookup"><span data-stu-id="0d15f-117">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>

8. <span data-ttu-id="0d15f-118">若要删除行或列，请单击 "**删除**" 按钮以删除**成员列表**中当前选定的项。</span><span class="sxs-lookup"><span data-stu-id="0d15f-118">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d15f-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d15f-119">See also</span></span>

- <xref:System.Windows.Forms.SizeType>
- [<span data-ttu-id="0d15f-120">TableLayoutPanel 控件</span><span class="sxs-lookup"><span data-stu-id="0d15f-120">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
