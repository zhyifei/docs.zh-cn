---
title: 如何：获取只读 Freezable 的可写副本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 2853b1e02e1223cbb2b6dff4acbddb0a41d882cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629951"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a><span data-ttu-id="85d56-102">如何：获取只读 Freezable 的可写副本</span><span class="sxs-lookup"><span data-stu-id="85d56-102">How to: Obtain a Writable Copy of a Read-Only Freezable</span></span>
<span data-ttu-id="85d56-103">此示例演示如何使用<xref:System.Windows.Freezable.Clone%2A>方法来创建一个只读的可写副本<xref:System.Windows.Freezable>。</span><span class="sxs-lookup"><span data-stu-id="85d56-103">This example shows how to use the <xref:System.Windows.Freezable.Clone%2A> method to create a writable copy of a read-only <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="85d56-104">之后<xref:System.Windows.Freezable>对象标记为只读的 （"冻结"），您不能修改它。</span><span class="sxs-lookup"><span data-stu-id="85d56-104">After a <xref:System.Windows.Freezable> object is marked as read-only ("frozen"), you cannot modify it.</span></span> <span data-ttu-id="85d56-105">但是，可以使用<xref:System.Windows.Freezable.Clone%2A>方法来创建冻结对象的可修改复本。</span><span class="sxs-lookup"><span data-stu-id="85d56-105">However, you can use the <xref:System.Windows.Freezable.Clone%2A> method to create a modifiable clone of the frozen object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85d56-106">示例</span><span class="sxs-lookup"><span data-stu-id="85d56-106">Example</span></span>  
 <span data-ttu-id="85d56-107">下面的示例创建的冻结的可修改复本<xref:System.Windows.Media.SolidColorBrush>对象。</span><span class="sxs-lookup"><span data-stu-id="85d56-107">The following example creates a modifiable clone of a frozen <xref:System.Windows.Media.SolidColorBrush> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 <span data-ttu-id="85d56-108">有关详细信息<xref:System.Windows.Freezable>对象，请参阅[Freezable 对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="85d56-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85d56-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="85d56-109">See also</span></span>
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [<span data-ttu-id="85d56-110">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="85d56-110">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [<span data-ttu-id="85d56-111">帮助主题</span><span class="sxs-lookup"><span data-stu-id="85d56-111">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
