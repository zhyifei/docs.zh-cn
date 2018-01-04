---
title: "如何：使用上下文菜单中的拼写检查功能"
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
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8a85426dc526e1e8560f494bcde5247fc394f7bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a><span data-ttu-id="def46-102">如何：使用上下文菜单中的拼写检查功能</span><span class="sxs-lookup"><span data-stu-id="def46-102">How to: Use Spell Checking with a Context Menu</span></span>
<span data-ttu-id="def46-103">默认情况下，当你启用拼写检查的编辑控件中如<xref:System.Windows.Controls.TextBox>或<xref:System.Windows.Controls.RichTextBox>，上下文菜单中使拼写检查的选择。</span><span class="sxs-lookup"><span data-stu-id="def46-103">By default, when you enable spell checking in an editing control like <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>, you get spell-checking choices in the context menu.</span></span> <span data-ttu-id="def46-104">例如，当用户右击拼错的字，会得到的拼写建议或选项组**全部忽略**。</span><span class="sxs-lookup"><span data-stu-id="def46-104">For example, when users right-click a misspelled word, they get a set of spelling suggestions or the option to **Ignore All**.</span></span> <span data-ttu-id="def46-105">但是，当你重写默认上下文菜单，其中您自己的自定义上下文菜单，此功能将会丢失，并且你需要编写代码以重新启用上下文菜单中的拼写检查功能。</span><span class="sxs-lookup"><span data-stu-id="def46-105">However, when you override the default context menu with your own custom context menu, this functionality is lost, and you need to write code to reenable the spell-checking feature in the context menu.</span></span> <span data-ttu-id="def46-106">下面的示例演示如何启用此设置<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="def46-106">The following example shows how to enable this on a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="def46-107">示例</span><span class="sxs-lookup"><span data-stu-id="def46-107">Example</span></span>  
 <span data-ttu-id="def46-108">下面的示例演示[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]创建<xref:System.Windows.Controls.TextBox>与用于实现上下文菜单上的某些事件。</span><span class="sxs-lookup"><span data-stu-id="def46-108">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that creates a <xref:System.Windows.Controls.TextBox> with some events that are used to implement the context menu.</span></span>  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="def46-109">示例</span><span class="sxs-lookup"><span data-stu-id="def46-109">Example</span></span>  
 <span data-ttu-id="def46-110">下面的示例演示实现的上下文菜单的代码。</span><span class="sxs-lookup"><span data-stu-id="def46-110">The following example shows the code that implements the context menu.</span></span>  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 <span data-ttu-id="def46-111">用于执行与此操作的代码<xref:System.Windows.Controls.RichTextBox>类似。</span><span class="sxs-lookup"><span data-stu-id="def46-111">The code used for doing this with a <xref:System.Windows.Controls.RichTextBox> is similar.</span></span> <span data-ttu-id="def46-112">主要区别在于传递给参数`GetSpellingError`方法。</span><span class="sxs-lookup"><span data-stu-id="def46-112">The main difference is in the parameter passed to the `GetSpellingError` method.</span></span> <span data-ttu-id="def46-113">有关<xref:System.Windows.Controls.TextBox>，传递脱字号位置的整数索引：</span><span class="sxs-lookup"><span data-stu-id="def46-113">For a <xref:System.Windows.Controls.TextBox>, pass the integer index of the caret position:</span></span>  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 <span data-ttu-id="def46-114">有关<xref:System.Windows.Controls.RichTextBox>，传递<xref:System.Windows.Documents.TextPointer>，它指定的插入符号位置：</span><span class="sxs-lookup"><span data-stu-id="def46-114">For a <xref:System.Windows.Controls.RichTextBox>, pass the <xref:System.Windows.Documents.TextPointer> that specifies the caret position:</span></span>  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a><span data-ttu-id="def46-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="def46-115">See Also</span></span>  
 [<span data-ttu-id="def46-116">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="def46-116">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="def46-117">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="def46-117">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [<span data-ttu-id="def46-118">在文本编辑控件中启用拼写检查</span><span class="sxs-lookup"><span data-stu-id="def46-118">Enable Spell Checking in a Text Editing Control</span></span>](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)  
 [<span data-ttu-id="def46-119">将自定义上下文菜单与 TextBox 结合使用</span><span class="sxs-lookup"><span data-stu-id="def46-119">Use a Custom Context Menu with a TextBox</span></span>](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)
