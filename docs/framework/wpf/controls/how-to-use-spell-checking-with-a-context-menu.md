---
title: 如何：使用上下文菜单中的拼写检查功能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
ms.openlocfilehash: 2b6790fd4d5d2e322a46bd98ed19e7b88c4923c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713111"
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a><span data-ttu-id="23f3d-102">如何：使用上下文菜单中的拼写检查功能</span><span class="sxs-lookup"><span data-stu-id="23f3d-102">How to: Use Spell Checking with a Context Menu</span></span>
<span data-ttu-id="23f3d-103">默认情况下，当启用拼写检查的编辑控件中时喜欢<xref:System.Windows.Controls.TextBox>或<xref:System.Windows.Controls.RichTextBox>，上下文菜单中获取拼写检查功能的选项。</span><span class="sxs-lookup"><span data-stu-id="23f3d-103">By default, when you enable spell checking in an editing control like <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>, you get spell-checking choices in the context menu.</span></span> <span data-ttu-id="23f3d-104">例如，当用户右键单击拼错的单词，会得到一组拼写建议或选项**忽略所有**。</span><span class="sxs-lookup"><span data-stu-id="23f3d-104">For example, when users right-click a misspelled word, they get a set of spelling suggestions or the option to **Ignore All**.</span></span> <span data-ttu-id="23f3d-105">但是时重写默认上下文菜单与自己的自定义上下文菜单，, 此功能将丢失，并且您需要自己编写代码以重新启用的上下文菜单中的拼写检查功能。</span><span class="sxs-lookup"><span data-stu-id="23f3d-105">However, when you override the default context menu with your own custom context menu, this functionality is lost, and you need to write code to reenable the spell-checking feature in the context menu.</span></span> <span data-ttu-id="23f3d-106">下面的示例演示如何启用此配置<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="23f3d-106">The following example shows how to enable this on a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23f3d-107">示例</span><span class="sxs-lookup"><span data-stu-id="23f3d-107">Example</span></span>  
 <span data-ttu-id="23f3d-108">下面的示例演示[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，创建<xref:System.Windows.Controls.TextBox>与用于实现的上下文菜单的某些事件。</span><span class="sxs-lookup"><span data-stu-id="23f3d-108">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that creates a <xref:System.Windows.Controls.TextBox> with some events that are used to implement the context menu.</span></span>  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="23f3d-109">示例</span><span class="sxs-lookup"><span data-stu-id="23f3d-109">Example</span></span>  
 <span data-ttu-id="23f3d-110">下面的示例显示了实现的上下文菜单的代码。</span><span class="sxs-lookup"><span data-stu-id="23f3d-110">The following example shows the code that implements the context menu.</span></span>  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 <span data-ttu-id="23f3d-111">使用实现这一点的代码<xref:System.Windows.Controls.RichTextBox>类似。</span><span class="sxs-lookup"><span data-stu-id="23f3d-111">The code used for doing this with a <xref:System.Windows.Controls.RichTextBox> is similar.</span></span> <span data-ttu-id="23f3d-112">传递给在参数中的主要区别是`GetSpellingError`方法。</span><span class="sxs-lookup"><span data-stu-id="23f3d-112">The main difference is in the parameter passed to the `GetSpellingError` method.</span></span> <span data-ttu-id="23f3d-113">有关<xref:System.Windows.Controls.TextBox>，传递的插入符号位置的整数索引：</span><span class="sxs-lookup"><span data-stu-id="23f3d-113">For a <xref:System.Windows.Controls.TextBox>, pass the integer index of the caret position:</span></span>  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 <span data-ttu-id="23f3d-114">有关<xref:System.Windows.Controls.RichTextBox>，将传递<xref:System.Windows.Documents.TextPointer>，它指定插入符号位置：</span><span class="sxs-lookup"><span data-stu-id="23f3d-114">For a <xref:System.Windows.Controls.RichTextBox>, pass the <xref:System.Windows.Documents.TextPointer> that specifies the caret position:</span></span>  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a><span data-ttu-id="23f3d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="23f3d-115">See also</span></span>
- [<span data-ttu-id="23f3d-116">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="23f3d-116">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [<span data-ttu-id="23f3d-117">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="23f3d-117">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
- [<span data-ttu-id="23f3d-118">在文本编辑控件中启用拼写检查</span><span class="sxs-lookup"><span data-stu-id="23f3d-118">Enable Spell Checking in a Text Editing Control</span></span>](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)
- [<span data-ttu-id="23f3d-119">将自定义上下文菜单与 TextBox 结合使用</span><span class="sxs-lookup"><span data-stu-id="23f3d-119">Use a Custom Context Menu with a TextBox</span></span>](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)
