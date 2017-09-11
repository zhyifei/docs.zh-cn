---
title: "索引器（C# 编程指南）"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.indexers
dev_langs:
- CSharp
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
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
ms.openlocfilehash: 784308f3073114cd0c07cf15edae527a2654edec
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="cf311-102">索引器（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="cf311-102">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="cf311-103">索引器允许类或结构的实例就像数组一样进行索引。</span><span class="sxs-lookup"><span data-stu-id="cf311-103">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="cf311-104">无需显式指定类型或实例成员，即可设置或检索索引值。</span><span class="sxs-lookup"><span data-stu-id="cf311-104">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="cf311-105">索引器类似于[属性](../../../csharp/programming-guide/classes-and-structs/properties.md)，不同之处在于它们的访问器需要使用参数。</span><span class="sxs-lookup"><span data-stu-id="cf311-105">Indexers resemble [properties](../../../csharp/programming-guide/classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  
 
 <span data-ttu-id="cf311-106">以下示例定义了一个泛型类，其中包含用于赋值和检索值的简单 [get](../../../csharp/language-reference/keywords/get.md) 和 [set](../../../csharp/language-reference/keywords/set.md) 访问器方法。</span><span class="sxs-lookup"><span data-stu-id="cf311-106">The following example defines a generic class with simple [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="cf311-107">`Program` 类创建了此类的一个实例，用于存储字符串。</span><span class="sxs-lookup"><span data-stu-id="cf311-107">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 <span data-ttu-id="cf311-108">[!code-cs[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="cf311-108">[!code-cs[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf311-109">有关更多示例，请参阅[相关部分](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections)。</span><span class="sxs-lookup"><span data-stu-id="cf311-109">For more examples, see [Related Sections](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="cf311-110">表达式主体定义</span><span class="sxs-lookup"><span data-stu-id="cf311-110">Expression Body Definitions</span></span>  
 
<span data-ttu-id="cf311-111">索引器的 get 或 set 访问器包含一个用于返回或设置值的语句很常见。</span><span class="sxs-lookup"><span data-stu-id="cf311-111">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="cf311-112">为了支持这种情况，表达式主体成员提供了一种经过简化的语法。</span><span class="sxs-lookup"><span data-stu-id="cf311-112">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="cf311-113">自 C# 6 起，可以表达式主体成员的形式实现只读索引器，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="cf311-113">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

<span data-ttu-id="cf311-114">[!code-cs[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="cf311-114">[!code-cs[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]</span></span>  

<span data-ttu-id="cf311-115">请注意，`=>` 引入了表达式主体，并未使用 `get` 关键字。</span><span class="sxs-lookup"><span data-stu-id="cf311-115">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span> 

<span data-ttu-id="cf311-116">自 C# 7 起，get 和 set 访问器均可作为表达式主体成员实现。</span><span class="sxs-lookup"><span data-stu-id="cf311-116">Starting with C# 7, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="cf311-117">在这种情况下，必须使用 `get` 和 `set` 关键字。</span><span class="sxs-lookup"><span data-stu-id="cf311-117">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="cf311-118">例如: </span><span class="sxs-lookup"><span data-stu-id="cf311-118">For example:</span></span>

<span data-ttu-id="cf311-119">[!code-cs[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="cf311-119">[!code-cs[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]</span></span>  
  
## <a name="indexers-overview"></a><span data-ttu-id="cf311-120">索引器概述</span><span class="sxs-lookup"><span data-stu-id="cf311-120">Indexers Overview</span></span>  
  
-   <span data-ttu-id="cf311-121">使用索引器可以用类似于数组的方式为对象建立索引。</span><span class="sxs-lookup"><span data-stu-id="cf311-121">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
-   <span data-ttu-id="cf311-122">`get` 取值函数返回值。</span><span class="sxs-lookup"><span data-stu-id="cf311-122">A `get` accessor returns a value.</span></span> <span data-ttu-id="cf311-123">`set` 取值函数分配值。</span><span class="sxs-lookup"><span data-stu-id="cf311-123">A `set` accessor assigns a value.</span></span>  
  
-   <span data-ttu-id="cf311-124">[this](../../../csharp/language-reference/keywords/this.md) 关键字用于定义索引器。</span><span class="sxs-lookup"><span data-stu-id="cf311-124">The [this](../../../csharp/language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
-   <span data-ttu-id="cf311-125">[value](../../../csharp/language-reference/keywords/value.md) 关键字用于定义 `set` 索引器所赋的值。</span><span class="sxs-lookup"><span data-stu-id="cf311-125">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
-   <span data-ttu-id="cf311-126">索引器不必根据整数值进行索引；由你决定如何定义特定的查找机制。</span><span class="sxs-lookup"><span data-stu-id="cf311-126">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
-   <span data-ttu-id="cf311-127">索引器可被重载。</span><span class="sxs-lookup"><span data-stu-id="cf311-127">Indexers can be overloaded.</span></span>  
  
-   <span data-ttu-id="cf311-128">索引器可以有多个形参，例如当访问二维数组时。</span><span class="sxs-lookup"><span data-stu-id="cf311-128">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
##  <span data-ttu-id="cf311-129"><a name="BKMK_RelatedSections"></a>相关部分</span><span class="sxs-lookup"><span data-stu-id="cf311-129"><a name="BKMK_RelatedSections"></a> Related Sections</span></span>  
  
-   [<span data-ttu-id="cf311-130">使用索引器</span><span class="sxs-lookup"><span data-stu-id="cf311-130">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="cf311-131">接口中的索引器</span><span class="sxs-lookup"><span data-stu-id="cf311-131">Indexers in Interfaces</span></span>](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [<span data-ttu-id="cf311-132">属性与索引器之间的比较</span><span class="sxs-lookup"><span data-stu-id="cf311-132">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="cf311-133">限制访问器可访问性</span><span class="sxs-lookup"><span data-stu-id="cf311-133">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="cf311-134">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="cf311-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cf311-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf311-135">See Also</span></span>  
 <span data-ttu-id="cf311-136">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf311-136">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="cf311-137">属性</span><span class="sxs-lookup"><span data-stu-id="cf311-137">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)

