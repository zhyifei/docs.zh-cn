---
title: 如何：将光标置于 TextBox 控件中的文本的开头或末尾
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
ms.openlocfilehash: e4058518e4eb56e1cd9d5fdafd792d8f8d3b77ab
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367838"
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a><span data-ttu-id="d4660-102">如何：将光标置于 TextBox 控件中的文本的开头或末尾</span><span class="sxs-lookup"><span data-stu-id="d4660-102">How to: Position the Cursor at the Beginning or End of Text in a TextBox Control</span></span>
<span data-ttu-id="d4660-103">此示例演示如何在开头或末尾的文本内容将光标置于<xref:System.Windows.Controls.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="d4660-103">This example shows how to position the cursor at the beginning or end of the text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4660-104">示例</span><span class="sxs-lookup"><span data-stu-id="d4660-104">Example</span></span>  
 <span data-ttu-id="d4660-105">以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]代码描述<xref:System.Windows.Controls.TextBox>控制并将其分配一个名称。</span><span class="sxs-lookup"><span data-stu-id="d4660-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a <xref:System.Windows.Controls.TextBox> control and assigns it a Name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a><span data-ttu-id="d4660-106">示例</span><span class="sxs-lookup"><span data-stu-id="d4660-106">Example</span></span>  
 <span data-ttu-id="d4660-107">若要将光标放置的内容的开头<xref:System.Windows.Controls.TextBox>控件，调用<xref:System.Windows.Controls.TextBox.Select%2A>方法并指定所选起始位置为 0，并选择长度为 0。</span><span class="sxs-lookup"><span data-stu-id="d4660-107">To position the cursor at the beginning of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position of 0, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a><span data-ttu-id="d4660-108">示例</span><span class="sxs-lookup"><span data-stu-id="d4660-108">Example</span></span>  
 <span data-ttu-id="d4660-109">若要结束的内容将光标置于<xref:System.Windows.Controls.TextBox>控件，调用<xref:System.Windows.Controls.TextBox.Select%2A>方法并指定所选内容的起始位置相等长度的文本内容，并选择长度为 0。</span><span class="sxs-lookup"><span data-stu-id="d4660-109">To position the cursor at the end of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position equal to the  length of the text content, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a><span data-ttu-id="d4660-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4660-110">See also</span></span>
- [<span data-ttu-id="d4660-111">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="d4660-111">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="d4660-112">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="d4660-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
