---
title: RichTextBox 컨트롤
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
# <a name="richtextbox-control-windows-forms"></a><span data-ttu-id="ed185-102">RichTextBox 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ed185-102">RichTextBox Control (Windows Forms)</span></span>
<span data-ttu-id="ed185-103">Windows 窗体 `RichTextBox` 控件用于显示、输入和操作格式设置的文本。</span><span class="sxs-lookup"><span data-stu-id="ed185-103">The Windows Forms `RichTextBox` control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="ed185-104">`RichTextBox` 控件执行 <xref:System.Windows.Forms.TextBox> 控件的所有操作，但也可以显示字体、颜色和链接;从文件中加载文本和嵌入图像;撤消和重做编辑操作;和查找指定的字符。</span><span class="sxs-lookup"><span data-stu-id="ed185-104">The `RichTextBox` control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; undo and redo editing operations; and find specified characters.</span></span> <span data-ttu-id="ed185-105">`RichTextBox` 控件通常用于提供文本操作并显示类似于 word 处理应用程序（如 Microsoft Word）的功能。</span><span class="sxs-lookup"><span data-stu-id="ed185-105">The `RichTextBox` control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="ed185-106">与 <xref:System.Windows.Forms.TextBox> 控件一样，`RichTextBox` 控件可以显示滚动条;但与 <xref:System.Windows.Forms.TextBox> 控件不同的是，默认情况下会显示水平滚动条和垂直滚动条，并具有其他滚动条设置。</span><span class="sxs-lookup"><span data-stu-id="ed185-106">Like the <xref:System.Windows.Forms.TextBox> control, the `RichTextBox` control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, it displays both horizontal and vertical scrollbars by default and has additional scrollbar settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ed185-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ed185-107">In This Section</span></span>  
 [<span data-ttu-id="ed185-108">RichTextBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="ed185-108">RichTextBox Control Overview</span></span>](richtextbox-control-overview-windows-forms.md)  
 <span data-ttu-id="ed185-109">介绍 `RichTextBox` 控件的一般概念，该控件允许用户输入、显示和操作具有格式设置选项的文本。</span><span class="sxs-lookup"><span data-stu-id="ed185-109">Introduces the general concepts of the `RichTextBox` control, which allows users to enter, display, and manipulate text with formatting options.</span></span>  
  
 [<span data-ttu-id="ed185-110">방법: Windows Forms RichTextBox 컨트롤에서 서식 특성의 변경 시기 결정</span><span class="sxs-lookup"><span data-stu-id="ed185-110">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>](determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 <span data-ttu-id="ed185-111">说明如何跟踪 `RichTextBox` 控件中的字体和段落格式更改。</span><span class="sxs-lookup"><span data-stu-id="ed185-111">Explains how to keep track of changes in font and paragraph formatting in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="ed185-112">방법: Windows Forms RichTextBox 컨트롤에서 스크롤 막대 표시</span><span class="sxs-lookup"><span data-stu-id="ed185-112">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>](how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="ed185-113">描述可用于 `RichTextBox` 控件中的滚动条的多种选项。</span><span class="sxs-lookup"><span data-stu-id="ed185-113">Describes the many choices available for scroll bars in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="ed185-114">방법: Windows Forms RichTextBox 컨트롤을 사용하여 웹 스타일 링크 표시</span><span class="sxs-lookup"><span data-stu-id="ed185-114">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="ed185-115">说明如何从 `RichTextBox` 控件链接到网站。</span><span class="sxs-lookup"><span data-stu-id="ed185-115">Explains how to link to Web sites from the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="ed185-116">방법: Windows Forms RichTextBox 컨트롤에서 끌어서 놓기 작업 사용</span><span class="sxs-lookup"><span data-stu-id="ed185-116">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>](enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 <span data-ttu-id="ed185-117">提供有关将数据拖动到 `RichTextBox` 控件中的说明。</span><span class="sxs-lookup"><span data-stu-id="ed185-117">Provides instructions for dragging data into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="ed185-118">방법: Windows Forms RichTextBox 컨트롤에 파일 로드</span><span class="sxs-lookup"><span data-stu-id="ed185-118">How to: Load Files into the Windows Forms RichTextBox Control</span></span>](how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="ed185-119">提供有关将现有文件加载到 `RichTextBox` 控件中的说明。</span><span class="sxs-lookup"><span data-stu-id="ed185-119">Provides instructions for loading an existing file into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="ed185-120">방법: Windows Forms RichTextBox 컨트롤을 사용하여 파일 저장</span><span class="sxs-lookup"><span data-stu-id="ed185-120">How to: Save Files with the Windows Forms RichTextBox Control</span></span>](how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="ed185-121">提供有关将 `RichTextBox` 控件的内容保存到文件中的说明。</span><span class="sxs-lookup"><span data-stu-id="ed185-121">Provides instructions for saving the contents of the `RichTextBox` control to a file.</span></span>  
  
 [<span data-ttu-id="ed185-122">방법: Windows Forms RichTextBox 컨트롤의 글꼴 특성 설정</span><span class="sxs-lookup"><span data-stu-id="ed185-122">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="ed185-123">描述如何设置 `RichTextBox` 控件中文本的字体系列、字号、样式和颜色。</span><span class="sxs-lookup"><span data-stu-id="ed185-123">Describes how to set the font family, size, style, and color of text in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="ed185-124">방법: Windows Forms RichTextBox 컨트롤을 사용하여 들여쓰기, 내어쓰기 및 글머리 기호 단락 설정</span><span class="sxs-lookup"><span data-stu-id="ed185-124">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 <span data-ttu-id="ed185-125">介绍如何设置 `RichTextBox` 控件中的段落格式。</span><span class="sxs-lookup"><span data-stu-id="ed185-125">Describes how to format paragraphs in the `RichTextBox` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ed185-126">참조</span><span class="sxs-lookup"><span data-stu-id="ed185-126">Reference</span></span>  
 <span data-ttu-id="ed185-127"><xref:System.Windows.Forms.RichTextBox> 클래스</span><span class="sxs-lookup"><span data-stu-id="ed185-127"><xref:System.Windows.Forms.RichTextBox> class</span></span>  
 <span data-ttu-id="ed185-128">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ed185-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ed185-129">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="ed185-129">Related Sections</span></span>  
 [<span data-ttu-id="ed185-130">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ed185-130">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="ed185-131">사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ed185-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="ed185-132">TextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ed185-132">TextBox Control</span></span>](textbox-control-windows-forms.md)  
 <span data-ttu-id="ed185-133">介绍 <xref:System.Windows.Forms.TextBox> 控件的一般概念，该控件允许用户的可编辑多行输入。</span><span class="sxs-lookup"><span data-stu-id="ed185-133">Introduces the general concepts of the <xref:System.Windows.Forms.TextBox> control, which allows editable, multiline input from the user.</span></span>
