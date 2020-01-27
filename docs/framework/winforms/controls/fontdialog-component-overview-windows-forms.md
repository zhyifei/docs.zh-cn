---
title: FontDialog 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 664b756dc068ca283e4f43edbdd0f3266f5d1142
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745703"
---
# <a name="fontdialog-component-overview-windows-forms"></a><span data-ttu-id="579cd-102">FontDialog 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="579cd-102">FontDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="579cd-103">Windows 窗体 <xref:System.Windows.Forms.FontDialog> 组件是一个预先配置的对话框，该对话框是标准的 Windows**字体**对话框，用于公开当前安装在系统中的字体。</span><span class="sxs-lookup"><span data-stu-id="579cd-103">The Windows Forms <xref:System.Windows.Forms.FontDialog> component is a pre-configured dialog box, which is the standard Windows **Font** dialog box used to expose the fonts that are currently installed on the system.</span></span> <span data-ttu-id="579cd-104">在基于 Windows 的应用程序中使用它作为字体选择的简单解决方案，而不是配置自己的对话框。</span><span class="sxs-lookup"><span data-stu-id="579cd-104">Use it within your Windows-based application as a simple solution for font selection in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="579cd-105">默认情况下，该对话框将显示字体、字形和字号的列表框;用于效果的复选框，如删除线和下划线;脚本的下拉列表;以及字体显示方式的示例。</span><span class="sxs-lookup"><span data-stu-id="579cd-105">By default, the dialog box shows list boxes for Font, Font style, and Size; check boxes for effects like Strikeout and Underline; a drop-down list for Script; and a sample of how the font will appear.</span></span> <span data-ttu-id="579cd-106">（脚本是指可用于给定字体的不同字符脚本，例如希伯来语或日语。）若要显示 "字体" 对话框，请调用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="579cd-106">(Script refers to different character scripts that are available for a given font, for example, Hebrew or Japanese.) To display the font dialog box, call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="579cd-107">키 속성</span><span class="sxs-lookup"><span data-stu-id="579cd-107">Key Properties</span></span>  
 <span data-ttu-id="579cd-108">组件具有多个配置其外观的属性。</span><span class="sxs-lookup"><span data-stu-id="579cd-108">The component has a number of properties that configure its appearance.</span></span> <span data-ttu-id="579cd-109">设置对话框选择的属性将 <xref:System.Windows.Forms.FontDialog.Font%2A> 和 <xref:System.Windows.Forms.FontDialog.Color%2A>。</span><span class="sxs-lookup"><span data-stu-id="579cd-109">The properties that set the dialog-box selections are <xref:System.Windows.Forms.FontDialog.Font%2A> and <xref:System.Windows.Forms.FontDialog.Color%2A>.</span></span> <span data-ttu-id="579cd-110"><xref:System.Windows.Forms.FontDialog.Font%2A> 属性设置字体、样式、大小、脚本和效果;例如，`Arial, 10pt, style=Italic, Strikeout`。</span><span class="sxs-lookup"><span data-stu-id="579cd-110">The <xref:System.Windows.Forms.FontDialog.Font%2A> property sets the font, style, size, script, and effects; for example, `Arial, 10pt, style=Italic, Strikeout`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="579cd-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="579cd-111">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="579cd-112">FontDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="579cd-112">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)
