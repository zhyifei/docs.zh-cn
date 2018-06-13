---
title: 何时使用 Windows 窗体 ComboBox 而非 ListBox
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], vs. ComboBox
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- ComboBox control [Windows Forms], compared to ListBox
- combo boxes [Windows Forms], compared to list boxes
- ListBox control [Windows Forms], accessing items
- ListCount property
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
ms.openlocfilehash: 88b6a6023fbfdd8fa315fcd434357626ea69a9ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537763"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="9f81f-102">何时使用 Windows 窗体 ComboBox 而非 ListBox</span><span class="sxs-lookup"><span data-stu-id="9f81f-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="9f81f-103"><xref:System.Windows.Forms.ComboBox>和<xref:System.Windows.Forms.ListBox>控件具有类似的行为，并在某些情况下可能是可互换。</span><span class="sxs-lookup"><span data-stu-id="9f81f-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="9f81f-104">有的次，但是，当一个或另一个是更适合于任务。</span><span class="sxs-lookup"><span data-stu-id="9f81f-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="9f81f-105">通常情况下，组合框进行了适当，有一个建议的选项列表而列表框适合于你想要限制为列表上的输入。</span><span class="sxs-lookup"><span data-stu-id="9f81f-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="9f81f-106">组合框包含一个文本框字段，因此可以键入中不在列表的选项。</span><span class="sxs-lookup"><span data-stu-id="9f81f-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="9f81f-107">例外情况是当<xref:System.Windows.Forms.ComboBox.DropDownStyle%2A>属性设置为<xref:System.Windows.Forms.ComboBoxStyle.DropDownList>。</span><span class="sxs-lookup"><span data-stu-id="9f81f-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="9f81f-108">在这种情况下，控件将选择一个项，如果键入其第一个字母。</span><span class="sxs-lookup"><span data-stu-id="9f81f-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="9f81f-109">此外，组合框可节省窗体上的空间。</span><span class="sxs-lookup"><span data-stu-id="9f81f-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="9f81f-110">由于直到用户单击向下箭头，未显示的完整列表，可以轻松地在列表框中放不下小空间符合组合框。</span><span class="sxs-lookup"><span data-stu-id="9f81f-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="9f81f-111">例外情况是当<xref:System.Windows.Forms.ComboBox.DropDownStyle%2A>属性设置为<xref:System.Windows.Forms.ComboBoxStyle.Simple>： 则显示的完整列表，而组合框占用更多的空间比列表框。</span><span class="sxs-lookup"><span data-stu-id="9f81f-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f81f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f81f-112">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [<span data-ttu-id="9f81f-113">如何：在 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件中添加和删除项</span><span class="sxs-lookup"><span data-stu-id="9f81f-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [<span data-ttu-id="9f81f-114">如何：对 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件的内容进行排序</span><span class="sxs-lookup"><span data-stu-id="9f81f-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [<span data-ttu-id="9f81f-115">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="9f81f-115">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
