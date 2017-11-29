---
title: "如何：将光标置于 TextBox 控件中的文本的开头或末尾"
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
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0efa81a9606235b214f30a8c6febb94ea2968714
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a><span data-ttu-id="98cef-102">如何：将光标置于 TextBox 控件中的文本的开头或末尾</span><span class="sxs-lookup"><span data-stu-id="98cef-102">How to: Position the Cursor at the Beginning or End of Text in a TextBox Control</span></span>
<span data-ttu-id="98cef-103">此示例演示如何将光标置于的开头或末尾的文本内容<xref:System.Windows.Controls.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="98cef-103">This example shows how to position the cursor at the beginning or end of the text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98cef-104">示例</span><span class="sxs-lookup"><span data-stu-id="98cef-104">Example</span></span>  
 <span data-ttu-id="98cef-105">以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]代码描述<xref:System.Windows.Controls.TextBox>控制并将其分配一个名称。</span><span class="sxs-lookup"><span data-stu-id="98cef-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a <xref:System.Windows.Controls.TextBox> control and assigns it a Name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a><span data-ttu-id="98cef-106">示例</span><span class="sxs-lookup"><span data-stu-id="98cef-106">Example</span></span>  
 <span data-ttu-id="98cef-107">将光标定位在的内容的开头<xref:System.Windows.Controls.TextBox>控制，请调用<xref:System.Windows.Controls.TextBox.Select%2A>方法并指定选择内容的起始位置为 0，并选择长度为 0。</span><span class="sxs-lookup"><span data-stu-id="98cef-107">To position the cursor at the beginning of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position of 0, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a><span data-ttu-id="98cef-108">示例</span><span class="sxs-lookup"><span data-stu-id="98cef-108">Example</span></span>  
 <span data-ttu-id="98cef-109">内容的末尾将光标定位<xref:System.Windows.Controls.TextBox>控制，请调用<xref:System.Windows.Controls.TextBox.Select%2A>方法并指定所选内容的起始位置等于的长度的文本内容，且所选内容长度为 0。</span><span class="sxs-lookup"><span data-stu-id="98cef-109">To position the cursor at the end of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position equal to the  length of the text content, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a><span data-ttu-id="98cef-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98cef-110">See Also</span></span>  
 [<span data-ttu-id="98cef-111">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="98cef-111">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="98cef-112">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="98cef-112">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
