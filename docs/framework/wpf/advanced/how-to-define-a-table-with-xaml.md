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
---
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="00e16-102">如何：使用 XAML 定义表</span><span class="sxs-lookup"><span data-stu-id="00e16-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="00e16-103">下面的示例演示如何定义<xref:System.Windows.Documents.Table>使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="00e16-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="00e16-104">示例表有四个列 (由表示<xref:System.Windows.Documents.TableColumn>元素) 和若干行 (由表示<xref:System.Windows.Documents.TableRow>元素) 包含数据以及标题、 页眉和页脚信息。</span><span class="sxs-lookup"><span data-stu-id="00e16-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="00e16-105">行必须包含在<xref:System.Windows.Documents.TableRowGroup>元素。</span><span class="sxs-lookup"><span data-stu-id="00e16-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="00e16-106">表中的每个行组成一个或多个单元格 (由表示<xref:System.Windows.Documents.TableCell>元素)。</span><span class="sxs-lookup"><span data-stu-id="00e16-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="00e16-107">在表格单元格的内容必须包含在<xref:System.Windows.Documents.Block>元素; 在这种情况下<xref:System.Windows.Documents.Paragraph>元素中使用。</span><span class="sxs-lookup"><span data-stu-id="00e16-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="00e16-108">表也承载超链接 (由表示<xref:System.Windows.Documents.Hyperlink>元素) 中的页脚行。</span><span class="sxs-lookup"><span data-stu-id="00e16-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00e16-109">示例</span><span class="sxs-lookup"><span data-stu-id="00e16-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="00e16-110">下图显示了此示例中定义的表的呈现效果。</span><span class="sxs-lookup"><span data-stu-id="00e16-110">The following figure shows how the table defined in this example renders.</span></span>  
  
 <span data-ttu-id="00e16-111">![呈现的表。](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")</span><span class="sxs-lookup"><span data-stu-id="00e16-111">![Rendered table.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")</span></span>
