---
title: 如何：从 TextBox 获取线条集合
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: 64187527da3cfb97343e2036338822d479dd997a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552735"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a><span data-ttu-id="cbf39-102">如何：从 TextBox 获取线条集合</span><span class="sxs-lookup"><span data-stu-id="cbf39-102">How to: Get a Collection of Lines from a TextBox</span></span>
<span data-ttu-id="cbf39-103">此示例演示如何获取的从文本的行集合<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="cbf39-103">This example shows how to get a collection of lines of text from a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbf39-104">示例</span><span class="sxs-lookup"><span data-stu-id="cbf39-104">Example</span></span>  
 <span data-ttu-id="cbf39-105">下面的示例演示一个简单的方法，采用<xref:System.Windows.Controls.TextBox>作为自变量，并返回<xref:System.Collections.Specialized.StringCollection>包含中的文本行**文本框中**。</span><span class="sxs-lookup"><span data-stu-id="cbf39-105">The following example shows a simple method that takes a <xref:System.Windows.Controls.TextBox> as the argument, and returns a <xref:System.Collections.Specialized.StringCollection> containing the lines of text in the **TextBox**.</span></span>  <span data-ttu-id="cbf39-106"><xref:System.Windows.Controls.TextBox.LineCount%2A>属性用于确定多少行是当前处于**文本框中**，和<xref:System.Windows.Controls.TextBox.GetLineText%2A>方法然后用于提取每个行并将其添加到的行的集合。</span><span class="sxs-lookup"><span data-stu-id="cbf39-106">The <xref:System.Windows.Controls.TextBox.LineCount%2A> property is used to determine how many lines are currently in the **TextBox**, and the <xref:System.Windows.Controls.TextBox.GetLineText%2A> method is then used to extract each line and add it to the collection of lines.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a><span data-ttu-id="cbf39-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="cbf39-107">See Also</span></span>  
 [<span data-ttu-id="cbf39-108">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="cbf39-108">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="cbf39-109">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="cbf39-109">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
