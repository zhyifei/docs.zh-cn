---
title: DomainUpDown 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: 1849e1bab440d779eaebfc7d2cd12e817c31bf79
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605414"
---
# <a name="domainupdown-control-overview-windows-forms"></a><span data-ttu-id="b4990-102">DomainUpDown 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="b4990-102">DomainUpDown Control Overview (Windows Forms)</span></span>
<span data-ttu-id="b4990-103">Windows 窗体<xref:System.Windows.Forms.DomainUpDown>控件是一对用于列表中向上或向下移动按钮和实质上是组合的文本框。</span><span class="sxs-lookup"><span data-stu-id="b4990-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control is essentially a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="b4990-104">该控件显示并从选项列表中设置一个文本字符串。</span><span class="sxs-lookup"><span data-stu-id="b4990-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="b4990-105">用户可以选择字符串，通过单击向上和向下按钮以浏览列表中，通过按向上和向下箭头键，或通过键入与匹配列表中的项的字符串。</span><span class="sxs-lookup"><span data-stu-id="b4990-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="b4990-106">此控件的可能用途之一是从名称按字母顺序排序列表中选择项。</span><span class="sxs-lookup"><span data-stu-id="b4990-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4990-107">若要对列表进行排序，设置<xref:System.Windows.Forms.DomainUpDown.Sorted%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="b4990-107">To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="b4990-108">此控件的功能是非常类似于列表框或组合框中，但其占用空间很少。</span><span class="sxs-lookup"><span data-stu-id="b4990-108">The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="b4990-109">键属性</span><span class="sxs-lookup"><span data-stu-id="b4990-109">Key Properties</span></span>  
 <span data-ttu-id="b4990-110">控件的主要属性包括<xref:System.Windows.Forms.DomainUpDown.Items%2A>， <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>，和<xref:System.Windows.Forms.DomainUpDown.Wrap%2A>。</span><span class="sxs-lookup"><span data-stu-id="b4990-110">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="b4990-111"><xref:System.Windows.Forms.DomainUpDown.Items%2A>属性包含的控件中显示其文本值的对象的列表。</span><span class="sxs-lookup"><span data-stu-id="b4990-111">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="b4990-112">如果<xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>设置为`false`，该控件自动完成用户类型，并为列表中的值匹配的文本。</span><span class="sxs-lookup"><span data-stu-id="b4990-112">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="b4990-113">如果<xref:System.Windows.Forms.DomainUpDown.Wrap%2A>设置为`true`，滚过最后一项将转到第一个项列表中，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="b4990-113">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="b4990-114">控件的主要方法是<xref:System.Windows.Forms.DomainUpDown.UpButton%2A>和<xref:System.Windows.Forms.DomainUpDown.DownButton%2A>。</span><span class="sxs-lookup"><span data-stu-id="b4990-114">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="b4990-115">此控件只显示文本字符串。</span><span class="sxs-lookup"><span data-stu-id="b4990-115">This control displays only text strings.</span></span> <span data-ttu-id="b4990-116">如果你想显示的数字值的控件，使用<xref:System.Windows.Forms.NumericUpDown>控件。</span><span class="sxs-lookup"><span data-stu-id="b4990-116">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="b4990-117">有关详细信息，请参阅[NumericUpDown 控件概述](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="b4990-117">For more information, see [NumericUpDown Control Overview](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4990-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4990-118">See also</span></span>
- <xref:System.Windows.Forms.DomainUpDown>
- [<span data-ttu-id="b4990-119">DomainUpDown 控件</span><span class="sxs-lookup"><span data-stu-id="b4990-119">DomainUpDown Control</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)
