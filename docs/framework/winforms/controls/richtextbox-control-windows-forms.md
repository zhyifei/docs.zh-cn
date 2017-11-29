---
title: "RichTextBox 控件（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text boxes
- RichTextBox control [Windows Forms]
- rich edit controls
ms.assetid: 3225f2ef-c6d9-4bd4-9d3e-2219e58edbf2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 80621a12a4ccd5008a0331af005629d45f60abdf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="richtextbox-control-windows-forms"></a><span data-ttu-id="4bc59-102">RichTextBox 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="4bc59-102">RichTextBox Control (Windows Forms)</span></span>
<span data-ttu-id="4bc59-103">Windows 窗体`RichTextBox`控件用于显示、 输入和操作具有格式的文本。</span><span class="sxs-lookup"><span data-stu-id="4bc59-103">The Windows Forms `RichTextBox` control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="4bc59-104">`RichTextBox`控件的作用的所有内容<xref:System.Windows.Forms.TextBox>控件的作用，但它还可以显示字体、 颜色和链接; 从文件; 撤消和重做编辑操作; 加载文本和嵌入的图像并查找指定的字符。</span><span class="sxs-lookup"><span data-stu-id="4bc59-104">The `RichTextBox` control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; undo and redo editing operations; and find specified characters.</span></span> <span data-ttu-id="4bc59-105">`RichTextBox`控件通常用于文本操作，并显示类似于 Microsoft Word 等文字处理应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="4bc59-105">The `RichTextBox` control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="4bc59-106">如<xref:System.Windows.Forms.TextBox>控件，`RichTextBox`控件可以显示滚动条; 但与<xref:System.Windows.Forms.TextBox>控件，它显示水平和垂直滚动条显示默认情况下，并具有其他的滚动条的设置。</span><span class="sxs-lookup"><span data-stu-id="4bc59-106">Like the <xref:System.Windows.Forms.TextBox> control, the `RichTextBox` control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, it displays both horizontal and vertical scrollbars by default and has additional scrollbar settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4bc59-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="4bc59-107">In This Section</span></span>  
 [<span data-ttu-id="4bc59-108">RichTextBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="4bc59-108">RichTextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md)  
 <span data-ttu-id="4bc59-109">引入了的一般概念`RichTextBox`控件，它允许用户输入，显示和操作文本具有格式设置选项。</span><span class="sxs-lookup"><span data-stu-id="4bc59-109">Introduces the general concepts of the `RichTextBox` control, which allows users to enter, display, and manipulate text with formatting options.</span></span>  
  
 [<span data-ttu-id="4bc59-110">如何：在 Windows 窗体 RichTextBox 控件中确定格式设置特性何时发生变化</span><span class="sxs-lookup"><span data-stu-id="4bc59-110">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 <span data-ttu-id="4bc59-111">说明如何跟踪的字体和段落格式设置中的更改`RichTextBox`控件。</span><span class="sxs-lookup"><span data-stu-id="4bc59-111">Explains how to keep track of changes in font and paragraph formatting in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="4bc59-112">如何：在 Windows 窗体 RichTextBox 控件中显示滚动条</span><span class="sxs-lookup"><span data-stu-id="4bc59-112">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="4bc59-113">介绍可用于在滚动条的许多选项`RichTextBox`控件。</span><span class="sxs-lookup"><span data-stu-id="4bc59-113">Describes the many choices available for scroll bars in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="4bc59-114">如何：使用 Windows 窗体 RichTextBox 控件显示 Web 样式链接</span><span class="sxs-lookup"><span data-stu-id="4bc59-114">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="4bc59-115">说明如何将链接到网站从`RichTextBox`控件。</span><span class="sxs-lookup"><span data-stu-id="4bc59-115">Explains how to link to Web sites from the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="4bc59-116">如何：在 Windows 窗体 RichTextBox 控件中启用拖放操作</span><span class="sxs-lookup"><span data-stu-id="4bc59-116">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 <span data-ttu-id="4bc59-117">提供有关拖动到的数据的说明`RichTextBox`控件。</span><span class="sxs-lookup"><span data-stu-id="4bc59-117">Provides instructions for dragging data into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="4bc59-118">如何：将文件加载到 Windows 窗体 RichTextBox 控件中</span><span class="sxs-lookup"><span data-stu-id="4bc59-118">How to: Load Files into the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="4bc59-119">提供用于加载到现有文件的说明`RichTextBox`控件。</span><span class="sxs-lookup"><span data-stu-id="4bc59-119">Provides instructions for loading an existing file into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="4bc59-120">如何：使用 Windows 窗体 RichTextBox 控件保存文件</span><span class="sxs-lookup"><span data-stu-id="4bc59-120">How to: Save Files with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="4bc59-121">提供有关保存的内容的说明`RichTextBox`到文件的控件。</span><span class="sxs-lookup"><span data-stu-id="4bc59-121">Provides instructions for saving the contents of the `RichTextBox` control to a file.</span></span>  
  
 [<span data-ttu-id="4bc59-122">如何：设置 Windows 窗体 RichTextBox 控件的字体特性</span><span class="sxs-lookup"><span data-stu-id="4bc59-122">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="4bc59-123">描述如何设置字体系列、 大小、 样式和中文本的颜色`RichTextBox`控件。</span><span class="sxs-lookup"><span data-stu-id="4bc59-123">Describes how to set the font family, size, style, and color of text in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="4bc59-124">如何：使用 Windows 窗体 RichTextBox 控件设置缩进、悬挂缩进和点符段落</span><span class="sxs-lookup"><span data-stu-id="4bc59-124">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 <span data-ttu-id="4bc59-125">描述如何设置中的段落格式`RichTextBox`控件。</span><span class="sxs-lookup"><span data-stu-id="4bc59-125">Describes how to format paragraphs in the `RichTextBox` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4bc59-126">参考</span><span class="sxs-lookup"><span data-stu-id="4bc59-126">Reference</span></span>  
 <span data-ttu-id="4bc59-127"><xref:System.Windows.Forms.RichTextBox> 类</span><span class="sxs-lookup"><span data-stu-id="4bc59-127"><xref:System.Windows.Forms.RichTextBox> class</span></span>  
 <span data-ttu-id="4bc59-128">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="4bc59-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4bc59-129">相关章节</span><span class="sxs-lookup"><span data-stu-id="4bc59-129">Related Sections</span></span>  
 [<span data-ttu-id="4bc59-130">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="4bc59-130">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="4bc59-131">提供 Windows 窗体控件的完整列表，附带其使用情况相关信息的链接。</span><span class="sxs-lookup"><span data-stu-id="4bc59-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="4bc59-132">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="4bc59-132">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)  
 <span data-ttu-id="4bc59-133">引入了的一般概念<xref:System.Windows.Forms.TextBox>控件，它允许来自用户的可编辑的多行输入。</span><span class="sxs-lookup"><span data-stu-id="4bc59-133">Introduces the general concepts of the <xref:System.Windows.Forms.TextBox> control, which allows editable, multiline input from the user.</span></span>
