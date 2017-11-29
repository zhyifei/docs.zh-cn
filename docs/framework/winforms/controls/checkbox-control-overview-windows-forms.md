---
title: "CheckBox 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a154a3f639102e3f3e2acd62626379e12bbd1344
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="checkbox-control-overview-windows-forms"></a><span data-ttu-id="30afe-102">CheckBox 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="30afe-102">CheckBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="30afe-103">Windows 窗体 <xref:System.Windows.Forms.CheckBox> 控件指示特定条件处于打开开始关闭状态。</span><span class="sxs-lookup"><span data-stu-id="30afe-103">The Windows Forms <xref:System.Windows.Forms.CheckBox> control indicates whether a particular condition is on or off.</span></span> <span data-ttu-id="30afe-104">通常用于向用户显示 Yes/No 或 True/False 选项。</span><span class="sxs-lookup"><span data-stu-id="30afe-104">It is commonly used to present a Yes/No or True/False selection to the user.</span></span> <span data-ttu-id="30afe-105">可以使用组中的复选框控件来显示用户可从中选择一个或多选的多个选项。</span><span class="sxs-lookup"><span data-stu-id="30afe-105">You can use check box controls in groups to display multiple choices from which the user can select one or more.</span></span>  
  
 <span data-ttu-id="30afe-106">复选框控件的类似于单选按钮控件，在于每个用于指示用户所做的选择。</span><span class="sxs-lookup"><span data-stu-id="30afe-106">The check box control is similar to the radio button control in that each is used to indicate a selection that is made by the user.</span></span> <span data-ttu-id="30afe-107">它们与组中的只有一个单选按钮在一次，可以选择的。</span><span class="sxs-lookup"><span data-stu-id="30afe-107">They differ in that only one radio button in a group can be selected at a time.</span></span> <span data-ttu-id="30afe-108">使用复选框控件，但是，任意数量的复选框可以选择。</span><span class="sxs-lookup"><span data-stu-id="30afe-108">With the check box control, however, any number of check boxes may be selected.</span></span>  
  
 <span data-ttu-id="30afe-109">复选框可能连接到数据库使用简单数据绑定中的元素。</span><span class="sxs-lookup"><span data-stu-id="30afe-109">A check box may be connected to elements in a database using simple data binding.</span></span> <span data-ttu-id="30afe-110">可使用组合多个复选框<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="30afe-110">Multiple check boxes may be grouped using the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="30afe-111">这很有用的可视外观以及用户界面设计的因为分组的控件可以一起移动窗体设计器上。</span><span class="sxs-lookup"><span data-stu-id="30afe-111">This is useful for visual appearance and also for user interface design, since grouped controls can be moved around together on the form designer.</span></span> <span data-ttu-id="30afe-112">有关详细信息，请参阅[Windows 窗体数据绑定](../../../../docs/framework/winforms/windows-forms-data-binding.md)和[GroupBox 控件](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="30afe-112">For more information, see [Windows Forms Data Binding](../../../../docs/framework/winforms/windows-forms-data-binding.md) and [GroupBox Control](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).</span></span>  
  
 <span data-ttu-id="30afe-113"><xref:System.Windows.Forms.CheckBox>控件具有两个重要属性，<xref:System.Windows.Forms.CheckBox.Checked%2A>和<xref:System.Windows.Forms.CheckBox.CheckState%2A>。</span><span class="sxs-lookup"><span data-stu-id="30afe-113">The <xref:System.Windows.Forms.CheckBox> control has two important properties, <xref:System.Windows.Forms.CheckBox.Checked%2A> and <xref:System.Windows.Forms.CheckBox.CheckState%2A>.</span></span> <span data-ttu-id="30afe-114"><xref:System.Windows.Forms.CheckBox.Checked%2A>属性返回`true`或`false`。</span><span class="sxs-lookup"><span data-stu-id="30afe-114">The <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns either `true` or `false`.</span></span> <span data-ttu-id="30afe-115"><xref:System.Windows.Forms.CheckBox.CheckState%2A>属性返回<xref:System.Windows.Forms.CheckState.Checked>或<xref:System.Windows.Forms.CheckState.Unchecked>; 或者，如果<xref:System.Windows.Forms.CheckBox.ThreeState%2A>属性设置为`true`，<xref:System.Windows.Forms.CheckBox.CheckState%2A>也可能返回<xref:System.Windows.Forms.CheckState.Indeterminate>。</span><span class="sxs-lookup"><span data-stu-id="30afe-115">The <xref:System.Windows.Forms.CheckBox.CheckState%2A> property returns either <xref:System.Windows.Forms.CheckState.Checked> or <xref:System.Windows.Forms.CheckState.Unchecked>; or, if the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> may also return <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span> <span data-ttu-id="30afe-116">在不确定状态下，将显示带有框灰显的外观，以指示选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="30afe-116">In the indeterminate state, the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30afe-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30afe-117">See Also</span></span>  
 <xref:System.Windows.Forms.CheckBox>  
 [<span data-ttu-id="30afe-118">如何：使用 Windows 窗体 CheckBox 控件设置选项</span><span class="sxs-lookup"><span data-stu-id="30afe-118">How to: Set Options with Windows Forms CheckBox Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [<span data-ttu-id="30afe-119">如何：响应 Windows 窗体 CheckBox 控件单击</span><span class="sxs-lookup"><span data-stu-id="30afe-119">How to: Respond to Windows Forms CheckBox Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [<span data-ttu-id="30afe-120">CheckBox 控件</span><span class="sxs-lookup"><span data-stu-id="30afe-120">CheckBox Control</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
