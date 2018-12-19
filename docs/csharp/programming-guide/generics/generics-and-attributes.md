---
title: 泛型和属性 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 35244ce33902760c2a0d3d8bda3181097f7ca38e
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245176"
---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="99bcf-102">泛型和特性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="99bcf-102">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="99bcf-103">属性可按与非泛型类型相同的方式应用到泛型类型。</span><span class="sxs-lookup"><span data-stu-id="99bcf-103">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="99bcf-104">有关应用特性的详细信息，请参阅[属性](../../../csharp/programming-guide/concepts/attributes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="99bcf-104">For more information on applying attributes, see [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="99bcf-105">仅允许自定义属性引用开放式泛型类型（即未向其提供任何类型参数的泛型类型）和封闭式构造泛型类型（即向所有类型参数提供参数的泛型类型）。</span><span class="sxs-lookup"><span data-stu-id="99bcf-105">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="99bcf-106">以下示例使用此自定义属性：</span><span class="sxs-lookup"><span data-stu-id="99bcf-106">The following examples use this custom attribute:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]  
  
 <span data-ttu-id="99bcf-107">属性可引用开放式泛型类型：</span><span class="sxs-lookup"><span data-stu-id="99bcf-107">An attribute can reference an open generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]  
  
 <span data-ttu-id="99bcf-108">通过使用适当数量的逗号指定多个类型参数。</span><span class="sxs-lookup"><span data-stu-id="99bcf-108">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="99bcf-109">在此示例中，`GenericClass2` 具有两个类型参数：</span><span class="sxs-lookup"><span data-stu-id="99bcf-109">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]  
  
 <span data-ttu-id="99bcf-110">属性可引用封闭式构造泛型类型：</span><span class="sxs-lookup"><span data-stu-id="99bcf-110">An attribute can reference a closed constructed generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]  
  
 <span data-ttu-id="99bcf-111">引用泛型类型参数的属性会导致编译时错误：</span><span class="sxs-lookup"><span data-stu-id="99bcf-111">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]  
  
 <span data-ttu-id="99bcf-112">不能从<xref:System.Attribute>继承泛型类型：</span><span class="sxs-lookup"><span data-stu-id="99bcf-112">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]  
  
 <span data-ttu-id="99bcf-113">若要在运行时获取有关泛型类型或类型参数的信息，可使用 <xref:System.Reflection> 方法。</span><span class="sxs-lookup"><span data-stu-id="99bcf-113">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="99bcf-114">有关详细信息，请参阅[泛型和反射](../../../csharp/programming-guide/generics/generics-and-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="99bcf-114">For more information, see [Generics and Reflection](../../../csharp/programming-guide/generics/generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99bcf-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="99bcf-115">See Also</span></span>

- [<span data-ttu-id="99bcf-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="99bcf-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="99bcf-117">泛型</span><span class="sxs-lookup"><span data-stu-id="99bcf-117">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)  
- [<span data-ttu-id="99bcf-118">特性</span><span class="sxs-lookup"><span data-stu-id="99bcf-118">Attributes</span></span>](../../../../docs/standard/attributes/index.md)
