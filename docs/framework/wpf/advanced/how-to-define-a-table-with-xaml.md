---
title: 如何：使用 XAML 定义表
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 011f612527f0c9e89ec05643edbb95b2d908488c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776568"
---
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="eff8c-102">如何：使用 XAML 定义表</span><span class="sxs-lookup"><span data-stu-id="eff8c-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="eff8c-103">下面的示例演示如何定义<xref:System.Windows.Documents.Table>使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="eff8c-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="eff8c-104">示例表有四个列 (由<xref:System.Windows.Documents.TableColumn>元素) 和若干行 (由<xref:System.Windows.Documents.TableRow>元素) 包含数据以及标题、 页眉和页脚信息。</span><span class="sxs-lookup"><span data-stu-id="eff8c-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="eff8c-105">行必须包含在<xref:System.Windows.Documents.TableRowGroup>元素。</span><span class="sxs-lookup"><span data-stu-id="eff8c-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="eff8c-106">表中的每个行组成的一个或多个单元格 (由<xref:System.Windows.Documents.TableCell>元素)。</span><span class="sxs-lookup"><span data-stu-id="eff8c-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="eff8c-107">在表单元的内容必须包含在<xref:System.Windows.Documents.Block>元素; 在这种情况下<xref:System.Windows.Documents.Paragraph>使用元素。</span><span class="sxs-lookup"><span data-stu-id="eff8c-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="eff8c-108">该表还承载一个超链接 (由<xref:System.Windows.Documents.Hyperlink>元素) 中的脚注行。</span><span class="sxs-lookup"><span data-stu-id="eff8c-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eff8c-109">示例</span><span class="sxs-lookup"><span data-stu-id="eff8c-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="eff8c-110">下图显示了在此示例中定义的表的呈现效果：</span><span class="sxs-lookup"><span data-stu-id="eff8c-110">The following figure shows how the table defined in this example renders:</span></span>  
  
 ![使用 XAML 定义的表的屏幕截图。](./media/how-to-define-a-table-with-xaml/planetary-information-xaml-table.png)
