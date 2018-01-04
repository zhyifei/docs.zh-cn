---
title: "ComboBox 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ComboBox
helpviewer_keywords:
- drop-down lists [Windows Forms], Windows Forms
- ComboBox control [Windows Forms], about ComboBox control
- drop-down lists [Windows Forms], ComboBox control
- combo boxes [Windows Forms], about combo boxes
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 801ebb97c6ee52ce52bbb8f96a07d55e68ca6f1d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="combobox-control-overview-windows-forms"></a><span data-ttu-id="f1c6b-102">ComboBox 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="f1c6b-102">ComboBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="f1c6b-103">Windows 窗体<xref:System.Windows.Forms.ComboBox>控件用于在下拉组合框中显示数据。</span><span class="sxs-lookup"><span data-stu-id="f1c6b-103">The Windows Forms <xref:System.Windows.Forms.ComboBox> control is used to display data in a drop-down combo box.</span></span> <span data-ttu-id="f1c6b-104">默认情况下，<xref:System.Windows.Forms.ComboBox>控件出现在两个部分： 顶部是文本框中，用户可以键入列表项。</span><span class="sxs-lookup"><span data-stu-id="f1c6b-104">By default, the <xref:System.Windows.Forms.ComboBox> control appears in two parts: the top part is a text box that allows the user to type a list item.</span></span> <span data-ttu-id="f1c6b-105">第二部分是显示的项，用户可以从中选择一个列表的列表框。</span><span class="sxs-lookup"><span data-stu-id="f1c6b-105">The second part is a list box that displays a list of items from which the user can select one.</span></span> <span data-ttu-id="f1c6b-106">有关其他样式组合框的详细信息，请参阅[何时使用 Windows 窗体 ComboBox Instead of ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)。</span><span class="sxs-lookup"><span data-stu-id="f1c6b-106">For more information on other styles of combo box, see [When to Use a Windows Forms ComboBox Instead of a ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md).</span></span>  
  
 <span data-ttu-id="f1c6b-107"><xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>属性选择的列表项将返回一个对应的整数值。</span><span class="sxs-lookup"><span data-stu-id="f1c6b-107">The <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> property returns an integer value that corresponds to the selected list item.</span></span> <span data-ttu-id="f1c6b-108">你可以以编程方式更改选定的项，通过更改<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>代码中的值; 在列表中相应的项将出现在组合框的文本框部分。</span><span class="sxs-lookup"><span data-stu-id="f1c6b-108">You can programmatically change the selected item by changing the <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> value in code; the corresponding item in the list will appear in the text box portion of the combo box.</span></span> <span data-ttu-id="f1c6b-109">如果未不选定任何项，<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>值为-1。</span><span class="sxs-lookup"><span data-stu-id="f1c6b-109">If no item is selected, the <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> value is -1.</span></span> <span data-ttu-id="f1c6b-110">如果选择列表中的第一个项，则<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>值为 0。</span><span class="sxs-lookup"><span data-stu-id="f1c6b-110">If the first item in the list is selected, then the <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> value is 0.</span></span> <span data-ttu-id="f1c6b-111"><xref:System.Windows.Forms.ComboBox.SelectedItem%2A>属性是类似于<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>，但它返回项本身，而通常一个字符串值。</span><span class="sxs-lookup"><span data-stu-id="f1c6b-111">The <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> property is similar to <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> , but returns the item itself, usually a string value.</span></span> <span data-ttu-id="f1c6b-112"><xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A>属性反映在列表中，项的数目和的值<xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A>属性始终是一个多个是可能的最大<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>值因为<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>是从零开始。</span><span class="sxs-lookup"><span data-stu-id="f1c6b-112">The <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> property reflects the number of items in the list, and the value of the <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> property is always one more than the largest possible <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> value because <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> is zero-based.</span></span>  
  
 <span data-ttu-id="f1c6b-113">若要添加或删除中的项<xref:System.Windows.Forms.ComboBox>控制，请使用<xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>， <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>，<xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A>或<xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="f1c6b-113">To add or delete items in a <xref:System.Windows.Forms.ComboBox> control, use the <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> or <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A> method.</span></span> <span data-ttu-id="f1c6b-114">或者，你可以向列表添加项使用<xref:System.Windows.Forms.ComboBox.Items%2A>设计器中的属性。</span><span class="sxs-lookup"><span data-stu-id="f1c6b-114">Alternatively, you can add items to the list by using the <xref:System.Windows.Forms.ComboBox.Items%2A> property in the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1c6b-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1c6b-115">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 [<span data-ttu-id="f1c6b-116">ListBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="f1c6b-116">ListBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="f1c6b-117">何时使用 Windows 窗体 ComboBox 而非 ListBox</span><span class="sxs-lookup"><span data-stu-id="f1c6b-117">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [<span data-ttu-id="f1c6b-118">如何：在 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件中添加和删除项</span><span class="sxs-lookup"><span data-stu-id="f1c6b-118">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [<span data-ttu-id="f1c6b-119">如何：对 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件的内容进行排序</span><span class="sxs-lookup"><span data-stu-id="f1c6b-119">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [<span data-ttu-id="f1c6b-120">如何：在 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件中访问特定项</span><span class="sxs-lookup"><span data-stu-id="f1c6b-120">How to: Access Specific Items in a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)  
 [<span data-ttu-id="f1c6b-121">如何：将 Windows 窗体 ComboBox 或 ListBox 控件绑定到数据</span><span class="sxs-lookup"><span data-stu-id="f1c6b-121">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 [<span data-ttu-id="f1c6b-122">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="f1c6b-122">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)  
 [<span data-ttu-id="f1c6b-123">如何：创建 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件的查找表</span><span class="sxs-lookup"><span data-stu-id="f1c6b-123">How to: Create a Lookup Table for a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)
