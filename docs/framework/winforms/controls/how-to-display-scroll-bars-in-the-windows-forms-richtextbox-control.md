---
title: 如何：在 Windows 窗体 RichTextBox 控件中显示滚动条
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 52c33239524e76bc26b9b2375578aa46bff51bf6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142553"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="f4691-102">如何：在 Windows 窗体 RichTextBox 控件中显示滚动条</span><span class="sxs-lookup"><span data-stu-id="f4691-102">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="f4691-103">默认情况下，Windows 窗体<xref:System.Windows.Forms.RichTextBox>控件在必要时将显示水平和垂直滚动条。</span><span class="sxs-lookup"><span data-stu-id="f4691-103">By default, the Windows Forms <xref:System.Windows.Forms.RichTextBox> control displays horizontal and vertical scroll bars as necessary.</span></span> <span data-ttu-id="f4691-104">有七个可能值为<xref:System.Windows.Forms.RichTextBox.ScrollBars%2A>属性的<xref:System.Windows.Forms.RichTextBox>控件，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="f4691-104">There are seven possible values for the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property of the <xref:System.Windows.Forms.RichTextBox> control, which are described in the table below.</span></span>  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a><span data-ttu-id="f4691-105">若要在 RichTextBox 控件中显示滚动条</span><span class="sxs-lookup"><span data-stu-id="f4691-105">To display scroll bars in a RichTextBox control</span></span>  
  
1.  <span data-ttu-id="f4691-106">将 <xref:System.Windows.Forms.RichTextBox.Multiline%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="f4691-106">Set the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="f4691-107">如果没有任何类型的滚动条，其中包括水平，将显示<xref:System.Windows.Forms.RichTextBox.Multiline%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="f4691-107">No type of scroll bar, including horizontal, will display if the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property is set to `false`.</span></span>  
  
2.  <span data-ttu-id="f4691-108">设置<xref:System.Windows.Forms.RichTextBox.ScrollBars%2A>属性设置为适当的值的<xref:System.Windows.Forms.RichTextBoxScrollBars>枚举。</span><span class="sxs-lookup"><span data-stu-id="f4691-108">Set the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property to an appropriate value of the <xref:System.Windows.Forms.RichTextBoxScrollBars> enumeration.</span></span>  
  
    |<span data-ttu-id="f4691-109">“值”</span><span class="sxs-lookup"><span data-stu-id="f4691-109">Value</span></span>|<span data-ttu-id="f4691-110">描述</span><span class="sxs-lookup"><span data-stu-id="f4691-110">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both> <span data-ttu-id="f4691-111">（默认）</span><span class="sxs-lookup"><span data-stu-id="f4691-111">(default)</span></span>|<span data-ttu-id="f4691-112">仅当文本超出宽度或长度的控件时显示和 / 或水平或垂直滚动条。</span><span class="sxs-lookup"><span data-stu-id="f4691-112">Displays horizontal or vertical scroll bars, or both, only when text exceeds the width or length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|<span data-ttu-id="f4691-113">永远不会显示任何类型的滚动条。</span><span class="sxs-lookup"><span data-stu-id="f4691-113">Never displays any type of scroll bar.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|<span data-ttu-id="f4691-114">显示水平滚动条仅当文本超过控件的宽度。</span><span class="sxs-lookup"><span data-stu-id="f4691-114">Displays a horizontal scroll bar only when the text exceeds the width of the control.</span></span> <span data-ttu-id="f4691-115">(，要实现这个<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>属性必须设置为`false`。)</span><span class="sxs-lookup"><span data-stu-id="f4691-115">(For this to occur, the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property must be set to `false`.)</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|<span data-ttu-id="f4691-116">显示一个垂直滚动条仅当文本超过控件的高度。</span><span class="sxs-lookup"><span data-stu-id="f4691-116">Displays a vertical scroll bar only when the text exceeds the height of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|<span data-ttu-id="f4691-117">显示水平滚动条何时<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="f4691-117">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="f4691-118">在文本未超过控件的宽度时滚动条显示为灰色。</span><span class="sxs-lookup"><span data-stu-id="f4691-118">The scroll bar appears dimmed when text does not exceed the width of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|<span data-ttu-id="f4691-119">始终显示垂直滚动条。</span><span class="sxs-lookup"><span data-stu-id="f4691-119">Always displays a vertical scroll bar.</span></span> <span data-ttu-id="f4691-120">滚动条的文本控件的长度不超过时显示为灰色。</span><span class="sxs-lookup"><span data-stu-id="f4691-120">The scroll bar appears dimmed when text does not exceed the length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|<span data-ttu-id="f4691-121">始终显示垂直滚动条。</span><span class="sxs-lookup"><span data-stu-id="f4691-121">Always displays a vertical scrollbar.</span></span> <span data-ttu-id="f4691-122">显示水平滚动条何时<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="f4691-122">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="f4691-123">文本不超过宽度或长度的控件时，滚动条显示为灰色。</span><span class="sxs-lookup"><span data-stu-id="f4691-123">The scroll bars appear grayed when text does not exceed the width or length of the control.</span></span>|  
  
3.  <span data-ttu-id="f4691-124">将 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="f4691-124">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="f4691-125">“值”</span><span class="sxs-lookup"><span data-stu-id="f4691-125">Value</span></span>|<span data-ttu-id="f4691-126">描述</span><span class="sxs-lookup"><span data-stu-id="f4691-126">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="f4691-127">控件中的文本不会自动调整来适应控件的宽度，所以它将滚动到右侧，直到到达一个分行符。</span><span class="sxs-lookup"><span data-stu-id="f4691-127">Text in the control is not automatically adjusted to fit the width of the control, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="f4691-128">如果您在上面选择和 / 或水平滚动条，请使用此值。</span><span class="sxs-lookup"><span data-stu-id="f4691-128">Use this value if you chose horizontal scroll bars or both, above.</span></span>|  
    |`true` <span data-ttu-id="f4691-129">（默认）</span><span class="sxs-lookup"><span data-stu-id="f4691-129">(default)</span></span>|<span data-ttu-id="f4691-130">控件中的文本自动调整以适应控件的宽度。</span><span class="sxs-lookup"><span data-stu-id="f4691-130">Text in the control is automatically adjusted to fit the width of the control.</span></span> <span data-ttu-id="f4691-131">不会出现水平滚动条。</span><span class="sxs-lookup"><span data-stu-id="f4691-131">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="f4691-132">如果选择了垂直滚动条或无、 更高版本，以显示一个或多个段落，请使用此值。</span><span class="sxs-lookup"><span data-stu-id="f4691-132">Use this value if you chose vertical scroll bars or none, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4691-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4691-133">See also</span></span>

- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="f4691-134">RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="f4691-134">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="f4691-135">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="f4691-135">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
