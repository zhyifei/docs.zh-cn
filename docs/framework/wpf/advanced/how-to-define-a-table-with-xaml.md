---
title: "如何：使用 XAML 定义表"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 350dff0b6ea9d92e919e45e4f46cf888f44f6212
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-define-a-table-with-xaml"></a>如何：使用 XAML 定义表
下面的示例演示如何定义<xref:System.Windows.Documents.Table>使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。  示例表有四个列 (由表示<xref:System.Windows.Documents.TableColumn>元素) 和若干行 (由表示<xref:System.Windows.Documents.TableRow>元素) 包含数据以及标题、 页眉和页脚信息。  行必须包含在<xref:System.Windows.Documents.TableRowGroup>元素。  表中的每个行组成一个或多个单元格 (由表示<xref:System.Windows.Documents.TableCell>元素)。  在表格单元格的内容必须包含在<xref:System.Windows.Documents.Block>元素; 在这种情况下<xref:System.Windows.Documents.Paragraph>元素中使用。  表也承载超链接 (由表示<xref:System.Windows.Documents.Hyperlink>元素) 中的页脚行。  
  
## <a name="example"></a>示例  
 [!code-xaml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 下图显示了此示例中定义的表的呈现效果。  
  
 ![呈现的表。](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")
