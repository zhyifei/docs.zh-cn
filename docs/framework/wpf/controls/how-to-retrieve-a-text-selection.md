---
title: 如何：检索选定文本内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
ms.openlocfilehash: b7f0b9ee02a7ace717787fc8eeb6e15649829a49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224580"
---
# <a name="how-to-retrieve-a-text-selection"></a><span data-ttu-id="bf8c4-102">如何：检索选定文本内容</span><span class="sxs-lookup"><span data-stu-id="bf8c4-102">How to: Retrieve a Text Selection</span></span>
<span data-ttu-id="bf8c4-103">此示例演示使用一种方法<xref:System.Windows.Controls.TextBox.SelectedText%2A>属性来检索用户已经选择了中的文本<xref:System.Windows.Controls.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="bf8c4-103">This example shows one way to use the <xref:System.Windows.Controls.TextBox.SelectedText%2A> property to retrieve text that the user has selected in a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf8c4-104">示例</span><span class="sxs-lookup"><span data-stu-id="bf8c4-104">Example</span></span>  
 <span data-ttu-id="bf8c4-105">以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]示例演示的定义<xref:System.Windows.Controls.TextBox>控件，其中包含一些文本，若要选择，和一个<xref:System.Windows.Controls.Button>与指定的控件<xref:System.Windows.Controls.Button.OnClick%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="bf8c4-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example shows the definition of a <xref:System.Windows.Controls.TextBox> control that contains some text to select, and a <xref:System.Windows.Controls.Button> control with a specified <xref:System.Windows.Controls.Button.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="bf8c4-106">在此示例中，一个具有一个关联的按钮<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件处理程序用于检索文本选定内容。</span><span class="sxs-lookup"><span data-stu-id="bf8c4-106">In this example, a button with an associated <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler is used to retrieve the text selection.</span></span> <span data-ttu-id="bf8c4-107">当用户单击按钮，<xref:System.Windows.Controls.Button.OnClick%2A>方法将任何所选的文本在文本框中复制到一个字符串。</span><span class="sxs-lookup"><span data-stu-id="bf8c4-107">When the user clicks the button, the <xref:System.Windows.Controls.Button.OnClick%2A> method copies any selected text in the textbox into a string.</span></span> <span data-ttu-id="bf8c4-108">在特定情况的文本选择检索 （单击某个按钮），还可以使用 （将选定文本复制到一个字符串） 所选内容，所执行的操作可以轻松修改以适应各种方案。</span><span class="sxs-lookup"><span data-stu-id="bf8c4-108">The particular circumstances by which the text selection is retrieved (clicking a button), as well as the action taken with that selection (copying the text selection to a string), can easily be modified to accommodate a wide variety of scenarios.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a><span data-ttu-id="bf8c4-109">示例</span><span class="sxs-lookup"><span data-stu-id="bf8c4-109">Example</span></span>  
 <span data-ttu-id="bf8c4-110">以下C#的示例演示<xref:System.Windows.Controls.Button.OnClick%2A>事件处理程序中定义的按钮[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]对于此示例。</span><span class="sxs-lookup"><span data-stu-id="bf8c4-110">The following C# example shows an <xref:System.Windows.Controls.Button.OnClick%2A> event handler for the button defined in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for this example.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a><span data-ttu-id="bf8c4-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf8c4-111">See also</span></span>

- [<span data-ttu-id="bf8c4-112">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="bf8c4-112">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="bf8c4-113">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="bf8c4-113">RichTextBox Overview</span></span>](richtextbox-overview.md)
