---
title: 使用 UI 自动化公开表的内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables, exposing content of
- UI Automation, exposing content of tables
- exposing content of tables using UI Automation
ms.assetid: ac3c5eaa-49c7-4653-b83e-532e2a2604a2
ms.openlocfilehash: a9867a07207f825f3f4a781f1c05607fc6b071b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174702"
---
# <a name="expose-the-content-of-a-table-using-ui-automation"></a><span data-ttu-id="c6744-102">使用 UI 自动化公开表的内容</span><span class="sxs-lookup"><span data-stu-id="c6744-102">Expose the Content of a Table Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="c6744-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="c6744-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c6744-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API:UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="c6744-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="c6744-105">本主题说明如何[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]可用于公开表格格式的控件中每个单元格的内容和内部属性。</span><span class="sxs-lookup"><span data-stu-id="c6744-105">This topic shows how [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] can be used to expose the content and intrinsic properties of each cell within a tabular control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6744-106">示例</span><span class="sxs-lookup"><span data-stu-id="c6744-106">Example</span></span>  
 <span data-ttu-id="c6744-107">下面的代码示例演示如何获取<xref:System.Windows.Automation.AutomationElement>表示表格单元格的内容; 也获取单元格属性，如行和列的索引、 行和列间距和行和列的标头信息。</span><span class="sxs-lookup"><span data-stu-id="c6744-107">The following code example demonstrates how to obtain a <xref:System.Windows.Automation.AutomationElement> that represents the content of a table cell; cell properties such as row and column indices, row and column spans, and row and column header information are also obtained.</span></span> <span data-ttu-id="c6744-108">此示例中使用的焦点更改事件处理程序来模拟键盘遍历实现的表格控件[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c6744-108">This example uses a focus change event handler to simulate keyboard traversal of a tabular control that implements [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="c6744-109">每个表项目的信息公开的焦点更改事件。</span><span class="sxs-lookup"><span data-stu-id="c6744-109">Information for each table item is exposed on a focus change event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6744-110">由于焦点更改全局桌面事件，应筛选表外的焦点更改事件。</span><span class="sxs-lookup"><span data-stu-id="c6744-110">Since focus changes are global desktop events, focus change events outside the table should be filtered.</span></span> <span data-ttu-id="c6744-111">请参阅[TrackFocus 示例](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771428(v=vs.90))相关的实现。</span><span class="sxs-lookup"><span data-stu-id="c6744-111">See the [TrackFocus Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771428(v=vs.90)) for a related implementation.</span></span>  
  
 [!code-csharp[UIATableItemPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#starttarget)]
 [!code-vb[UIATableItemPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#starttarget)]  
[!code-csharp[UIATableItemPattern_snip#GetTableElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#gettableelement)]
[!code-vb[UIATableItemPattern_snip#GetTableElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#gettableelement)]  
[!code-csharp[UIATableItemPattern_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#101)]
[!code-vb[UIATableItemPattern_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#101)]  
[!code-csharp[UIATableItemPattern_snip#1015](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#1015)]
[!code-vb[UIATableItemPattern_snip#1015](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#1015)]  
[!code-csharp[UIATableItemPattern_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#102)]
[!code-vb[UIATableItemPattern_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#102)]  
[!code-csharp[UIATableItemPattern_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#103)]
[!code-vb[UIATableItemPattern_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="c6744-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6744-112">See also</span></span>

- [<span data-ttu-id="c6744-113">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="c6744-113">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="c6744-114">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="c6744-114">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="c6744-115">实现 UI 自动化 Table 控件模式</span><span class="sxs-lookup"><span data-stu-id="c6744-115">Implementing the UI Automation Table Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-table-control-pattern.md)
- [<span data-ttu-id="c6744-116">实现 UI 自动化 TableItem 控件模式</span><span class="sxs-lookup"><span data-stu-id="c6744-116">Implementing the UI Automation TableItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-tableitem-control-pattern.md)
- [<span data-ttu-id="c6744-117">实现 UI 自动化 Grid 控件模式</span><span class="sxs-lookup"><span data-stu-id="c6744-117">Implementing the UI Automation Grid Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="c6744-118">实现 UI 自动化 GridItem 控件模式</span><span class="sxs-lookup"><span data-stu-id="c6744-118">Implementing the UI Automation GridItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)
