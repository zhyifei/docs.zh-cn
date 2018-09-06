---
title: 使用 UI 自动化遍历文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, traversing text
- text, traversing
- traversing text
ms.assetid: 3ddb3b7b-1d6b-4dba-8678-5a68e868aadb
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 7353ad142bb276cde1c6fb0ff0c6dcf03b699aeb
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43873795"
---
# <a name="traverse-text-using-ui-automation"></a><span data-ttu-id="4e26f-102">使用 UI 自动化遍历文本</span><span class="sxs-lookup"><span data-stu-id="4e26f-102">Traverse Text Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="4e26f-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="4e26f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4e26f-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="4e26f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="4e26f-105">本主题演示如何使用 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 按 <xref:System.Windows.Automation.Text.TextUnit> 增量来遍历文档的文本内容。</span><span class="sxs-lookup"><span data-stu-id="4e26f-105">This topic shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to traverse the textual content of a document by <xref:System.Windows.Automation.Text.TextUnit> increments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e26f-106">示例</span><span class="sxs-lookup"><span data-stu-id="4e26f-106">Example</span></span>  
 <span data-ttu-id="4e26f-107">下面的代码示例演示如何遍历 UI 自动化文本提供程序的内容。</span><span class="sxs-lookup"><span data-stu-id="4e26f-107">The following code example demonstrates how to traverse the content of a UI Automation text provider.</span></span> <span data-ttu-id="4e26f-108"><xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> 方法将移动 <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> 和 <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> 的 <xref:System.Windows.Automation.Text.TextPatternRange>终结点。</span><span class="sxs-lookup"><span data-stu-id="4e26f-108">The <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> method moves the <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> and <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> endpoints of a <xref:System.Windows.Automation.Text.TextPatternRange>.</span></span> <span data-ttu-id="4e26f-109">此文本范围通常是一个退化范围，表示文本的插入点。</span><span class="sxs-lookup"><span data-stu-id="4e26f-109">This text range is typically a degenerate range representing the text insertion point.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e26f-110">由于只有基于文本的嵌入对象被视为文本流的一部分，因此图像等嵌入对象将不会影响 `Move` 或其返回值。</span><span class="sxs-lookup"><span data-stu-id="4e26f-110">Since only text-based embedded objects are considered part of the text stream, embedded objects such as images do not affect `Move` or its return value.</span></span>  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#Navigate](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#navigate)]
[!code-vb[FindText#Navigate](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#navigate)]  
  
 <span data-ttu-id="4e26f-111">如果控件不支持给定的 <xref:System.Windows.Automation.Text.TextUnit> ，则使用 <xref:System.Windows.Automation.Text.TextUnit> 的所有方法都将推迟到下一个支持的最大 <xref:System.Windows.Automation.Text.TextUnit> 。</span><span class="sxs-lookup"><span data-stu-id="4e26f-111">Any method using <xref:System.Windows.Automation.Text.TextUnit> will defer to the next largest <xref:System.Windows.Automation.Text.TextUnit> supported if the given <xref:System.Windows.Automation.Text.TextUnit> is not supported by the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e26f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e26f-112">See Also</span></span>  
 [<span data-ttu-id="4e26f-113">UI 自动化 TextPattern 概述</span><span class="sxs-lookup"><span data-stu-id="4e26f-113">UI Automation TextPattern Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [<span data-ttu-id="4e26f-114">使用 UI 自动化向文本框添加内容</span><span class="sxs-lookup"><span data-stu-id="4e26f-114">Add Content to a Text Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [<span data-ttu-id="4e26f-115">使用 UI 自动化查找和突出显示文本</span><span class="sxs-lookup"><span data-stu-id="4e26f-115">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)  
 [<span data-ttu-id="4e26f-116">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="4e26f-116">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="4e26f-117">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="4e26f-117">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
