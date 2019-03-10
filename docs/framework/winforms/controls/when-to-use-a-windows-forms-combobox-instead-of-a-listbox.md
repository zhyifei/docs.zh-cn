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
ms.openlocfilehash: 5dc7778f43c01fd28a14489a7b4179dd851568b2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702992"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="cd87d-102">何时使用 Windows 窗体 ComboBox 而非 ListBox</span><span class="sxs-lookup"><span data-stu-id="cd87d-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="cd87d-103"><xref:System.Windows.Forms.ComboBox>和<xref:System.Windows.Forms.ListBox>控件具有类似的行为，并在某些情况下可能是可互换。</span><span class="sxs-lookup"><span data-stu-id="cd87d-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="cd87d-104">有些的时候，但是，当一个或另一个是更适合于任务。</span><span class="sxs-lookup"><span data-stu-id="cd87d-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="cd87d-105">通常情况下，组合框进行了适当，有一组建议的选择，而列表框适合于你想要将输入限制为位于列表上。</span><span class="sxs-lookup"><span data-stu-id="cd87d-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="cd87d-106">组合框包含一个文本字段，因此可以在键入不在列表的选项。</span><span class="sxs-lookup"><span data-stu-id="cd87d-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="cd87d-107">例外情况是何时<xref:System.Windows.Forms.ComboBox.DropDownStyle%2A>属性设置为<xref:System.Windows.Forms.ComboBoxStyle.DropDownList>。</span><span class="sxs-lookup"><span data-stu-id="cd87d-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="cd87d-108">在这种情况下，该控件将选择一个项，如果键入其第一个字母。</span><span class="sxs-lookup"><span data-stu-id="cd87d-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="cd87d-109">此外，组合框在窗体上节省空间。</span><span class="sxs-lookup"><span data-stu-id="cd87d-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="cd87d-110">因为，只有在用户单击向下箭头，不显示的完整列表，组合框可以方便地放入列表框中放不下的小空间。</span><span class="sxs-lookup"><span data-stu-id="cd87d-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="cd87d-111">例外情况是何时<xref:System.Windows.Forms.ComboBox.DropDownStyle%2A>属性设置为<xref:System.Windows.Forms.ComboBoxStyle.Simple>： 显示的完整列表，并且占用更多的空间不是列表框将组合框。</span><span class="sxs-lookup"><span data-stu-id="cd87d-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd87d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd87d-112">See also</span></span>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="cd87d-113">如何：添加和删除项从 Windows 窗体 ComboBox、 ListBox 或 CheckedListBox 控件</span><span class="sxs-lookup"><span data-stu-id="cd87d-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="cd87d-114">如何：排序的内容的 Windows 窗体 ComboBox、 ListBox 或 CheckedListBox 控件</span><span class="sxs-lookup"><span data-stu-id="cd87d-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="cd87d-115">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="cd87d-115">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
