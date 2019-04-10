---
title: 如何：在 Windows 窗体 TextBox 控件中查看多个行
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
ms.openlocfilehash: f7a0e3a14d14f0629bd9995dbecd3f0b98bea1d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190907"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a><span data-ttu-id="7018b-102">如何：在 Windows 窗体 TextBox 控件中查看多个行</span><span class="sxs-lookup"><span data-stu-id="7018b-102">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="7018b-103">默认情况下，Windows 窗体<xref:System.Windows.Forms.TextBox>控件显示单行文本并不会显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="7018b-103">By default, the Windows Forms <xref:System.Windows.Forms.TextBox> control displays a single line of text and does not display scroll bars.</span></span> <span data-ttu-id="7018b-104">文本的长度超过可用空间，仅部分文本可见。</span><span class="sxs-lookup"><span data-stu-id="7018b-104">If the text is longer than the available space, only part of the text is visible.</span></span> <span data-ttu-id="7018b-105">可以通过设置更改此默认行为<xref:System.Windows.Forms.TextBox.Multiline%2A>， <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>，和<xref:System.Windows.Forms.TextBox.ScrollBars%2A>为适当的值的属性。</span><span class="sxs-lookup"><span data-stu-id="7018b-105">You can change this default behavior by setting the <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, and <xref:System.Windows.Forms.TextBox.ScrollBars%2A> properties to appropriate values.</span></span>  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a><span data-ttu-id="7018b-106">若要显示在 TextBox 控件中返回一个回车符</span><span class="sxs-lookup"><span data-stu-id="7018b-106">To display a carriage return in the TextBox control</span></span>  
  
-   <span data-ttu-id="7018b-107">若要显示多行的回车<xref:System.Windows.Forms.TextBox>，使用<xref:System.Environment.NewLine%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7018b-107">To display a carriage return in a multi-line <xref:System.Windows.Forms.TextBox>, use the <xref:System.Environment.NewLine%2A> property.</span></span>  
  
     <span data-ttu-id="7018b-108">请注意，解释转义符 (\\) 是特定于语言的。</span><span class="sxs-lookup"><span data-stu-id="7018b-108">Be aware that the interpretation of escape characters (\\) is language-specific.</span></span> <span data-ttu-id="7018b-109">Visual Basic 则使用`Chr$(13) & Chr$(10)`为回车符和换行符字符组合。</span><span class="sxs-lookup"><span data-stu-id="7018b-109">Visual Basic uses `Chr$(13) & Chr$(10)` for the carriage return and linefeed character combination.</span></span>  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a><span data-ttu-id="7018b-110">若要查看 TextBox 控件中的多个行</span><span class="sxs-lookup"><span data-stu-id="7018b-110">To view multiple lines in the TextBox control</span></span>  
  
1.  <span data-ttu-id="7018b-111">将 <xref:System.Windows.Forms.TextBox.Multiline%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="7018b-111">Set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="7018b-112">如果<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>是`true`（默认值），然后在控件中的文本将显示为一个或多个段落; 否则它将显示为列表中，某些行可能会剪裁在控件的边缘。</span><span class="sxs-lookup"><span data-stu-id="7018b-112">If <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> is `true` (the default), then the text in the control will appear as one or more paragraphs; otherwise it will appear as a list, in which some lines may be clipped at the edge of the control.</span></span>  
  
2.  <span data-ttu-id="7018b-113">将 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="7018b-113">Set the <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="7018b-114">“值”</span><span class="sxs-lookup"><span data-stu-id="7018b-114">Value</span></span>|<span data-ttu-id="7018b-115">描述</span><span class="sxs-lookup"><span data-stu-id="7018b-115">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|<span data-ttu-id="7018b-116">使用此值，如果该文本则为一个段落，几乎总是能适合控件。</span><span class="sxs-lookup"><span data-stu-id="7018b-116">Use this value if the text will be a paragraph that almost always fits the control.</span></span> <span data-ttu-id="7018b-117">用户可以使用鼠标指针在控件内移动，如果文本太长而无法一次性全部显示。</span><span class="sxs-lookup"><span data-stu-id="7018b-117">The user can use the mouse pointer to move around inside the control if the text is too long to display all at once.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|<span data-ttu-id="7018b-118">如果你想要显示的行，其中一些可能会比的宽度更长列表，请使用此值<xref:System.Windows.Forms.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="7018b-118">Use this value if you want to display a list of lines, some of which may be longer than the width of the <xref:System.Windows.Forms.TextBox> control.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|<span data-ttu-id="7018b-119">如果该列表可能会超过控件的高度，则使用此值。</span><span class="sxs-lookup"><span data-stu-id="7018b-119">Use this value if the list may be longer than the height of the control.</span></span>|  
  
3.  <span data-ttu-id="7018b-120">将 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="7018b-120">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="7018b-121">“值”</span><span class="sxs-lookup"><span data-stu-id="7018b-121">Value</span></span>|<span data-ttu-id="7018b-122">描述</span><span class="sxs-lookup"><span data-stu-id="7018b-122">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="7018b-123">控件中的文本不会自动换行，所以它将滚动到右侧，直到到达一个分行符。</span><span class="sxs-lookup"><span data-stu-id="7018b-123">Text in the control will not automatically be wrapped, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="7018b-124">使用此值，如果你选择了<xref:System.Windows.Forms.ScrollBars.Horizontal>滚动条或<xref:System.Windows.Forms.ScrollBars.Both>、 更高版本。</span><span class="sxs-lookup"><span data-stu-id="7018b-124">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Horizontal> scroll bars or <xref:System.Windows.Forms.ScrollBars.Both>, above.</span></span>|  
    |`true` <span data-ttu-id="7018b-125">（默认）</span><span class="sxs-lookup"><span data-stu-id="7018b-125">(default)</span></span>|<span data-ttu-id="7018b-126">不会出现水平滚动条。</span><span class="sxs-lookup"><span data-stu-id="7018b-126">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="7018b-127">使用此值，如果你选择了<xref:System.Windows.Forms.ScrollBars.Vertical>滚动条或<xref:System.Windows.Forms.ScrollBars.None>、 更高版本来显示一个或多个段落。</span><span class="sxs-lookup"><span data-stu-id="7018b-127">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Vertical> scroll bars or <xref:System.Windows.Forms.ScrollBars.None>, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7018b-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="7018b-128">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="7018b-129">TextBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="7018b-129">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="7018b-130">如何：控制 Windows 窗体 TextBox 控件中的插入点</span><span class="sxs-lookup"><span data-stu-id="7018b-130">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="7018b-131">如何：使用 Windows 窗体 TextBox 控件创建密码文本框</span><span class="sxs-lookup"><span data-stu-id="7018b-131">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="7018b-132">如何：创建只读文本框</span><span class="sxs-lookup"><span data-stu-id="7018b-132">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="7018b-133">如何：在字符串中添加引号</span><span class="sxs-lookup"><span data-stu-id="7018b-133">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="7018b-134">如何：在 Windows 窗体 TextBox 控件中选择文本</span><span class="sxs-lookup"><span data-stu-id="7018b-134">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="7018b-135">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="7018b-135">TextBox Control</span></span>](textbox-control-windows-forms.md)
