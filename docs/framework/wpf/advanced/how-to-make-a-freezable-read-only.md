---
title: 如何：使 Freezable 成为只读
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 4185966d864be425bc631953461f6f27ab983bee
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460074"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="7d0e9-102">如何：使 Freezable 成为只读</span><span class="sxs-lookup"><span data-stu-id="7d0e9-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="7d0e9-103">此示例演示如何通过调用其 <xref:System.Windows.Freezable.Freeze%2A> 方法将 <xref:System.Windows.Freezable> 设置为只读。</span><span class="sxs-lookup"><span data-stu-id="7d0e9-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="7d0e9-104">如果以下任一条件 `true` 对象，则不能冻结 <xref:System.Windows.Freezable> 对象：</span><span class="sxs-lookup"><span data-stu-id="7d0e9-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
- <span data-ttu-id="7d0e9-105">它具有动画或数据绑定属性。</span><span class="sxs-lookup"><span data-stu-id="7d0e9-105">It has animated or data bound properties.</span></span>  
  
- <span data-ttu-id="7d0e9-106">它具有由动态资源设置的属性。</span><span class="sxs-lookup"><span data-stu-id="7d0e9-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="7d0e9-107">有关动态资源的详细信息，请参阅[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。</span><span class="sxs-lookup"><span data-stu-id="7d0e9-107">For more information about dynamic resources, see the [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>  
  
- <span data-ttu-id="7d0e9-108">它包含不能冻结 <xref:System.Windows.Freezable> 子对象。</span><span class="sxs-lookup"><span data-stu-id="7d0e9-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="7d0e9-109">如果 `false` <xref:System.Windows.Freezable> 对象的这些条件，并且不打算对其进行修改，请考虑将其冻结以获得性能优势。</span><span class="sxs-lookup"><span data-stu-id="7d0e9-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d0e9-110">示例</span><span class="sxs-lookup"><span data-stu-id="7d0e9-110">Example</span></span>  
 <span data-ttu-id="7d0e9-111">下面的示例将冻结 <xref:System.Windows.Media.SolidColorBrush>，这是 <xref:System.Windows.Freezable> 对象的一种类型。</span><span class="sxs-lookup"><span data-stu-id="7d0e9-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="7d0e9-112">有关 <xref:System.Windows.Freezable> 对象的详细信息，请参阅 "[冻结对象概述](freezable-objects-overview.md)"。</span><span class="sxs-lookup"><span data-stu-id="7d0e9-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d0e9-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d0e9-113">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="7d0e9-114">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="7d0e9-114">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="7d0e9-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="7d0e9-115">How-to Topics</span></span>](base-elements-how-to-topics.md)
