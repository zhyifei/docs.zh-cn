---
title: RichTextBox 控件（Windows 窗体）
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes
- RichTextBox control [Windows Forms]
- rich edit controls
ms.assetid: 3225f2ef-c6d9-4bd4-9d3e-2219e58edbf2
ms.openlocfilehash: 2b1a6604df3979e83e4a815cdb4a9397ab4e67ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012459"
---
# <a name="richtextbox-control-windows-forms"></a><span data-ttu-id="48b2a-102">RichTextBox 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="48b2a-102">RichTextBox Control (Windows Forms)</span></span>
<span data-ttu-id="48b2a-103">Windows 窗体`RichTextBox`控件用于显示、 输入和操作带有格式的文本。</span><span class="sxs-lookup"><span data-stu-id="48b2a-103">The Windows Forms `RichTextBox` control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="48b2a-104">`RichTextBox`控件的功能无所不包<xref:System.Windows.Forms.TextBox>控件的作用，但它还可以显示字体、 颜色和链接; 从文件; 撤消和重做的编辑操作; 加载文本和嵌入的图像并查找指定的字符。</span><span class="sxs-lookup"><span data-stu-id="48b2a-104">The `RichTextBox` control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; undo and redo editing operations; and find specified characters.</span></span> <span data-ttu-id="48b2a-105">`RichTextBox`控件通常用于提供文本操作和显示功能，类似于 Microsoft Word 等文字处理应用程序。</span><span class="sxs-lookup"><span data-stu-id="48b2a-105">The `RichTextBox` control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="48b2a-106">像<xref:System.Windows.Forms.TextBox>控件，`RichTextBox`控件可以显示滚动条; 但不同于<xref:System.Windows.Forms.TextBox>控件，它默认情况下显示水平和垂直滚动条，并具有附加的滚动条设置。</span><span class="sxs-lookup"><span data-stu-id="48b2a-106">Like the <xref:System.Windows.Forms.TextBox> control, the `RichTextBox` control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, it displays both horizontal and vertical scrollbars by default and has additional scrollbar settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="48b2a-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="48b2a-107">In This Section</span></span>  
 [<span data-ttu-id="48b2a-108">RichTextBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="48b2a-108">RichTextBox Control Overview</span></span>](richtextbox-control-overview-windows-forms.md)  
 <span data-ttu-id="48b2a-109">引入了的一般概念`RichTextBox`控件，它允许用户输入、 显示和操作文本格式设置选项。</span><span class="sxs-lookup"><span data-stu-id="48b2a-109">Introduces the general concepts of the `RichTextBox` control, which allows users to enter, display, and manipulate text with formatting options.</span></span>  
  
 [<span data-ttu-id="48b2a-110">如何：确定格式化 Windows 窗体 RichTextBox 控件中的属性更改时</span><span class="sxs-lookup"><span data-stu-id="48b2a-110">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>](determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 <span data-ttu-id="48b2a-111">介绍如何跟踪的字体和段落格式设置中的更改`RichTextBox`控件。</span><span class="sxs-lookup"><span data-stu-id="48b2a-111">Explains how to keep track of changes in font and paragraph formatting in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="48b2a-112">如何：显示滚动条在 Windows 窗体 RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="48b2a-112">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>](how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="48b2a-113">介绍可用于在滚动条的很多选择`RichTextBox`控件。</span><span class="sxs-lookup"><span data-stu-id="48b2a-113">Describes the many choices available for scroll bars in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="48b2a-114">如何：显示 Web 样式链接使用 Windows 窗体 RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="48b2a-114">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="48b2a-115">介绍如何链接到网站从`RichTextBox`控件。</span><span class="sxs-lookup"><span data-stu-id="48b2a-115">Explains how to link to Web sites from the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="48b2a-116">如何：启用使用 Windows 窗体 RichTextBox 控件的拖放操作</span><span class="sxs-lookup"><span data-stu-id="48b2a-116">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>](enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 <span data-ttu-id="48b2a-117">说明如何将数据拖到`RichTextBox`控件。</span><span class="sxs-lookup"><span data-stu-id="48b2a-117">Provides instructions for dragging data into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="48b2a-118">如何：将文件加载到 Windows 窗体 RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="48b2a-118">How to: Load Files into the Windows Forms RichTextBox Control</span></span>](how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="48b2a-119">提供用于加载到现有文件的说明`RichTextBox`控件。</span><span class="sxs-lookup"><span data-stu-id="48b2a-119">Provides instructions for loading an existing file into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="48b2a-120">如何：使用 Windows 窗体 RichTextBox 控件保存文件</span><span class="sxs-lookup"><span data-stu-id="48b2a-120">How to: Save Files with the Windows Forms RichTextBox Control</span></span>](how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="48b2a-121">提供用于保存的内容说明`RichTextBox`到文件的控件。</span><span class="sxs-lookup"><span data-stu-id="48b2a-121">Provides instructions for saving the contents of the `RichTextBox` control to a file.</span></span>  
  
 [<span data-ttu-id="48b2a-122">如何：Windows 窗体 RichTextBox 控件设置字体特性</span><span class="sxs-lookup"><span data-stu-id="48b2a-122">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="48b2a-123">介绍如何设置字体系列、 大小、 样式和中的文本颜色`RichTextBox`控件。</span><span class="sxs-lookup"><span data-stu-id="48b2a-123">Describes how to set the font family, size, style, and color of text in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="48b2a-124">如何：设置缩进、 悬挂缩进和项目符号的段落，使用 Windows 窗体 RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="48b2a-124">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 <span data-ttu-id="48b2a-125">介绍了如何设置中的段落`RichTextBox`控件。</span><span class="sxs-lookup"><span data-stu-id="48b2a-125">Describes how to format paragraphs in the `RichTextBox` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="48b2a-126">参考</span><span class="sxs-lookup"><span data-stu-id="48b2a-126">Reference</span></span>  
 <span data-ttu-id="48b2a-127"><xref:System.Windows.Forms.RichTextBox> 类</span><span class="sxs-lookup"><span data-stu-id="48b2a-127"><xref:System.Windows.Forms.RichTextBox> class</span></span>  
 <span data-ttu-id="48b2a-128">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="48b2a-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="48b2a-129">相关章节</span><span class="sxs-lookup"><span data-stu-id="48b2a-129">Related Sections</span></span>  
 [<span data-ttu-id="48b2a-130">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="48b2a-130">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="48b2a-131">提供 Windows 窗体控件的完整列表，附带其使用情况相关信息的链接。</span><span class="sxs-lookup"><span data-stu-id="48b2a-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="48b2a-132">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="48b2a-132">TextBox Control</span></span>](textbox-control-windows-forms.md)  
 <span data-ttu-id="48b2a-133">引入了的一般概念<xref:System.Windows.Forms.TextBox>控件，它允许来自用户的可编辑、 多行输入。</span><span class="sxs-lookup"><span data-stu-id="48b2a-133">Introduces the general concepts of the <xref:System.Windows.Forms.TextBox> control, which allows editable, multiline input from the user.</span></span>
