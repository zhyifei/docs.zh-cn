---
title: 如何：以编程方式更改内容的 FlowDirection
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
ms.openlocfilehash: ec159ed0efce8b5514788331e8715a55e7a8a638
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776553"
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a><span data-ttu-id="76df8-102">如何：以编程方式更改内容的 FlowDirection</span><span class="sxs-lookup"><span data-stu-id="76df8-102">How to: Change the FlowDirection of Content Programmatically</span></span>
<span data-ttu-id="76df8-103">此示例演示如何以编程方式更改<xref:System.Windows.FrameworkElement.FlowDirection%2A>属性的<xref:System.Windows.Controls.FlowDocumentReader>。</span><span class="sxs-lookup"><span data-stu-id="76df8-103">This example shows how to programmatically change the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property of a <xref:System.Windows.Controls.FlowDocumentReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76df8-104">示例</span><span class="sxs-lookup"><span data-stu-id="76df8-104">Example</span></span>  
 <span data-ttu-id="76df8-105">两个<xref:System.Windows.Controls.Button>元素创建的每个资源表示的可能值之一<xref:System.Windows.FlowDirection>。</span><span class="sxs-lookup"><span data-stu-id="76df8-105">Two <xref:System.Windows.Controls.Button> elements are created, each representing one of the possible values of <xref:System.Windows.FlowDirection>.</span></span> <span data-ttu-id="76df8-106">单击按钮时，关联的属性值应用于的内容<xref:System.Windows.Controls.FlowDocumentReader>名为`tf1`。</span><span class="sxs-lookup"><span data-stu-id="76df8-106">When a button is clicked, the associated property value is applied to the contents of a <xref:System.Windows.Controls.FlowDocumentReader> named `tf1`.</span></span>  <span data-ttu-id="76df8-107">属性值也写入到<xref:System.Windows.Controls.TextBlock>名为`txt1`。</span><span class="sxs-lookup"><span data-stu-id="76df8-107">The property value is also written to a <xref:System.Windows.Controls.TextBlock> named `txt1`.</span></span>  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a><span data-ttu-id="76df8-108">示例</span><span class="sxs-lookup"><span data-stu-id="76df8-108">Example</span></span>  
 <span data-ttu-id="76df8-109">与上述按钮单击事件处理中C#代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="76df8-109">The events associated with the button clicks defined above are handled in a C# code-behind file.</span></span>  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
