---
title: 如何：确定 Freezable 是否处于冻结状态
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 005bb27803830a2e38a7b143d2c4cff669ad1da6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362508"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a><span data-ttu-id="7e1a4-102">如何：确定 Freezable 是否处于冻结状态</span><span class="sxs-lookup"><span data-stu-id="7e1a4-102">How to: Determine Whether a Freezable Is Frozen</span></span>
<span data-ttu-id="7e1a4-103">此示例演示如何确定是否<xref:System.Windows.Freezable>对象已被冻结。</span><span class="sxs-lookup"><span data-stu-id="7e1a4-103">This example shows how to determine whether a <xref:System.Windows.Freezable> object is frozen.</span></span> <span data-ttu-id="7e1a4-104">如果你尝试修改的冻结<xref:System.Windows.Freezable>对象，它会引发<xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="7e1a4-104">If you try to modify a frozen <xref:System.Windows.Freezable> object, it throws an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="7e1a4-105">若要避免此异常，请使用<xref:System.Windows.Freezable.IsFrozen%2A>属性的<xref:System.Windows.Freezable>对象，以确定是否已被冻结。</span><span class="sxs-lookup"><span data-stu-id="7e1a4-105">To avoid throwing this exception, use the <xref:System.Windows.Freezable.IsFrozen%2A> property of the <xref:System.Windows.Freezable> object to determine whether it is frozen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e1a4-106">示例</span><span class="sxs-lookup"><span data-stu-id="7e1a4-106">Example</span></span>  
 <span data-ttu-id="7e1a4-107">下面的示例冻结<xref:System.Windows.Media.SolidColorBrush>并测试使用<xref:System.Windows.Freezable.IsFrozen%2A>属性来确定是否已被冻结。</span><span class="sxs-lookup"><span data-stu-id="7e1a4-107">The following example freezes a <xref:System.Windows.Media.SolidColorBrush> and then tests it by using the <xref:System.Windows.Freezable.IsFrozen%2A> property to determine whether it is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="7e1a4-108">有关详细信息<xref:System.Windows.Freezable>对象，请参阅[Freezable 对象概述](freezable-objects-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7e1a4-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e1a4-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e1a4-109">See also</span></span>
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [<span data-ttu-id="7e1a4-110">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="7e1a4-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="7e1a4-111">帮助主题</span><span class="sxs-lookup"><span data-stu-id="7e1a4-111">How-to Topics</span></span>](base-elements-how-to-topics.md)
