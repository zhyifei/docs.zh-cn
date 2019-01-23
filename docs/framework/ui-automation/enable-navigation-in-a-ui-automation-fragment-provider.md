---
title: 在 UI 自动化片段提供程序中启用导航
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, enabling navigation in provider
- navigation, enabling in UI Automation provider
ms.assetid: 3cb6092a-58c9-4ca0-84a5-0e54d5d00a0d
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: b920fbd118dd3757976a0fc48c42a0bb6dd97c6b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495212"
---
# <a name="enable-navigation-in-a-ui-automation-fragment-provider"></a><span data-ttu-id="844dc-102">在 UI 自动化片段提供程序中启用导航</span><span class="sxs-lookup"><span data-stu-id="844dc-102">Enable Navigation in a UI Automation Fragment Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="844dc-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="844dc-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="844dc-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API:UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="844dc-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="844dc-105">本主题包含示例代码，该示例代码演示如何为片段中的元素启用在 UI 自动化提供程序中导航的功能。</span><span class="sxs-lookup"><span data-stu-id="844dc-105">This topic contains example code that shows how to enable navigation in a UI Automation provider for an element that is within a fragment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="844dc-106">示例</span><span class="sxs-lookup"><span data-stu-id="844dc-106">Example</span></span>  
 <span data-ttu-id="844dc-107">下面的示例代码为列表中的列表项实现 <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A></span><span class="sxs-lookup"><span data-stu-id="844dc-107">The following example code implements <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> for a list item within a list.</span></span> <span data-ttu-id="844dc-108">父元素是列表框元素，且同级元素是列表集合中的其他项。</span><span class="sxs-lookup"><span data-stu-id="844dc-108">The parent element is the list box element, and the sibling elements are other items in the list collection.</span></span> <span data-ttu-id="844dc-109">对于无效的方向，该方法返回 `null` （在 Visual Basic 中则返回`Nothing` ）；在本例中，将返回 <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> 和 <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>，因为该元素没有任何子级。</span><span class="sxs-lookup"><span data-stu-id="844dc-109">The method returns `null` (`Nothing` in Visual Basic) for directions that are not valid; in this case, <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> and <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>, because the element has no children.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListItemFragment.cs#103)]
 [!code-vb[UIAFragmentProvider_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListItemFragment.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="844dc-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="844dc-110">See also</span></span>
- [<span data-ttu-id="844dc-111">UI 自动化提供程序概述</span><span class="sxs-lookup"><span data-stu-id="844dc-111">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="844dc-112">服务器端 UI 自动化提供程序实现</span><span class="sxs-lookup"><span data-stu-id="844dc-112">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
