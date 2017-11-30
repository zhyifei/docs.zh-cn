---
title: "如何：使 Freezable 成为只读"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c407a2fcccfbda29ba23f63ba6ae71302c734d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="350b2-102">如何：使 Freezable 成为只读</span><span class="sxs-lookup"><span data-stu-id="350b2-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="350b2-103">此示例演示如何使<xref:System.Windows.Freezable>只读通过调用其<xref:System.Windows.Freezable.Freeze%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="350b2-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="350b2-104">不能冻结<xref:System.Windows.Freezable>对象如果以下情况中的任何一个为`true`有关对象：</span><span class="sxs-lookup"><span data-stu-id="350b2-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
-   <span data-ttu-id="350b2-105">它具有经过动画处理或数据绑定属性。</span><span class="sxs-lookup"><span data-stu-id="350b2-105">It has animated or data bound properties.</span></span>  
  
-   <span data-ttu-id="350b2-106">它具有由动态资源设置的属性。</span><span class="sxs-lookup"><span data-stu-id="350b2-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="350b2-107">有关动态资源的详细信息，请参阅[XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="350b2-107">For more information about dynamic resources, see the [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
-   <span data-ttu-id="350b2-108">它包含<xref:System.Windows.Freezable>无法冻结的子对象。</span><span class="sxs-lookup"><span data-stu-id="350b2-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="350b2-109">如果这些条件是`false`为你<xref:System.Windows.Freezable>对象，并且您不想要对其进行修改，请考虑冻结它以获得性能优势。</span><span class="sxs-lookup"><span data-stu-id="350b2-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="350b2-110">示例</span><span class="sxs-lookup"><span data-stu-id="350b2-110">Example</span></span>  
 <span data-ttu-id="350b2-111">下面的示例会冻结<xref:System.Windows.Media.SolidColorBrush>，这是一种<xref:System.Windows.Freezable>对象。</span><span class="sxs-lookup"><span data-stu-id="350b2-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="350b2-112">有关详细信息<xref:System.Windows.Freezable>对象，请参阅[可冻结对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="350b2-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="350b2-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="350b2-113">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CanFreeze%2A>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [<span data-ttu-id="350b2-114">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="350b2-114">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="350b2-115">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="350b2-115">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
