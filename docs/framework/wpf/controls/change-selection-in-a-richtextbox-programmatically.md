---
title: 以编程方式更改 RichTextBox 中的选定内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- changing selections in a text box [WPF]
- changing selections in a RichTextBox [WPF]
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
ms.openlocfilehash: e8ad33956f1a9fdddc728457e6c302635115b709
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550997"
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a><span data-ttu-id="fce1e-102">以编程方式更改 RichTextBox 中的选定内容</span><span class="sxs-lookup"><span data-stu-id="fce1e-102">Change Selection in a RichTextBox Programmatically</span></span>
<span data-ttu-id="fce1e-103">此示例演示如何以编程方式更改中的当前选定<xref:System.Windows.Controls.RichTextBox>。</span><span class="sxs-lookup"><span data-stu-id="fce1e-103">This example shows how to programmatically change the current selection in a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="fce1e-104">如果因为用户已通过使用用户界面选择内容，选择此选项都是相同的。</span><span class="sxs-lookup"><span data-stu-id="fce1e-104">This selection is the same as if the user had selected the content by using the user interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fce1e-105">示例</span><span class="sxs-lookup"><span data-stu-id="fce1e-105">Example</span></span>  
 <span data-ttu-id="fce1e-106">以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]代码描述命名<xref:System.Windows.Controls.RichTextBox>具有简单内容的控件。</span><span class="sxs-lookup"><span data-stu-id="fce1e-106">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="fce1e-107">示例</span><span class="sxs-lookup"><span data-stu-id="fce1e-107">Example</span></span>  
 <span data-ttu-id="fce1e-108">下面的代码以编程方式选择一些任意文本，当用户单击内<xref:System.Windows.Controls.RichTextBox>。</span><span class="sxs-lookup"><span data-stu-id="fce1e-108">The following code programmatically selects some arbitrary text when the user clicks inside the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="fce1e-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="fce1e-109">See Also</span></span>  
 [<span data-ttu-id="fce1e-110">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="fce1e-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [<span data-ttu-id="fce1e-111">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="fce1e-111">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
