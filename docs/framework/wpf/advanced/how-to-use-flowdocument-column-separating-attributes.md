---
title: 如何：使用 FlowDocument 列分隔特性
ms.date: 03/30/2017
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
ms.openlocfilehash: 678e01a35c286ea03f0385291d64f2f900f068c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543766"
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a><span data-ttu-id="aaca7-102">如何：使用 FlowDocument 列分隔特性</span><span class="sxs-lookup"><span data-stu-id="aaca7-102">How to: Use FlowDocument Column-Separating Attributes</span></span>
<span data-ttu-id="aaca7-103">此示例演示如何使用的列分隔功能<xref:System.Windows.Documents.FlowDocument>。</span><span class="sxs-lookup"><span data-stu-id="aaca7-103">This example shows how to use the column-separating features of a <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaca7-104">示例</span><span class="sxs-lookup"><span data-stu-id="aaca7-104">Example</span></span>  
 <span data-ttu-id="aaca7-105">下面的示例定义<xref:System.Windows.Documents.FlowDocument>，并将设置<xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>， <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>，和<xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="aaca7-105">The following example defines a <xref:System.Windows.Documents.FlowDocument>, and sets the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes.</span></span>  <span data-ttu-id="aaca7-106"><xref:System.Windows.Documents.FlowDocument>包含一段的示例内容。</span><span class="sxs-lookup"><span data-stu-id="aaca7-106">The <xref:System.Windows.Documents.FlowDocument> contains a single paragraph of sample content.</span></span>  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 <span data-ttu-id="aaca7-107">下图显示的效果<xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>， <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>，和<xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A>特性在所呈现<xref:System.Windows.Documents.FlowDocument>。</span><span class="sxs-lookup"><span data-stu-id="aaca7-107">The following figure shows the effects of the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes in a rendered <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="aaca7-108">![屏幕快照： FlowDocument Intra 列](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")</span><span class="sxs-lookup"><span data-stu-id="aaca7-108">![Screenshot: FlowDocument Intra Column](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")</span></span>
