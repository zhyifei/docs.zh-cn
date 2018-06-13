---
title: DomainUpDown 控件（Windows 窗体）
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: c23f374f1ec9cab6e43b12d32b97c40533ac36cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527321"
---
# <a name="domainupdown-control-windows-forms"></a><span data-ttu-id="4cc9b-102">DomainUpDown 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="4cc9b-102">DomainUpDown Control (Windows Forms)</span></span>
<span data-ttu-id="4cc9b-103">Windows 窗体<xref:System.Windows.Forms.DomainUpDown>如下所示的成对的按钮和文本框中的组合的控件的向上或向下滚动到列表。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control looks like a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="4cc9b-104">该控件显示，并设置从选项列表中的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="4cc9b-105">用户可以选择字符串，通过单击向上和向下按钮来浏览列表，按向上和向下箭头键，或通过键入与列表中的项匹配的字符串。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="4cc9b-106">对于此控件的可能用途之一是用于从名称按字母顺序排序列表中选择项。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span> <span data-ttu-id="4cc9b-107">(若要对列表进行排序，将设置<xref:System.Windows.Forms.DomainUpDown.Sorted%2A>属性`true`。)此控件的功能是非常类似于列表框或组合框中，但其占用很少的空间。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-107">(To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.) The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
 <span data-ttu-id="4cc9b-108">控件的主要属性包括<xref:System.Windows.Forms.DomainUpDown.Items%2A>， <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>，和<xref:System.Windows.Forms.DomainUpDown.Wrap%2A>。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-108">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="4cc9b-109"><xref:System.Windows.Forms.DomainUpDown.Items%2A>属性包含的控件中显示其文本值的对象的列表。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-109">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="4cc9b-110">如果<xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>设置为`false`，该控件自动完成用户键入，并与列表中的值进行匹配的文本。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-110">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="4cc9b-111">如果<xref:System.Windows.Forms.DomainUpDown.Wrap%2A>设置为`true`，滚过最后一项将转到第一项在列表中，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-111">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="4cc9b-112">控件的主要方法是<xref:System.Windows.Forms.DomainUpDown.UpButton%2A>和<xref:System.Windows.Forms.DomainUpDown.DownButton%2A>。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-112">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="4cc9b-113">此控件显示仅文本字符串。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-113">This control displays only text strings.</span></span> <span data-ttu-id="4cc9b-114">如果你希望显示数字值的控件，使用<xref:System.Windows.Forms.NumericUpDown>控件。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-114">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="4cc9b-115">有关详细信息，请参阅[NumericUpDown 控件](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-115">For more information, see [NumericUpDown Control](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md) .</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4cc9b-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="4cc9b-116">In This Section</span></span>  
 [<span data-ttu-id="4cc9b-117">DomainUpDown 控件概述</span><span class="sxs-lookup"><span data-stu-id="4cc9b-117">DomainUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)  
 <span data-ttu-id="4cc9b-118">引入了的一般概念<xref:System.Windows.Forms.DomainUpDown>控件，它允许用户通过浏览并从文本字符串的列表中选择。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-118">Introduces the general concepts of the <xref:System.Windows.Forms.DomainUpDown> control, which allows users to browse through and select from a list of text strings.</span></span>  
  
 [<span data-ttu-id="4cc9b-119">如何：以编程方式向 Windows 窗体 DomainUpDown 控件添加项</span><span class="sxs-lookup"><span data-stu-id="4cc9b-119">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>](../../../../docs/framework/winforms/controls/how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 <span data-ttu-id="4cc9b-120">介绍如何指定文本字符串<xref:System.Windows.Forms.DomainUpDown>控件应显示。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-120">Describes how to specify the text strings the <xref:System.Windows.Forms.DomainUpDown> control should display.</span></span>  
  
 [<span data-ttu-id="4cc9b-121">如何：从 Windows 窗体 DomainUpDown 控件中删除项</span><span class="sxs-lookup"><span data-stu-id="4cc9b-121">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 <span data-ttu-id="4cc9b-122">描述如何删除项从<xref:System.Windows.Forms.DomainUpDown>在代码中的控件。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-122">Describes how to delete items from the <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4cc9b-123">参考</span><span class="sxs-lookup"><span data-stu-id="4cc9b-123">Reference</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 <span data-ttu-id="4cc9b-124">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-124">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 <span data-ttu-id="4cc9b-125">对此类进行描述，并提供指向其所有成员...</span><span class="sxs-lookup"><span data-stu-id="4cc9b-125">Describes this class and has links to all its members..</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4cc9b-126">相关章节</span><span class="sxs-lookup"><span data-stu-id="4cc9b-126">Related Sections</span></span>  
 [<span data-ttu-id="4cc9b-127">可在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="4cc9b-127">Controls You Can Use On Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="4cc9b-128">提供 Windows 窗体控件的完整列表，附带其使用情况相关信息的链接。</span><span class="sxs-lookup"><span data-stu-id="4cc9b-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
