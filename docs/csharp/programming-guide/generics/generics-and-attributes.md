---
title: 泛型和属性 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 99a24a7069145dfad5ce6c9c91f2a8653eb9a224
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589638"
---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="85a40-102">泛型和特性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="85a40-102">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="85a40-103">属性可按与非泛型类型相同的方式应用到泛型类型。</span><span class="sxs-lookup"><span data-stu-id="85a40-103">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="85a40-104">有关应用特性的详细信息，请参阅[属性](../concepts/attributes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="85a40-104">For more information on applying attributes, see [Attributes](../concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="85a40-105">仅允许自定义属性引用开放式泛型类型（即未向其提供任何类型参数的泛型类型）和封闭式构造泛型类型（即向所有类型参数提供参数的泛型类型）。</span><span class="sxs-lookup"><span data-stu-id="85a40-105">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="85a40-106">以下示例使用此自定义属性：</span><span class="sxs-lookup"><span data-stu-id="85a40-106">The following examples use this custom attribute:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#48](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#48)]  
  
 <span data-ttu-id="85a40-107">属性可引用开放式泛型类型：</span><span class="sxs-lookup"><span data-stu-id="85a40-107">An attribute can reference an open generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#49](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#49)]  
  
 <span data-ttu-id="85a40-108">通过使用适当数量的逗号指定多个类型参数。</span><span class="sxs-lookup"><span data-stu-id="85a40-108">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="85a40-109">在此示例中，`GenericClass2` 具有两个类型参数：</span><span class="sxs-lookup"><span data-stu-id="85a40-109">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#50)]  
  
 <span data-ttu-id="85a40-110">属性可引用封闭式构造泛型类型：</span><span class="sxs-lookup"><span data-stu-id="85a40-110">An attribute can reference a closed constructed generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#51)]  
  
 <span data-ttu-id="85a40-111">引用泛型类型参数的属性会导致编译时错误：</span><span class="sxs-lookup"><span data-stu-id="85a40-111">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#52](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#52)]  
  
 <span data-ttu-id="85a40-112">不能从<xref:System.Attribute>继承泛型类型：</span><span class="sxs-lookup"><span data-stu-id="85a40-112">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#53)]  
  
 <span data-ttu-id="85a40-113">若要在运行时获取有关泛型类型或类型参数的信息，可使用 <xref:System.Reflection> 方法。</span><span class="sxs-lookup"><span data-stu-id="85a40-113">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="85a40-114">有关详细信息，请参阅[泛型和反射](./generics-and-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="85a40-114">For more information, see [Generics and Reflection](./generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85a40-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="85a40-115">See also</span></span>

- [<span data-ttu-id="85a40-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="85a40-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="85a40-117">泛型</span><span class="sxs-lookup"><span data-stu-id="85a40-117">Generics</span></span>](./index.md)
- [<span data-ttu-id="85a40-118">特性</span><span class="sxs-lookup"><span data-stu-id="85a40-118">Attributes</span></span>](../../../standard/attributes/index.md)
