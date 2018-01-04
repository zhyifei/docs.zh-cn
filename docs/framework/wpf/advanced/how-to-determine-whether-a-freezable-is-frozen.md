---
title: "如何：确定 Freezable 是否处于冻结状态"
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
helpviewer_keywords: Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5eed85f982687bfc90f53e57ab1ec3949820097e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a><span data-ttu-id="921b8-102">如何：确定 Freezable 是否处于冻结状态</span><span class="sxs-lookup"><span data-stu-id="921b8-102">How to: Determine Whether a Freezable Is Frozen</span></span>
<span data-ttu-id="921b8-103">此示例演示如何确定是否<xref:System.Windows.Freezable>对象被冻结。</span><span class="sxs-lookup"><span data-stu-id="921b8-103">This example shows how to determine whether a <xref:System.Windows.Freezable> object is frozen.</span></span> <span data-ttu-id="921b8-104">如果你尝试修改冻结<xref:System.Windows.Freezable>对象，它将引发<xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="921b8-104">If you try to modify a frozen <xref:System.Windows.Freezable> object, it throws an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="921b8-105">若要避免发生此异常，请使用<xref:System.Windows.Freezable.IsFrozen%2A>属性<xref:System.Windows.Freezable>对象以确定是否已被冻结。</span><span class="sxs-lookup"><span data-stu-id="921b8-105">To avoid throwing this exception, use the <xref:System.Windows.Freezable.IsFrozen%2A> property of the <xref:System.Windows.Freezable> object to determine whether it is frozen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="921b8-106">示例</span><span class="sxs-lookup"><span data-stu-id="921b8-106">Example</span></span>  
 <span data-ttu-id="921b8-107">下面的示例会冻结<xref:System.Windows.Media.SolidColorBrush>，然后测试它通过使用<xref:System.Windows.Freezable.IsFrozen%2A>属性来确定是否已被冻结。</span><span class="sxs-lookup"><span data-stu-id="921b8-107">The following example freezes a <xref:System.Windows.Media.SolidColorBrush> and then tests it by using the <xref:System.Windows.Freezable.IsFrozen%2A> property to determine whether it is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="921b8-108">有关详细信息<xref:System.Windows.Freezable>对象，请参阅[可冻结对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="921b8-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="921b8-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="921b8-109">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.IsFrozen%2A>  
 [<span data-ttu-id="921b8-110">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="921b8-110">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="921b8-111">帮助主题</span><span class="sxs-lookup"><span data-stu-id="921b8-111">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
