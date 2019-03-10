---
title: CheckBox 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
ms.openlocfilehash: 003e57db16c35b519d3948fc24e82a94a5c3744d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713440"
---
# <a name="checkbox-control-overview-windows-forms"></a><span data-ttu-id="ec61b-102">CheckBox 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="ec61b-102">CheckBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="ec61b-103">Windows 窗体 <xref:System.Windows.Forms.CheckBox> 控件指示特定条件处于打开开始关闭状态。</span><span class="sxs-lookup"><span data-stu-id="ec61b-103">The Windows Forms <xref:System.Windows.Forms.CheckBox> control indicates whether a particular condition is on or off.</span></span> <span data-ttu-id="ec61b-104">通常用于向用户显示 Yes/No 或 True/False 选项。</span><span class="sxs-lookup"><span data-stu-id="ec61b-104">It is commonly used to present a Yes/No or True/False selection to the user.</span></span> <span data-ttu-id="ec61b-105">可以使用组中的复选框控件来显示用户可从中选择一个或多选的多个选项。</span><span class="sxs-lookup"><span data-stu-id="ec61b-105">You can use check box controls in groups to display multiple choices from which the user can select one or more.</span></span>  
  
 <span data-ttu-id="ec61b-106">复选框控件的单选按钮控件相似，在于每个用来指示用户所做的选择。</span><span class="sxs-lookup"><span data-stu-id="ec61b-106">The check box control is similar to the radio button control in that each is used to indicate a selection that is made by the user.</span></span> <span data-ttu-id="ec61b-107">它们不同组中的只有一个单选按钮在一次，可以选择的。</span><span class="sxs-lookup"><span data-stu-id="ec61b-107">They differ in that only one radio button in a group can be selected at a time.</span></span> <span data-ttu-id="ec61b-108">与复选框控件，但是，任意数量的复选框可以选择。</span><span class="sxs-lookup"><span data-stu-id="ec61b-108">With the check box control, however, any number of check boxes may be selected.</span></span>  
  
 <span data-ttu-id="ec61b-109">复选框可能连接到数据库使用简单数据绑定中的元素。</span><span class="sxs-lookup"><span data-stu-id="ec61b-109">A check box may be connected to elements in a database using simple data binding.</span></span> <span data-ttu-id="ec61b-110">可使用组合多个复选框<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="ec61b-110">Multiple check boxes may be grouped using the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="ec61b-111">这是用于可视外观和用户界面设计也有用，因为分组后的控件可以一起移动窗体设计器上。</span><span class="sxs-lookup"><span data-stu-id="ec61b-111">This is useful for visual appearance and also for user interface design, since grouped controls can be moved around together on the form designer.</span></span> <span data-ttu-id="ec61b-112">有关详细信息，请参阅[Windows 窗体数据绑定](../windows-forms-data-binding.md)并[GroupBox 控件](groupbox-control-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="ec61b-112">For more information, see [Windows Forms Data Binding](../windows-forms-data-binding.md) and [GroupBox Control](groupbox-control-windows-forms.md).</span></span>  
  
 <span data-ttu-id="ec61b-113"><xref:System.Windows.Forms.CheckBox>控件具有两个重要属性<xref:System.Windows.Forms.CheckBox.Checked%2A>和<xref:System.Windows.Forms.CheckBox.CheckState%2A>。</span><span class="sxs-lookup"><span data-stu-id="ec61b-113">The <xref:System.Windows.Forms.CheckBox> control has two important properties, <xref:System.Windows.Forms.CheckBox.Checked%2A> and <xref:System.Windows.Forms.CheckBox.CheckState%2A>.</span></span> <span data-ttu-id="ec61b-114"><xref:System.Windows.Forms.CheckBox.Checked%2A>属性返回`true`或`false`。</span><span class="sxs-lookup"><span data-stu-id="ec61b-114">The <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns either `true` or `false`.</span></span> <span data-ttu-id="ec61b-115"><xref:System.Windows.Forms.CheckBox.CheckState%2A>属性返回<xref:System.Windows.Forms.CheckState.Checked>或<xref:System.Windows.Forms.CheckState.Unchecked>; 或者，如果<xref:System.Windows.Forms.CheckBox.ThreeState%2A>属性设置为`true`，<xref:System.Windows.Forms.CheckBox.CheckState%2A>也可能返回<xref:System.Windows.Forms.CheckState.Indeterminate>。</span><span class="sxs-lookup"><span data-stu-id="ec61b-115">The <xref:System.Windows.Forms.CheckBox.CheckState%2A> property returns either <xref:System.Windows.Forms.CheckState.Checked> or <xref:System.Windows.Forms.CheckState.Unchecked>; or, if the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> may also return <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span> <span data-ttu-id="ec61b-116">在不确定状态下，框中将显示为灰色的外观，以指示选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="ec61b-116">In the indeterminate state, the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec61b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec61b-117">See also</span></span>
- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="ec61b-118">如何：使用 Windows 窗体 CheckBox 控件设置选项</span><span class="sxs-lookup"><span data-stu-id="ec61b-118">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="ec61b-119">如何：响应 Windows 窗体 CheckBox 控件单击</span><span class="sxs-lookup"><span data-stu-id="ec61b-119">How to: Respond to Windows Forms CheckBox Clicks</span></span>](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [<span data-ttu-id="ec61b-120">CheckBox 控件</span><span class="sxs-lookup"><span data-stu-id="ec61b-120">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
