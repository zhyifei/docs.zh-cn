---
title: 在 RichTextBox 控件中显示滚动条
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 2185b572ef20765043d3df3dbfd8bf5b21cfac28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745562"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="713d2-102">如何：在 Windows 窗体 RichTextBox 控件中显示滚动条</span><span class="sxs-lookup"><span data-stu-id="713d2-102">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="713d2-103">默认情况下，Windows 窗体 <xref:System.Windows.Forms.RichTextBox> 控件在需要时显示水平滚动条和垂直滚动条。</span><span class="sxs-lookup"><span data-stu-id="713d2-103">By default, the Windows Forms <xref:System.Windows.Forms.RichTextBox> control displays horizontal and vertical scroll bars as necessary.</span></span> <span data-ttu-id="713d2-104"><xref:System.Windows.Forms.RichTextBox> 控件的 <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> 属性有七个可能的值，如下表中所述。</span><span class="sxs-lookup"><span data-stu-id="713d2-104">There are seven possible values for the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property of the <xref:System.Windows.Forms.RichTextBox> control, which are described in the table below.</span></span>  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a><span data-ttu-id="713d2-105">在 RichTextBox 控件中显示滚动条</span><span class="sxs-lookup"><span data-stu-id="713d2-105">To display scroll bars in a RichTextBox control</span></span>  
  
1. <span data-ttu-id="713d2-106">将 <xref:System.Windows.Forms.RichTextBox.Multiline%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="713d2-106">Set the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="713d2-107">如果 <xref:System.Windows.Forms.RichTextBox.Multiline%2A> 属性设置为 `false`，则不会显示任何类型的滚动条（包括水平滚动条）。</span><span class="sxs-lookup"><span data-stu-id="713d2-107">No type of scroll bar, including horizontal, will display if the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property is set to `false`.</span></span>  
  
2. <span data-ttu-id="713d2-108">将 <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> 属性设置为 <xref:System.Windows.Forms.RichTextBoxScrollBars> 枚举的适当值。</span><span class="sxs-lookup"><span data-stu-id="713d2-108">Set the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property to an appropriate value of the <xref:System.Windows.Forms.RichTextBoxScrollBars> enumeration.</span></span>  
  
    |<span data-ttu-id="713d2-109">值</span><span class="sxs-lookup"><span data-stu-id="713d2-109">Value</span></span>|<span data-ttu-id="713d2-110">说明</span><span class="sxs-lookup"><span data-stu-id="713d2-110">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="713d2-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both>（默认值）</span><span class="sxs-lookup"><span data-stu-id="713d2-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (default)</span></span>|<span data-ttu-id="713d2-112">仅当文本超过控件的宽度或长度时，显示水平或垂直滚动条，或同时显示两者。</span><span class="sxs-lookup"><span data-stu-id="713d2-112">Displays horizontal or vertical scroll bars, or both, only when text exceeds the width or length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|<span data-ttu-id="713d2-113">永远不会显示任何类型的滚动条。</span><span class="sxs-lookup"><span data-stu-id="713d2-113">Never displays any type of scroll bar.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|<span data-ttu-id="713d2-114">仅当文本超过控件的宽度时，才显示水平滚动条。</span><span class="sxs-lookup"><span data-stu-id="713d2-114">Displays a horizontal scroll bar only when the text exceeds the width of the control.</span></span> <span data-ttu-id="713d2-115">（为此，必须将 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 属性设置为 `false`。）</span><span class="sxs-lookup"><span data-stu-id="713d2-115">(For this to occur, the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property must be set to `false`.)</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|<span data-ttu-id="713d2-116">仅当文本超过控件的高度时显示垂直滚动条。</span><span class="sxs-lookup"><span data-stu-id="713d2-116">Displays a vertical scroll bar only when the text exceeds the height of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|<span data-ttu-id="713d2-117">当 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 属性设置为 `false`时，将显示水平滚动条。</span><span class="sxs-lookup"><span data-stu-id="713d2-117">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="713d2-118">当文本不超过控件的宽度时，滚动条将灰显。</span><span class="sxs-lookup"><span data-stu-id="713d2-118">The scroll bar appears dimmed when text does not exceed the width of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|<span data-ttu-id="713d2-119">始终显示垂直滚动条。</span><span class="sxs-lookup"><span data-stu-id="713d2-119">Always displays a vertical scroll bar.</span></span> <span data-ttu-id="713d2-120">当文本不超过控件的长度时，滚动条将灰显。</span><span class="sxs-lookup"><span data-stu-id="713d2-120">The scroll bar appears dimmed when text does not exceed the length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|<span data-ttu-id="713d2-121">始终显示垂直滚动条。</span><span class="sxs-lookup"><span data-stu-id="713d2-121">Always displays a vertical scrollbar.</span></span> <span data-ttu-id="713d2-122">当 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 属性设置为 `false`时，将显示水平滚动条。</span><span class="sxs-lookup"><span data-stu-id="713d2-122">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="713d2-123">当文本不超过控件的宽度或长度时，滚动条显示为灰色。</span><span class="sxs-lookup"><span data-stu-id="713d2-123">The scroll bars appear grayed when text does not exceed the width or length of the control.</span></span>|  
  
3. <span data-ttu-id="713d2-124">将 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="713d2-124">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="713d2-125">值</span><span class="sxs-lookup"><span data-stu-id="713d2-125">Value</span></span>|<span data-ttu-id="713d2-126">说明</span><span class="sxs-lookup"><span data-stu-id="713d2-126">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="713d2-127">控件中的文本不会自动调整以适应控件的宽度，因此它将向右滚动，直至到达换行符。</span><span class="sxs-lookup"><span data-stu-id="713d2-127">Text in the control is not automatically adjusted to fit the width of the control, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="713d2-128">如果选择了 "水平滚动条" 或以上两者，请使用此值。</span><span class="sxs-lookup"><span data-stu-id="713d2-128">Use this value if you chose horizontal scroll bars or both, above.</span></span>|  
    |<span data-ttu-id="713d2-129">`true`（默认值）</span><span class="sxs-lookup"><span data-stu-id="713d2-129">`true` (default)</span></span>|<span data-ttu-id="713d2-130">控件中的文本会自动调整以适应控件的宽度。</span><span class="sxs-lookup"><span data-stu-id="713d2-130">Text in the control is automatically adjusted to fit the width of the control.</span></span> <span data-ttu-id="713d2-131">不会显示水平滚动条。</span><span class="sxs-lookup"><span data-stu-id="713d2-131">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="713d2-132">如果选择了 "垂直滚动条" 或 "无"，则使用此值来显示一个或多个段落。</span><span class="sxs-lookup"><span data-stu-id="713d2-132">Use this value if you chose vertical scroll bars or none, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="713d2-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="713d2-133">See also</span></span>

- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="713d2-134">RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="713d2-134">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="713d2-135">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="713d2-135">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
