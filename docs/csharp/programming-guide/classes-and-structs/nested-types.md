---
title: 嵌套类型 - C# 编程指南
ms.custom: seodec18
ms.date: 07/10/2017
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 7269f925b3fc78eea04249984697899b1997c3fb
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976702"
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="4c25e-102">嵌套类型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="4c25e-102">Nested Types (C# Programming Guide)</span></span>
<span data-ttu-id="4c25e-103">在[类](../../../csharp/language-reference/keywords/class.md)或[构造](../../../csharp/language-reference/keywords/struct.md)中定义的类型称为嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="4c25e-103">A type defined within a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is called a nested type.</span></span> <span data-ttu-id="4c25e-104">例如:</span><span class="sxs-lookup"><span data-stu-id="4c25e-104">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#68](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#68)]  
  
<span data-ttu-id="4c25e-105">不论外部类型是类还是构造，嵌套类型均默认为 [private](../../../csharp/language-reference/keywords/private.md)；仅可从其包含类型中进行访问。</span><span class="sxs-lookup"><span data-stu-id="4c25e-105">Regardless of whether the outer type is a class or a struct, nested types default to [private](../../../csharp/language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="4c25e-106">在上一个示例中，`Nested` 类无法访问外部类型。</span><span class="sxs-lookup"><span data-stu-id="4c25e-106">In the previous example, the `Nested` class is inaccessible to external types.</span></span> 

<span data-ttu-id="4c25e-107">还可指定[访问修饰符](../../language-reference/keywords/access-modifiers.md)来定义嵌套类型的可访问性，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4c25e-107">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="4c25e-108">“类”的嵌套类型可以是 [public](../../../csharp/language-reference/keywords/public.md)、[protected](../../../csharp/language-reference/keywords/protected.md)、[internal](../../../csharp/language-reference/keywords/internal.md)、[protected internal](../../../csharp/language-reference/keywords/protected-internal.md)、[private](../../../csharp/language-reference/keywords/private.md) 或 [private protected](../../../csharp/language-reference/keywords/private-protected.md)。</span><span class="sxs-lookup"><span data-stu-id="4c25e-108">Nested types of a **class** can be [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md), [private](../../../csharp/language-reference/keywords/private.md) or [private protected](../../../csharp/language-reference/keywords/private-protected.md).</span></span> 

   <span data-ttu-id="4c25e-109">但是，在[密封类](../../language-reference/keywords/sealed.md)中定义 `protected`、`protected internal` 或 `private protected` 嵌套类将产生编译器警告 [CS0628](../../misc/cs0628.md)“封闭类汇中声明了新的受保护成员”。</span><span class="sxs-lookup"><span data-stu-id="4c25e-109">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="4c25e-110">构造的嵌套类型可以是 [public](../../../csharp/language-reference/keywords/public.md)、[internal](../../../csharp/language-reference/keywords/internal.md) 或 [private](../../../csharp/language-reference/keywords/private.md)。</span><span class="sxs-lookup"><span data-stu-id="4c25e-110">Nested types of a **struct** can be [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md).</span></span>
  
<span data-ttu-id="4c25e-111">以下示例使 `Nested` 类为 public：</span><span class="sxs-lookup"><span data-stu-id="4c25e-111">The following example makes the `Nested` class public:</span></span>
  
 [!code-csharp[csProgGuideObjects#69](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#69)]  
  
 <span data-ttu-id="4c25e-112">嵌套类型（或内部类型）可访问包含类型（或外部类型）。</span><span class="sxs-lookup"><span data-stu-id="4c25e-112">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="4c25e-113">若要访问包含类型，请将其作为参数传递给嵌套类型的构造函数。</span><span class="sxs-lookup"><span data-stu-id="4c25e-113">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="4c25e-114">例如:</span><span class="sxs-lookup"><span data-stu-id="4c25e-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#70](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#70)]  
  
 <span data-ttu-id="4c25e-115">嵌套类型可以访问其包含类型可以访问的所有成员。</span><span class="sxs-lookup"><span data-stu-id="4c25e-115">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="4c25e-116">它可以访问包含类型的私有成员和受保护成员（包括所有继承的受保护成员）。</span><span class="sxs-lookup"><span data-stu-id="4c25e-116">It can access private and protected members of the containing type, including any inherited protected members.</span></span>  
  
 <span data-ttu-id="4c25e-117">在前面的声明中，类 `Nested` 的完整名称为 `Container.Nested`。</span><span class="sxs-lookup"><span data-stu-id="4c25e-117">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="4c25e-118">这是用来创建嵌套类新实例的名称，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4c25e-118">This is the name used to create a new instance of the nested class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#71](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#71)]  
  
## <a name="see-also"></a><span data-ttu-id="4c25e-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c25e-119">See also</span></span>

- [<span data-ttu-id="4c25e-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="4c25e-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="4c25e-121">类和结构</span><span class="sxs-lookup"><span data-stu-id="4c25e-121">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="4c25e-122">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="4c25e-122">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="4c25e-123">构造函数</span><span class="sxs-lookup"><span data-stu-id="4c25e-123">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
