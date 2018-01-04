---
title: "如何：使用流内容元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e637e114187d0864afe4211a45c346c1e5a449b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="405fa-102">如何：使用流内容元素</span><span class="sxs-lookup"><span data-stu-id="405fa-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="405fa-103">下面的示例演示各种流内容元素及其相关联特性的声明性用法。</span><span class="sxs-lookup"><span data-stu-id="405fa-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="405fa-104">演示的元素和特性包括：</span><span class="sxs-lookup"><span data-stu-id="405fa-104">Elements and attributes demonstrated include:</span></span>  
  
-   <span data-ttu-id="405fa-105"><xref:System.Windows.Documents.Bold> 元素</span><span class="sxs-lookup"><span data-stu-id="405fa-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
-   <span data-ttu-id="405fa-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> 特性</span><span class="sxs-lookup"><span data-stu-id="405fa-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
-   <span data-ttu-id="405fa-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> 特性</span><span class="sxs-lookup"><span data-stu-id="405fa-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
-   <span data-ttu-id="405fa-108"><xref:System.Windows.Documents.Italic> 元素</span><span class="sxs-lookup"><span data-stu-id="405fa-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
-   <span data-ttu-id="405fa-109"><xref:System.Windows.Documents.LineBreak> 元素</span><span class="sxs-lookup"><span data-stu-id="405fa-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
-   <span data-ttu-id="405fa-110"><xref:System.Windows.Documents.List> 元素</span><span class="sxs-lookup"><span data-stu-id="405fa-110"><xref:System.Windows.Documents.List> element</span></span>  
  
-   <span data-ttu-id="405fa-111"><xref:System.Windows.Documents.ListItem> 元素</span><span class="sxs-lookup"><span data-stu-id="405fa-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
-   <span data-ttu-id="405fa-112"><xref:System.Windows.Documents.Paragraph> 元素</span><span class="sxs-lookup"><span data-stu-id="405fa-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
-   <span data-ttu-id="405fa-113"><xref:System.Windows.Documents.Run> 元素</span><span class="sxs-lookup"><span data-stu-id="405fa-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
-   <span data-ttu-id="405fa-114"><xref:System.Windows.Documents.Section> 元素</span><span class="sxs-lookup"><span data-stu-id="405fa-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
-   <span data-ttu-id="405fa-115"><xref:System.Windows.Documents.Span> 元素</span><span class="sxs-lookup"><span data-stu-id="405fa-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
-   <span data-ttu-id="405fa-116"><xref:System.Windows.Documents.Typography.Variants%2A>属性 （上标和下标）</span><span class="sxs-lookup"><span data-stu-id="405fa-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
-   <span data-ttu-id="405fa-117"><xref:System.Windows.Documents.Underline> 元素</span><span class="sxs-lookup"><span data-stu-id="405fa-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="405fa-118">示例</span><span class="sxs-lookup"><span data-stu-id="405fa-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
