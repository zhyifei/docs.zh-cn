---
title: 如何：处理 Loaded 事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: b8cd2f5e9d848cebb712e7b4930ca39efe48ecc0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122546"
---
# <a name="how-to-handle-a-loaded-event"></a><span data-ttu-id="d34f9-102">如何：处理 Loaded 事件</span><span class="sxs-lookup"><span data-stu-id="d34f9-102">How to: Handle a Loaded Event</span></span>
<span data-ttu-id="d34f9-103">此示例演示如何处理<xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType>事件，并处理该事件的适当的方案。</span><span class="sxs-lookup"><span data-stu-id="d34f9-103">This example shows how to handle the <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> event, and an appropriate scenario for handling that event.</span></span> <span data-ttu-id="d34f9-104">该处理程序创建<xref:System.Windows.Controls.Button>加载页面时。</span><span class="sxs-lookup"><span data-stu-id="d34f9-104">The handler  creates a <xref:System.Windows.Controls.Button> when the page loads.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d34f9-105">示例</span><span class="sxs-lookup"><span data-stu-id="d34f9-105">Example</span></span>  
 <span data-ttu-id="d34f9-106">下面的示例使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]以及代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="d34f9-106">The following example uses [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] together with a code-behind file.</span></span>  
  
 [!code-xaml[FELoaded#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="d34f9-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="d34f9-107">See also</span></span>

- <xref:System.Windows.FrameworkElement>
- [<span data-ttu-id="d34f9-108">对象生存期事件</span><span class="sxs-lookup"><span data-stu-id="d34f9-108">Object Lifetime Events</span></span>](object-lifetime-events.md)
- [<span data-ttu-id="d34f9-109">路由事件概述</span><span class="sxs-lookup"><span data-stu-id="d34f9-109">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="d34f9-110">帮助主题</span><span class="sxs-lookup"><span data-stu-id="d34f9-110">How-to Topics</span></span>](base-elements-how-to-topics.md)
