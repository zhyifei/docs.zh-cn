---
title: "如何：保存、加载和打印 RichTextBox 内容"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- saving RichTextBox controls [WPF]
- printing RichTextBox controls [WPF]
- loading RichTextBox controls [WPF]
- RichTextBox control [WPF], saving
- RichTextBox control [WPF], printing
- RichTextBox control [WPF], loading
ms.assetid: ffb113d3-c68a-47ca-8ac0-882283f38326
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ca969848ae82d567642cd0f4174c52ebc24ef5d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-save-load-and-print-richtextbox-content"></a><span data-ttu-id="e9e6f-102">如何：保存、加载和打印 RichTextBox 内容</span><span class="sxs-lookup"><span data-stu-id="e9e6f-102">How to: Save, Load, and Print RichTextBox Content</span></span>
<span data-ttu-id="e9e6f-103">下面的示例演示如何将保存的内容<xref:System.Windows.Controls.RichTextBox>到文件，该内容重新加载到<xref:System.Windows.Controls.RichTextBox>，以及如何打印内容。</span><span class="sxs-lookup"><span data-stu-id="e9e6f-103">The following example shows how to save content of a <xref:System.Windows.Controls.RichTextBox> to a file, load that content back into the <xref:System.Windows.Controls.RichTextBox>, and print the contents.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9e6f-104">示例</span><span class="sxs-lookup"><span data-stu-id="e9e6f-104">Example</span></span>  
 <span data-ttu-id="e9e6f-105">下面是示例的标记。</span><span class="sxs-lookup"><span data-stu-id="e9e6f-105">Below is the markup for the example.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="e9e6f-106">示例</span><span class="sxs-lookup"><span data-stu-id="e9e6f-106">Example</span></span>  
 <span data-ttu-id="e9e6f-107">下面是该示例的隐藏代码。</span><span class="sxs-lookup"><span data-stu-id="e9e6f-107">Below is the code behind for the example.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e9e6f-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9e6f-108">See Also</span></span>  
 [<span data-ttu-id="e9e6f-109">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="e9e6f-109">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [<span data-ttu-id="e9e6f-110">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="e9e6f-110">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
