---
title: "TextBox 控件（Windows 窗体）"
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
- TextBox control [Windows Forms]
ms.assetid: e5a06987-8aec-4271-b196-2245ba992d62
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d606140a5be2b1770bc5a16159e96e20b0fccdd9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="textbox-control-windows-forms"></a><span data-ttu-id="14a0d-102">TextBox 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="14a0d-102">TextBox Control (Windows Forms)</span></span>
<span data-ttu-id="14a0d-103">若要获取用户输入或显示文本使用 Windows 窗体的文本框。</span><span class="sxs-lookup"><span data-stu-id="14a0d-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="14a0d-104">`TextBox`控件通常用于可编辑文本，虽然也可使其成为只读的。</span><span class="sxs-lookup"><span data-stu-id="14a0d-104">The `TextBox` control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="14a0d-105">文本框可以显示多个行，为该控件的大小的文本换行并添加基本格式设置。</span><span class="sxs-lookup"><span data-stu-id="14a0d-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="14a0d-106">`TextBox`控件允许文本控件中输入或显示一种格式。</span><span class="sxs-lookup"><span data-stu-id="14a0d-106">The `TextBox` control allows a single format for text displayed or entered in the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14a0d-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="14a0d-107">In This Section</span></span>  
 [<span data-ttu-id="14a0d-108">TextBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="14a0d-108">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 <span data-ttu-id="14a0d-109">说明此控件的本质及其主要功能和属性。</span><span class="sxs-lookup"><span data-stu-id="14a0d-109">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="14a0d-110">如何：在 Windows 窗体 TextBox 控件中控制插入点</span><span class="sxs-lookup"><span data-stu-id="14a0d-110">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 <span data-ttu-id="14a0d-111">提供有关如何指定一个编辑控件首先获得焦点时插入点出现的位置。</span><span class="sxs-lookup"><span data-stu-id="14a0d-111">Gives directions for specifying where the insertion point appears when an edit control first gets the focus.</span></span>  
  
 [<span data-ttu-id="14a0d-112">如何：使用 Windows 窗体 TextBox 控件创建密码文本框</span><span class="sxs-lookup"><span data-stu-id="14a0d-112">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="14a0d-113">解释如何隐藏文本框中键入的内容。</span><span class="sxs-lookup"><span data-stu-id="14a0d-113">Explains how to conceal what is typed into a text box.</span></span>  
  
 [<span data-ttu-id="14a0d-114">如何：创建只读文本框</span><span class="sxs-lookup"><span data-stu-id="14a0d-114">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 <span data-ttu-id="14a0d-115">描述如何防止一个文本框的内容被更改。</span><span class="sxs-lookup"><span data-stu-id="14a0d-115">Describes how to prevent the contents of a text box from being changed.</span></span>  
  
 [<span data-ttu-id="14a0d-116">如何：在字符串中添加引号</span><span class="sxs-lookup"><span data-stu-id="14a0d-116">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 <span data-ttu-id="14a0d-117">介绍在文本框中的字符串的方法添加引号引起来。</span><span class="sxs-lookup"><span data-stu-id="14a0d-117">Explains adding quotation marks to a string in a text box.</span></span>  
  
 [<span data-ttu-id="14a0d-118">如何：在 Windows 窗体 TextBox 控件中选择文本</span><span class="sxs-lookup"><span data-stu-id="14a0d-118">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="14a0d-119">说明如何突出显示在文本框中的文本。</span><span class="sxs-lookup"><span data-stu-id="14a0d-119">Explains how to highlight text in a text box.</span></span>  
  
 [<span data-ttu-id="14a0d-120">如何：在 Windows 窗体 TextBox 控件中查看多个行</span><span class="sxs-lookup"><span data-stu-id="14a0d-120">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="14a0d-121">描述如何使文本框中可滚动。</span><span class="sxs-lookup"><span data-stu-id="14a0d-121">Describes how to make a text box scrollable.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="14a0d-122">参考</span><span class="sxs-lookup"><span data-stu-id="14a0d-122">Reference</span></span>  
 <span data-ttu-id="14a0d-123"><xref:System.Windows.Forms.TextBox> 类</span><span class="sxs-lookup"><span data-stu-id="14a0d-123"><xref:System.Windows.Forms.TextBox> class</span></span>  
 <span data-ttu-id="14a0d-124">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="14a0d-124">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="14a0d-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="14a0d-125">Related Sections</span></span>  
 [<span data-ttu-id="14a0d-126">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="14a0d-126">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="14a0d-127">提供 Windows 窗体控件的完整列表，附带其使用情况相关信息的链接。</span><span class="sxs-lookup"><span data-stu-id="14a0d-127">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
