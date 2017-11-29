---
title: "如何：在 Windows 窗体 RichTextBox 控件中显示滚动条"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3b20c526b27eb185bf79eaf0ace47e5a9fded42a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="832a4-102">如何：在 Windows 窗体 RichTextBox 控件中显示滚动条</span><span class="sxs-lookup"><span data-stu-id="832a4-102">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="832a4-103">默认情况下，Windows 窗体<xref:System.Windows.Forms.RichTextBox>控件根据需要显示水平和垂直滚动条。</span><span class="sxs-lookup"><span data-stu-id="832a4-103">By default, the Windows Forms <xref:System.Windows.Forms.RichTextBox> control displays horizontal and vertical scroll bars as necessary.</span></span> <span data-ttu-id="832a4-104">有七个可能值<xref:System.Windows.Forms.RichTextBox.ScrollBars%2A>属性<xref:System.Windows.Forms.RichTextBox>控件下, 表所述。</span><span class="sxs-lookup"><span data-stu-id="832a4-104">There are seven possible values for the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property of the <xref:System.Windows.Forms.RichTextBox> control, which are described in the table below.</span></span>  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a><span data-ttu-id="832a4-105">在 RichTextBox 控件中显示滚动条</span><span class="sxs-lookup"><span data-stu-id="832a4-105">To display scroll bars in a RichTextBox control</span></span>  
  
1.  <span data-ttu-id="832a4-106">将 <xref:System.Windows.Forms.RichTextBox.Multiline%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="832a4-106">Set the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="832a4-107">如果没有任何类型的滚动条，包括水平，将显示<xref:System.Windows.Forms.RichTextBox.Multiline%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="832a4-107">No type of scroll bar, including horizontal, will display if the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property is set to `false`.</span></span>  
  
2.  <span data-ttu-id="832a4-108">设置<xref:System.Windows.Forms.RichTextBox.ScrollBars%2A>为适当的值的属性<xref:System.Windows.Forms.RichTextBoxScrollBars>枚举。</span><span class="sxs-lookup"><span data-stu-id="832a4-108">Set the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property to an appropriate value of the <xref:System.Windows.Forms.RichTextBoxScrollBars> enumeration.</span></span>  
  
    |<span data-ttu-id="832a4-109">值</span><span class="sxs-lookup"><span data-stu-id="832a4-109">Value</span></span>|<span data-ttu-id="832a4-110">描述</span><span class="sxs-lookup"><span data-stu-id="832a4-110">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="832a4-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both>（默认值）</span><span class="sxs-lookup"><span data-stu-id="832a4-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (default)</span></span>|<span data-ttu-id="832a4-112">水平或垂直滚动条，或两个，仅当显示的文本超出宽度或的控件长度。</span><span class="sxs-lookup"><span data-stu-id="832a4-112">Displays horizontal or vertical scroll bars, or both, only when text exceeds the width or length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|<span data-ttu-id="832a4-113">永远不会显示任何类型的滚动条。</span><span class="sxs-lookup"><span data-stu-id="832a4-113">Never displays any type of scroll bar.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|<span data-ttu-id="832a4-114">显示水平滚动条仅当文本超过控件的宽度。</span><span class="sxs-lookup"><span data-stu-id="832a4-114">Displays a horizontal scroll bar only when the text exceeds the width of the control.</span></span> <span data-ttu-id="832a4-115">(若要执行，此<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>属性必须设置为`false`。)</span><span class="sxs-lookup"><span data-stu-id="832a4-115">(For this to occur, the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property must be set to `false`.)</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|<span data-ttu-id="832a4-116">显示一个垂直滚动条仅当文本超过控件的高度。</span><span class="sxs-lookup"><span data-stu-id="832a4-116">Displays a vertical scroll bar only when the text exceeds the height of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|<span data-ttu-id="832a4-117">显示水平滚动条时<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="832a4-117">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="832a4-118">在文本未超过控件的宽度时，滚动条显示为灰色。</span><span class="sxs-lookup"><span data-stu-id="832a4-118">The scroll bar appears dimmed when text does not exceed the width of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|<span data-ttu-id="832a4-119">始终显示垂直滚动条。</span><span class="sxs-lookup"><span data-stu-id="832a4-119">Always displays a vertical scroll bar.</span></span> <span data-ttu-id="832a4-120">在文本未超过的控件长度时，滚动条显示为灰色。</span><span class="sxs-lookup"><span data-stu-id="832a4-120">The scroll bar appears dimmed when text does not exceed the length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|<span data-ttu-id="832a4-121">始终显示垂直滚动条。</span><span class="sxs-lookup"><span data-stu-id="832a4-121">Always displays a vertical scrollbar.</span></span> <span data-ttu-id="832a4-122">显示水平滚动条时<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="832a4-122">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="832a4-123">滚动条显示为灰色，宽度或的控件长度不超过文本时。</span><span class="sxs-lookup"><span data-stu-id="832a4-123">The scroll bars appear grayed when text does not exceed the width or length of the control.</span></span>|  
  
3.  <span data-ttu-id="832a4-124">将 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="832a4-124">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="832a4-125">值</span><span class="sxs-lookup"><span data-stu-id="832a4-125">Value</span></span>|<span data-ttu-id="832a4-126">描述</span><span class="sxs-lookup"><span data-stu-id="832a4-126">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="832a4-127">控件中的文本不自动调整以适应该控件的宽度，所以它将向右滚动，直到到达一个分行符。</span><span class="sxs-lookup"><span data-stu-id="832a4-127">Text in the control is not automatically adjusted to fit the width of the control, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="832a4-128">如果您在上面选择和 / 或水平滚动条，请使用此值。</span><span class="sxs-lookup"><span data-stu-id="832a4-128">Use this value if you chose horizontal scroll bars or both, above.</span></span>|  
    |<span data-ttu-id="832a4-129">`true`（默认值）</span><span class="sxs-lookup"><span data-stu-id="832a4-129">`true` (default)</span></span>|<span data-ttu-id="832a4-130">控件中的文本自动调整以适应控件的宽度。</span><span class="sxs-lookup"><span data-stu-id="832a4-130">Text in the control is automatically adjusted to fit the width of the control.</span></span> <span data-ttu-id="832a4-131">水平滚动条将不会出现。</span><span class="sxs-lookup"><span data-stu-id="832a4-131">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="832a4-132">如果选择垂直滚动条或无、 更高版本，以显示一个或多个段落，请使用此值。</span><span class="sxs-lookup"><span data-stu-id="832a4-132">Use this value if you chose vertical scroll bars or none, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="832a4-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="832a4-133">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBoxScrollBars>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="832a4-134">RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="832a4-134">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="832a4-135">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="832a4-135">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
