---
title: "FontDialog 组件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b9e3018d024254adb249860f7736399e7f2da72a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="fontdialog-component-overview-windows-forms"></a><span data-ttu-id="472de-102">FontDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="472de-102">FontDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="472de-103">Windows 窗体<xref:System.Windows.Forms.FontDialog>组件是一个预配置的对话框，这是标准的 Windows**字体**用于公开当前系统安装的字体的对话框。</span><span class="sxs-lookup"><span data-stu-id="472de-103">The Windows Forms <xref:System.Windows.Forms.FontDialog> component is a pre-configured dialog box, which is the standard Windows **Font** dialog box used to expose the fonts that are currently installed on the system.</span></span> <span data-ttu-id="472de-104">替代配置自己对话框的字体选择基于 Windows 的应用程序作为简单的解决方案中使用它。</span><span class="sxs-lookup"><span data-stu-id="472de-104">Use it within your Windows-based application as a simple solution for font selection in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="472de-105">默认情况下，该对话框显示列表框字体，字体样式和大小;效果，例如删除线和下划线; 对应的复选框脚本; 下拉列表和的显示字体的外观示例。</span><span class="sxs-lookup"><span data-stu-id="472de-105">By default, the dialog box shows list boxes for Font, Font style, and Size; check boxes for effects like Strikeout and Underline; a drop-down list for Script; and a sample of how the font will appear.</span></span> <span data-ttu-id="472de-106">（脚本引用不同的字符脚本可用于给定字体，例如，希伯来语或日语。）若要显示字体对话框中，调用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="472de-106">(Script refers to different character scripts that are available for a given font, for example, Hebrew or Japanese.) To display the font dialog box, call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="472de-107">键属性</span><span class="sxs-lookup"><span data-stu-id="472de-107">Key Properties</span></span>  
 <span data-ttu-id="472de-108">该组件具有多个配置其外观的属性。</span><span class="sxs-lookup"><span data-stu-id="472de-108">The component has a number of properties that configure its appearance.</span></span> <span data-ttu-id="472de-109">设置对话框中选择的属性是<xref:System.Windows.Forms.FontDialog.Font%2A>和<xref:System.Windows.Forms.FontDialog.Color%2A>。</span><span class="sxs-lookup"><span data-stu-id="472de-109">The properties that set the dialog-box selections are <xref:System.Windows.Forms.FontDialog.Font%2A> and <xref:System.Windows.Forms.FontDialog.Color%2A>.</span></span> <span data-ttu-id="472de-110"><xref:System.Windows.Forms.FontDialog.Font%2A>属性设置字体、 样式、 大小、 脚本和效果; 例如， `Arial, 10pt, style=Italic, Strikeout`。</span><span class="sxs-lookup"><span data-stu-id="472de-110">The <xref:System.Windows.Forms.FontDialog.Font%2A> property sets the font, style, size, script, and effects; for example, `Arial, 10pt, style=Italic, Strikeout`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="472de-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="472de-111">See Also</span></span>  
 <xref:System.Windows.Forms.FontDialog>  
 [<span data-ttu-id="472de-112">FontDialog 组件</span><span class="sxs-lookup"><span data-stu-id="472de-112">FontDialog Component</span></span>](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)
