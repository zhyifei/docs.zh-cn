---
title: CheckBox 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
ms.openlocfilehash: b42816cf1bc0ce1ab6db0a2a436b17b0d4370d59
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737091"
---
# <a name="checkbox-control-overview-windows-forms"></a><span data-ttu-id="b17d9-102">CheckBox 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b17d9-102">CheckBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="b17d9-103">Windows Forms <xref:System.Windows.Forms.CheckBox> 컨트롤은 특정 조건이 설정 또는 해제되었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b17d9-103">The Windows Forms <xref:System.Windows.Forms.CheckBox> control indicates whether a particular condition is on or off.</span></span> <span data-ttu-id="b17d9-104">일반적으로 예/아니요 또는 True/False 선택을 사용자에게 제공하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b17d9-104">It is commonly used to present a Yes/No or True/False selection to the user.</span></span> <span data-ttu-id="b17d9-105">확인란 컨트롤을 그룹으로 사용하여 사용자가 하나 이상 선택할 수 있는 여러 선택 항목을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b17d9-105">You can use check box controls in groups to display multiple choices from which the user can select one or more.</span></span>  
  
 <span data-ttu-id="b17d9-106">复选框控件类似于单选按钮控件，其中每个控件用于指示用户所做的选择。</span><span class="sxs-lookup"><span data-stu-id="b17d9-106">The check box control is similar to the radio button control in that each is used to indicate a selection that is made by the user.</span></span> <span data-ttu-id="b17d9-107">它们的区别在于，一次只能选择一个组中的一个单选按钮。</span><span class="sxs-lookup"><span data-stu-id="b17d9-107">They differ in that only one radio button in a group can be selected at a time.</span></span> <span data-ttu-id="b17d9-108">但对于复选框控件，可能会选择任意数量的复选框。</span><span class="sxs-lookup"><span data-stu-id="b17d9-108">With the check box control, however, any number of check boxes may be selected.</span></span>  
  
 <span data-ttu-id="b17d9-109">可以使用简单的数据绑定将复选框连接到数据库中的元素。</span><span class="sxs-lookup"><span data-stu-id="b17d9-109">A check box may be connected to elements in a database using simple data binding.</span></span> <span data-ttu-id="b17d9-110">可以使用 <xref:System.Windows.Forms.GroupBox> 控件对多个复选框进行分组。</span><span class="sxs-lookup"><span data-stu-id="b17d9-110">Multiple check boxes may be grouped using the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="b17d9-111">这对于视觉外观和用户界面设计都很有用，因为可以在窗体设计器上一起移动分组控件。</span><span class="sxs-lookup"><span data-stu-id="b17d9-111">This is useful for visual appearance and also for user interface design, since grouped controls can be moved around together on the form designer.</span></span> <span data-ttu-id="b17d9-112">有关详细信息，请参阅[Windows 窗体数据绑定](../windows-forms-data-binding.md)和[分组框控件](groupbox-control-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="b17d9-112">For more information, see [Windows Forms Data Binding](../windows-forms-data-binding.md) and [GroupBox Control](groupbox-control-windows-forms.md).</span></span>  
  
 <span data-ttu-id="b17d9-113"><xref:System.Windows.Forms.CheckBox> 控件具有两个重要属性，<xref:System.Windows.Forms.CheckBox.Checked%2A> 和 <xref:System.Windows.Forms.CheckBox.CheckState%2A>。</span><span class="sxs-lookup"><span data-stu-id="b17d9-113">The <xref:System.Windows.Forms.CheckBox> control has two important properties, <xref:System.Windows.Forms.CheckBox.Checked%2A> and <xref:System.Windows.Forms.CheckBox.CheckState%2A>.</span></span> <span data-ttu-id="b17d9-114"><xref:System.Windows.Forms.CheckBox.Checked%2A> 属性返回 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="b17d9-114">The <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns either `true` or `false`.</span></span> <span data-ttu-id="b17d9-115"><xref:System.Windows.Forms.CheckBox.CheckState%2A> 属性返回 <xref:System.Windows.Forms.CheckState.Checked> 或 <xref:System.Windows.Forms.CheckState.Unchecked>;或者，如果 <xref:System.Windows.Forms.CheckBox.ThreeState%2A> 属性设置为 `true`，则 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 也可能返回 <xref:System.Windows.Forms.CheckState.Indeterminate>。</span><span class="sxs-lookup"><span data-stu-id="b17d9-115">The <xref:System.Windows.Forms.CheckBox.CheckState%2A> property returns either <xref:System.Windows.Forms.CheckState.Checked> or <xref:System.Windows.Forms.CheckState.Unchecked>; or, if the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> may also return <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span> <span data-ttu-id="b17d9-116">处于不确定状态时，将显示带有一个灰显外观的框，指示该选项不可用。</span><span class="sxs-lookup"><span data-stu-id="b17d9-116">In the indeterminate state, the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b17d9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b17d9-117">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="b17d9-118">방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="b17d9-118">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="b17d9-119">방법: Windows Forms CheckBox 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="b17d9-119">How to: Respond to Windows Forms CheckBox Clicks</span></span>](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [<span data-ttu-id="b17d9-120">CheckBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="b17d9-120">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
