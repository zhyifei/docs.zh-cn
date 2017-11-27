---
title: "如何：使用 FlowDocument 列分隔特性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7e4a300acccd0c6915844c988a4bbc81426f90f0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a>如何：使用 FlowDocument 列分隔特性
此示例演示如何使用的列分隔功能<xref:System.Windows.Documents.FlowDocument>。  
  
## <a name="example"></a>示例  
 下面的示例定义<xref:System.Windows.Documents.FlowDocument>，并将设置<xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>， <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>，和<xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A>属性。  <xref:System.Windows.Documents.FlowDocument>包含一段的示例内容。  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 下图显示的效果<xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>， <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>，和<xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A>特性在所呈现<xref:System.Windows.Documents.FlowDocument>。  
  
 ![屏幕快照： FlowDocument Intra 列](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")
