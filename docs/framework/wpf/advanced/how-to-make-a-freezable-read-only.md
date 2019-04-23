---
title: 如何：将 Freezable 设为只读
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 9b7102db4de0df7183355e50e3b372eac30d81b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191429"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="28e65-102">如何：将 Freezable 设为只读</span><span class="sxs-lookup"><span data-stu-id="28e65-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="28e65-103">此示例演示如何使<xref:System.Windows.Freezable>只读通过调用其<xref:System.Windows.Freezable.Freeze%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="28e65-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="28e65-104">不能冻结<xref:System.Windows.Freezable>对象是否满足以下条件之一`true`有关对象：</span><span class="sxs-lookup"><span data-stu-id="28e65-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
-   <span data-ttu-id="28e65-105">它具有经过动画处理或数据绑定属性。</span><span class="sxs-lookup"><span data-stu-id="28e65-105">It has animated or data bound properties.</span></span>  
  
-   <span data-ttu-id="28e65-106">它具有由动态资源设置的属性。</span><span class="sxs-lookup"><span data-stu-id="28e65-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="28e65-107">有关动态资源的详细信息，请参阅[XAML 资源](xaml-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="28e65-107">For more information about dynamic resources, see the [XAML Resources](xaml-resources.md).</span></span>  
  
-   <span data-ttu-id="28e65-108">它包含<xref:System.Windows.Freezable>不能冻结的子对象。</span><span class="sxs-lookup"><span data-stu-id="28e65-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="28e65-109">如果这些条件`false`为你<xref:System.Windows.Freezable>对象，并且您不想要对其进行修改，请考虑冻结它来获得性能优势。</span><span class="sxs-lookup"><span data-stu-id="28e65-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28e65-110">示例</span><span class="sxs-lookup"><span data-stu-id="28e65-110">Example</span></span>  
 <span data-ttu-id="28e65-111">下面的示例冻结<xref:System.Windows.Media.SolidColorBrush>，这是一种类型的<xref:System.Windows.Freezable>对象。</span><span class="sxs-lookup"><span data-stu-id="28e65-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="28e65-112">有关详细信息<xref:System.Windows.Freezable>对象，请参阅[Freezable 对象概述](freezable-objects-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="28e65-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28e65-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="28e65-113">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="28e65-114">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="28e65-114">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="28e65-115">帮助主题</span><span class="sxs-lookup"><span data-stu-id="28e65-115">How-to Topics</span></span>](base-elements-how-to-topics.md)
