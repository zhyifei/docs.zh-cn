---
title: RichTextBox 控件
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes
- RichTextBox control [Windows Forms]
- rich edit controls
ms.assetid: 3225f2ef-c6d9-4bd4-9d3e-2219e58edbf2
ms.openlocfilehash: 9d26ec7bfc4d75b304bbc9dc98dbbeaed64effe7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743133"
---
# <a name="richtextbox-control-windows-forms"></a><span data-ttu-id="bbfd9-102">RichTextBox 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="bbfd9-102">RichTextBox Control (Windows Forms)</span></span>
<span data-ttu-id="bbfd9-103">Windows 窗体 `RichTextBox` 控件用于显示、输入和操作格式设置的文本。</span><span class="sxs-lookup"><span data-stu-id="bbfd9-103">The Windows Forms `RichTextBox` control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="bbfd9-104">`RichTextBox` 控件执行 <xref:System.Windows.Forms.TextBox> 控件的所有操作，但也可以显示字体、颜色和链接;从文件中加载文本和嵌入图像;撤消和重做编辑操作;和查找指定的字符。</span><span class="sxs-lookup"><span data-stu-id="bbfd9-104">The `RichTextBox` control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; undo and redo editing operations; and find specified characters.</span></span> <span data-ttu-id="bbfd9-105">`RichTextBox` 控件通常用于提供文本操作并显示类似于 word 处理应用程序（如 Microsoft Word）的功能。</span><span class="sxs-lookup"><span data-stu-id="bbfd9-105">The `RichTextBox` control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="bbfd9-106">与 <xref:System.Windows.Forms.TextBox> 控件一样，`RichTextBox` 控件可以显示滚动条;但与 <xref:System.Windows.Forms.TextBox> 控件不同的是，默认情况下会显示水平滚动条和垂直滚动条，并具有其他滚动条设置。</span><span class="sxs-lookup"><span data-stu-id="bbfd9-106">Like the <xref:System.Windows.Forms.TextBox> control, the `RichTextBox` control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, it displays both horizontal and vertical scrollbars by default and has additional scrollbar settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bbfd9-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="bbfd9-107">In This Section</span></span>  
 [<span data-ttu-id="bbfd9-108">RichTextBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="bbfd9-108">RichTextBox Control Overview</span></span>](richtextbox-control-overview-windows-forms.md)  
 <span data-ttu-id="bbfd9-109">介绍 `RichTextBox` 控件的一般概念，该控件允许用户输入、显示和操作具有格式设置选项的文本。</span><span class="sxs-lookup"><span data-stu-id="bbfd9-109">Introduces the general concepts of the `RichTextBox` control, which allows users to enter, display, and manipulate text with formatting options.</span></span>  
  
 [<span data-ttu-id="bbfd9-110">如何：在 Windows 窗体 RichTextBox 控件中确定格式设置特性何时发生变化</span><span class="sxs-lookup"><span data-stu-id="bbfd9-110">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>](determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 <span data-ttu-id="bbfd9-111">说明如何跟踪 `RichTextBox` 控件中的字体和段落格式更改。</span><span class="sxs-lookup"><span data-stu-id="bbfd9-111">Explains how to keep track of changes in font and paragraph formatting in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="bbfd9-112">如何：在 Windows 窗体 RichTextBox 控件中显示滚动条</span><span class="sxs-lookup"><span data-stu-id="bbfd9-112">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>](how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="bbfd9-113">描述可用于 `RichTextBox` 控件中的滚动条的多种选项。</span><span class="sxs-lookup"><span data-stu-id="bbfd9-113">Describes the many choices available for scroll bars in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="bbfd9-114">如何：使用 Windows 窗体 RichTextBox 控件显示 Web 样式链接</span><span class="sxs-lookup"><span data-stu-id="bbfd9-114">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="bbfd9-115">说明如何从 `RichTextBox` 控件链接到网站。</span><span class="sxs-lookup"><span data-stu-id="bbfd9-115">Explains how to link to Web sites from the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="bbfd9-116">如何：在 Windows 窗体 RichTextBox 控件中启用拖放操作</span><span class="sxs-lookup"><span data-stu-id="bbfd9-116">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>](enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 <span data-ttu-id="bbfd9-117">提供有关将数据拖动到 `RichTextBox` 控件中的说明。</span><span class="sxs-lookup"><span data-stu-id="bbfd9-117">Provides instructions for dragging data into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="bbfd9-118">如何：将文件加载到 Windows 窗体 RichTextBox 控件中</span><span class="sxs-lookup"><span data-stu-id="bbfd9-118">How to: Load Files into the Windows Forms RichTextBox Control</span></span>](how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="bbfd9-119">提供有关将现有文件加载到 `RichTextBox` 控件中的说明。</span><span class="sxs-lookup"><span data-stu-id="bbfd9-119">Provides instructions for loading an existing file into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="bbfd9-120">如何：使用 Windows 窗体 RichTextBox 控件保存文件</span><span class="sxs-lookup"><span data-stu-id="bbfd9-120">How to: Save Files with the Windows Forms RichTextBox Control</span></span>](how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="bbfd9-121">提供有关将 `RichTextBox` 控件的内容保存到文件中的说明。</span><span class="sxs-lookup"><span data-stu-id="bbfd9-121">Provides instructions for saving the contents of the `RichTextBox` control to a file.</span></span>  
  
 [<span data-ttu-id="bbfd9-122">如何：设置 Windows 窗体 RichTextBox 控件的字体特性</span><span class="sxs-lookup"><span data-stu-id="bbfd9-122">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="bbfd9-123">描述如何设置 `RichTextBox` 控件中文本的字体系列、字号、样式和颜色。</span><span class="sxs-lookup"><span data-stu-id="bbfd9-123">Describes how to set the font family, size, style, and color of text in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="bbfd9-124">如何：使用 Windows 窗体 RichTextBox 控件设置缩进、悬挂缩进和点符段落</span><span class="sxs-lookup"><span data-stu-id="bbfd9-124">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 <span data-ttu-id="bbfd9-125">介绍如何设置 `RichTextBox` 控件中的段落格式。</span><span class="sxs-lookup"><span data-stu-id="bbfd9-125">Describes how to format paragraphs in the `RichTextBox` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="bbfd9-126">参考</span><span class="sxs-lookup"><span data-stu-id="bbfd9-126">Reference</span></span>  
 <span data-ttu-id="bbfd9-127"><xref:System.Windows.Forms.RichTextBox> 类</span><span class="sxs-lookup"><span data-stu-id="bbfd9-127"><xref:System.Windows.Forms.RichTextBox> class</span></span>  
 <span data-ttu-id="bbfd9-128">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="bbfd9-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bbfd9-129">相关章节</span><span class="sxs-lookup"><span data-stu-id="bbfd9-129">Related Sections</span></span>  
 [<span data-ttu-id="bbfd9-130">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="bbfd9-130">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="bbfd9-131">提供 Windows 窗体控件的完整列表，附带其使用情况相关信息的链接。</span><span class="sxs-lookup"><span data-stu-id="bbfd9-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="bbfd9-132">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="bbfd9-132">TextBox Control</span></span>](textbox-control-windows-forms.md)  
 <span data-ttu-id="bbfd9-133">介绍 <xref:System.Windows.Forms.TextBox> 控件的一般概念，该控件允许用户的可编辑多行输入。</span><span class="sxs-lookup"><span data-stu-id="bbfd9-133">Introduces the general concepts of the <xref:System.Windows.Forms.TextBox> control, which allows editable, multiline input from the user.</span></span>
