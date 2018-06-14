---
title: 如何：使用 XAML 定义表
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 2a35a27567d962fc125cb3c408ccab95afa222af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543096"
---
# <a name="how-to-define-a-table-with-xaml"></a>如何：使用 XAML 定义表
下面的示例演示如何定义<xref:System.Windows.Documents.Table>使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。  示例表有四个列 (由表示<xref:System.Windows.Documents.TableColumn>元素) 和若干行 (由表示<xref:System.Windows.Documents.TableRow>元素) 包含数据以及标题、 页眉和页脚信息。  行必须包含在<xref:System.Windows.Documents.TableRowGroup>元素。  表中的每个行组成一个或多个单元格 (由表示<xref:System.Windows.Documents.TableCell>元素)。  在表格单元格的内容必须包含在<xref:System.Windows.Documents.Block>元素; 在这种情况下<xref:System.Windows.Documents.Paragraph>元素中使用。  表也承载超链接 (由表示<xref:System.Windows.Documents.Hyperlink>元素) 中的页脚行。  
  
## <a name="example"></a>示例  
 [!code-xaml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 下图显示了此示例中定义的表的呈现效果。  
  
 ![呈现的表。](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")
