---
title: "接口（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- interface_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 126e674a2c56f04f54f35a011c24ebf0f713ee8d
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="interface-c-reference"></a><span data-ttu-id="4ab22-102">接口（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="4ab22-102">interface (C# Reference)</span></span>
<span data-ttu-id="4ab22-103">接口只包含[方法](../../../csharp/programming-guide/classes-and-structs/methods.md)、[属性](../../../csharp/programming-guide/classes-and-structs/properties.md)、[事件](../../../csharp/programming-guide/events/index.md)或[索引器](../../../csharp/programming-guide/indexers/index.md)的签名。</span><span class="sxs-lookup"><span data-stu-id="4ab22-103">An interface contains only the signatures of [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [events](../../../csharp/programming-guide/events/index.md) or [indexers](../../../csharp/programming-guide/indexers/index.md).</span></span> <span data-ttu-id="4ab22-104">实现接口的类或结构必须实现接口定义中指定的接口成员。</span><span class="sxs-lookup"><span data-stu-id="4ab22-104">A class or struct that implements the interface must implement the members of the interface that are specified in the interface definition.</span></span> <span data-ttu-id="4ab22-105">在以下示例中，类 `ImplementationClass` 必须实现一个不含参数但返回 `void` 的名为 `SampleMethod` 的方法。</span><span class="sxs-lookup"><span data-stu-id="4ab22-105">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>  
  
 <span data-ttu-id="4ab22-106">有关详细信息和示例，请参阅[接口](../../../csharp/programming-guide/interfaces/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4ab22-106">For more information and examples, see [Interfaces](../../../csharp/programming-guide/interfaces/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ab22-107">示例</span><span class="sxs-lookup"><span data-stu-id="4ab22-107">Example</span></span>  
 <span data-ttu-id="4ab22-108">[!code-cs[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4ab22-108">[!code-cs[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]</span></span>  
  
 <span data-ttu-id="4ab22-109">接口可以是命名空间或类的成员，并且可以包含下列成员的签名：</span><span class="sxs-lookup"><span data-stu-id="4ab22-109">An interface can be a member of a namespace or a class and can contain signatures of the following members:</span></span>  
  
-   [<span data-ttu-id="4ab22-110">方法</span><span class="sxs-lookup"><span data-stu-id="4ab22-110">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [<span data-ttu-id="4ab22-111">属性</span><span class="sxs-lookup"><span data-stu-id="4ab22-111">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [<span data-ttu-id="4ab22-112">索引器</span><span class="sxs-lookup"><span data-stu-id="4ab22-112">Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="4ab22-113">事件</span><span class="sxs-lookup"><span data-stu-id="4ab22-113">Events</span></span>](../../../csharp/language-reference/keywords/event.md)  
  
 <span data-ttu-id="4ab22-114">一个接口可从一个或多个基接口继承。</span><span class="sxs-lookup"><span data-stu-id="4ab22-114">An interface can inherit from one or more base interfaces.</span></span>  
  
 <span data-ttu-id="4ab22-115">基类型列表包含基类和接口时，基类必须是列表中的第 1 项。</span><span class="sxs-lookup"><span data-stu-id="4ab22-115">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>  
  
 <span data-ttu-id="4ab22-116">实现接口的类可以显式实现该接口的成员。</span><span class="sxs-lookup"><span data-stu-id="4ab22-116">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="4ab22-117">显式实现的成员不能通过类实例访问，而只能通过接口实例访问。</span><span class="sxs-lookup"><span data-stu-id="4ab22-117">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span>  
  
 <span data-ttu-id="4ab22-118">有关显式接口实现的更多详细信息和代码示例，请参阅[显式接口实现](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="4ab22-118">For more details and code examples on explicit interface implementation, see [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ab22-119">示例</span><span class="sxs-lookup"><span data-stu-id="4ab22-119">Example</span></span>  
 <span data-ttu-id="4ab22-120">下例演示了接口实现。</span><span class="sxs-lookup"><span data-stu-id="4ab22-120">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="4ab22-121">在此示例中，接口包含属性声明，类包含实现。</span><span class="sxs-lookup"><span data-stu-id="4ab22-121">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="4ab22-122">实现 `IPoint` 的类的任何实例都具有整数属性 `x` 和 `y`。</span><span class="sxs-lookup"><span data-stu-id="4ab22-122">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>  
  
 <span data-ttu-id="4ab22-123">[!code-cs[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4ab22-123">[!code-cs[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4ab22-124">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="4ab22-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4ab22-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ab22-125">See Also</span></span>  
 <span data-ttu-id="4ab22-126">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4ab22-126">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4ab22-127">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4ab22-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4ab22-128">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="4ab22-128">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="4ab22-129">[引用类型](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="4ab22-129">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="4ab22-130">[接口](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="4ab22-130">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 <span data-ttu-id="4ab22-131">[使用属性](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span><span class="sxs-lookup"><span data-stu-id="4ab22-131">[Using Properties](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span></span>  
 <span data-ttu-id="4ab22-132">[使用索引器](../../../csharp/programming-guide/indexers/using-indexers.md) </span><span class="sxs-lookup"><span data-stu-id="4ab22-132">[Using Indexers](../../../csharp/programming-guide/indexers/using-indexers.md) </span></span>  
 <span data-ttu-id="4ab22-133">[类](../../../csharp/language-reference/keywords/class.md) </span><span class="sxs-lookup"><span data-stu-id="4ab22-133">[class](../../../csharp/language-reference/keywords/class.md) </span></span>  
 <span data-ttu-id="4ab22-134">[结构](../../../csharp/language-reference/keywords/struct.md) </span><span class="sxs-lookup"><span data-stu-id="4ab22-134">[struct](../../../csharp/language-reference/keywords/struct.md) </span></span>  
 [<span data-ttu-id="4ab22-135">接口</span><span class="sxs-lookup"><span data-stu-id="4ab22-135">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

