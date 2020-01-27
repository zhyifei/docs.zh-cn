---
title: 在 TextBox 控件中查看多行
ms.date: 03/30/2017
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
ms.openlocfilehash: 61ea671c1e86fa8254bfc1b043a46f3b7aa6af1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728288"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a><span data-ttu-id="c5b5a-102">如何：在 Windows 窗体 TextBox 控件中查看多个行</span><span class="sxs-lookup"><span data-stu-id="c5b5a-102">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="c5b5a-103">默认情况下，Windows 窗体 <xref:System.Windows.Forms.TextBox> 控件显示单行文本，而不显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-103">By default, the Windows Forms <xref:System.Windows.Forms.TextBox> control displays a single line of text and does not display scroll bars.</span></span> <span data-ttu-id="c5b5a-104">如果文本长度超过可用空间，则仅部分文本可见。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-104">If the text is longer than the available space, only part of the text is visible.</span></span> <span data-ttu-id="c5b5a-105">可以通过将 <xref:System.Windows.Forms.TextBox.Multiline%2A>、<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>和 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 属性设置为相应的值来更改此默认行为。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-105">You can change this default behavior by setting the <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, and <xref:System.Windows.Forms.TextBox.ScrollBars%2A> properties to appropriate values.</span></span>  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a><span data-ttu-id="c5b5a-106">在 TextBox 控件中显示回车符</span><span class="sxs-lookup"><span data-stu-id="c5b5a-106">To display a carriage return in the TextBox control</span></span>  
  
- <span data-ttu-id="c5b5a-107">若要在多行 <xref:System.Windows.Forms.TextBox>中显示回车符，请使用 <xref:System.Environment.NewLine%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-107">To display a carriage return in a multi-line <xref:System.Windows.Forms.TextBox>, use the <xref:System.Environment.NewLine%2A> property.</span></span>  
  
     <span data-ttu-id="c5b5a-108">请注意，转义符（\\）的解释是特定于语言的。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-108">Be aware that the interpretation of escape characters (\\) is language-specific.</span></span> <span data-ttu-id="c5b5a-109">Visual Basic 使用 `Chr$(13) & Chr$(10)` 的回车符和换行符组合。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-109">Visual Basic uses `Chr$(13) & Chr$(10)` for the carriage return and linefeed character combination.</span></span>  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a><span data-ttu-id="c5b5a-110">在 TextBox 控件中查看多行</span><span class="sxs-lookup"><span data-stu-id="c5b5a-110">To view multiple lines in the TextBox control</span></span>  
  
1. <span data-ttu-id="c5b5a-111">将 <xref:System.Windows.Forms.TextBox.Multiline%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-111">Set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="c5b5a-112">如果 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> `true` （默认值），则控件中的文本将显示为一个或多个段落;否则，它将显示为一个列表，在此列表中，可能会在控件的边缘剪裁一些行。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-112">If <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> is `true` (the default), then the text in the control will appear as one or more paragraphs; otherwise it will appear as a list, in which some lines may be clipped at the edge of the control.</span></span>  
  
2. <span data-ttu-id="c5b5a-113">将 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-113">Set the <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="c5b5a-114">{2&gt;值&lt;2}</span><span class="sxs-lookup"><span data-stu-id="c5b5a-114">Value</span></span>|<span data-ttu-id="c5b5a-115">描述</span><span class="sxs-lookup"><span data-stu-id="c5b5a-115">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|<span data-ttu-id="c5b5a-116">如果文本将是几乎始终适合控件的段落，请使用此值。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-116">Use this value if the text will be a paragraph that almost always fits the control.</span></span> <span data-ttu-id="c5b5a-117">如果文本太长而无法同时显示，用户可以使用鼠标指针在控件内移动。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-117">The user can use the mouse pointer to move around inside the control if the text is too long to display all at once.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|<span data-ttu-id="c5b5a-118">如果要显示行列表，则使用此值，其中某些行的长度可能大于 <xref:System.Windows.Forms.TextBox> 控件的宽度。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-118">Use this value if you want to display a list of lines, some of which may be longer than the width of the <xref:System.Windows.Forms.TextBox> control.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|<span data-ttu-id="c5b5a-119">如果列表的长度可能超过控件的高度，则使用此值。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-119">Use this value if the list may be longer than the height of the control.</span></span>|  
  
3. <span data-ttu-id="c5b5a-120">将 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-120">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="c5b5a-121">{2&gt;值&lt;2}</span><span class="sxs-lookup"><span data-stu-id="c5b5a-121">Value</span></span>|<span data-ttu-id="c5b5a-122">描述</span><span class="sxs-lookup"><span data-stu-id="c5b5a-122">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="c5b5a-123">控件中的文本不会自动换行，因此它将向右滚动，直至到达换行符。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-123">Text in the control will not automatically be wrapped, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="c5b5a-124">如果选择了上面 <xref:System.Windows.Forms.ScrollBars.Horizontal> 滚动条或 <xref:System.Windows.Forms.ScrollBars.Both>，请使用此值。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-124">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Horizontal> scroll bars or <xref:System.Windows.Forms.ScrollBars.Both>, above.</span></span>|  
    |<span data-ttu-id="c5b5a-125">`true`（默认）</span><span class="sxs-lookup"><span data-stu-id="c5b5a-125">`true` (default)</span></span>|<span data-ttu-id="c5b5a-126">不会显示水平滚动条。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-126">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="c5b5a-127">如果选择 <xref:System.Windows.Forms.ScrollBars.Vertical> 滚动条或 <xref:System.Windows.Forms.ScrollBars.None>上方以显示一个或多个段落，请使用此值。</span><span class="sxs-lookup"><span data-stu-id="c5b5a-127">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Vertical> scroll bars or <xref:System.Windows.Forms.ScrollBars.None>, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5b5a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5b5a-128">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="c5b5a-129">TextBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="c5b5a-129">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="c5b5a-130">如何：在 Windows 窗体 TextBox 控件中控制插入点</span><span class="sxs-lookup"><span data-stu-id="c5b5a-130">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="c5b5a-131">如何：使用 Windows 窗体 TextBox 控件创建密码文本框</span><span class="sxs-lookup"><span data-stu-id="c5b5a-131">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="c5b5a-132">如何：创建只读文本框</span><span class="sxs-lookup"><span data-stu-id="c5b5a-132">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="c5b5a-133">如何：在字符串中添加引号</span><span class="sxs-lookup"><span data-stu-id="c5b5a-133">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="c5b5a-134">如何：在 Windows 窗体 TextBox 控件中选择文本</span><span class="sxs-lookup"><span data-stu-id="c5b5a-134">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="c5b5a-135">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="c5b5a-135">TextBox Control</span></span>](textbox-control-windows-forms.md)
