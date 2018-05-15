---
title: 如何：设置 TextBox 控件中的焦点
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus [WPF], setting
- TextBox control [WPF], setting focus
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
ms.openlocfilehash: 1bda01a3d330ad384c2f922ff3c7679e10d0f148
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-focus-in-a-textbox-control"></a><span data-ttu-id="4a531-102">如何：设置 TextBox 控件中的焦点</span><span class="sxs-lookup"><span data-stu-id="4a531-102">How to: Set Focus in a TextBox Control</span></span>
<span data-ttu-id="4a531-103">此示例演示如何使用<xref:System.Windows.UIElement.Focus%2A>方法上设置焦点<xref:System.Windows.Controls.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="4a531-103">This example shows how to use the <xref:System.Windows.UIElement.Focus%2A> method to set focus on a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a531-104">示例</span><span class="sxs-lookup"><span data-stu-id="4a531-104">Example</span></span>  
 <span data-ttu-id="4a531-105">以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]示例介绍了一个简单<xref:System.Windows.Controls.TextBox>控件名为*tbFocusMe*</span><span class="sxs-lookup"><span data-stu-id="4a531-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example describes a simple <xref:System.Windows.Controls.TextBox> control named *tbFocusMe*</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxFocusXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## <a name="example"></a><span data-ttu-id="4a531-106">示例</span><span class="sxs-lookup"><span data-stu-id="4a531-106">Example</span></span>  
 <span data-ttu-id="4a531-107">下面的示例调用<xref:System.Windows.UIElement.Focus%2A>方法上设置焦点<xref:System.Windows.Controls.TextBox>同名控件*tbFocusMe*。</span><span class="sxs-lookup"><span data-stu-id="4a531-107">The following example calls the <xref:System.Windows.UIElement.Focus%2A> method to set the focus on the <xref:System.Windows.Controls.TextBox> control with the Name *tbFocusMe*.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## <a name="see-also"></a><span data-ttu-id="4a531-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a531-108">See Also</span></span>  
 <xref:System.Windows.UIElement.Focusable%2A>  
 <xref:System.Windows.UIElement.IsFocused%2A>  
 [<span data-ttu-id="4a531-109">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="4a531-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="4a531-110">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="4a531-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
