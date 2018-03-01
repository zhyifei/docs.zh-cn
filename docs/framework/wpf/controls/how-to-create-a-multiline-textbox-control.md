---
title: "如何：创建多行 TextBox 控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2a6885a594e5fcd747f85dedf1afbd39ec644717
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-multiline-textbox-control"></a><span data-ttu-id="c8ff4-102">如何：创建多行 TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="c8ff4-102">How to: Create a Multiline TextBox Control</span></span>
<span data-ttu-id="c8ff4-103">此示例演示如何使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]定义<xref:System.Windows.Controls.TextBox>将自动扩展以容纳多行文本的控件。</span><span class="sxs-lookup"><span data-stu-id="c8ff4-103">This example shows how to use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.TextBox> control that will automatically expand to accommodate multiple lines of text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8ff4-104">示例</span><span class="sxs-lookup"><span data-stu-id="c8ff4-104">Example</span></span>  
 <span data-ttu-id="c8ff4-105">设置<xref:System.Windows.Controls.TextBox.TextWrapping%2A>属性设为**包装**将导致输入的文本换行到一个新行时的边缘<xref:System.Windows.Controls.TextBox>达到控件时，自动扩展<xref:System.Windows.Controls.TextBox>控件为新行，留出空间必需。</span><span class="sxs-lookup"><span data-stu-id="c8ff4-105">Setting the <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attribute to **Wrap** will cause entered text to wrap to a new line when the edge of the <xref:System.Windows.Controls.TextBox> control is reached, automatically expanding the <xref:System.Windows.Controls.TextBox> control to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="c8ff4-106">设置<xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A>属性设为**true**会导致在新行时按 RETURN 键，再一次自动扩展插入<xref:System.Windows.Controls.TextBox>以便留出空间为新行，如有必要。</span><span class="sxs-lookup"><span data-stu-id="c8ff4-106">Setting the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attribute to **true** causes a new line to be inserted when the RETURN key is pressed, once again automatically expanding the <xref:System.Windows.Controls.TextBox> to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="c8ff4-107"><xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A>属性添加到一个滚动条<xref:System.Windows.Controls.TextBox>，以便内容<xref:System.Windows.Controls.TextBox>可以滚动如果<xref:System.Windows.Controls.TextBox>超出的框架或包围它的窗口的大小。</span><span class="sxs-lookup"><span data-stu-id="c8ff4-107">The <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attribute adds a scroll bar to the <xref:System.Windows.Controls.TextBox>, so that the contents of the <xref:System.Windows.Controls.TextBox> can be scrolled through if the <xref:System.Windows.Controls.TextBox> expands beyond the size of the frame or window that encloses it.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="c8ff4-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8ff4-108">See Also</span></span>  
 <xref:System.Windows.TextWrapping>  
 [<span data-ttu-id="c8ff4-109">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="c8ff4-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="c8ff4-110">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="c8ff4-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
