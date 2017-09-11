---
title: "get（C# 参考）"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- get_CSharpKeyword
- get
dev_langs:
- CSharp
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
caps.latest.revision: 11
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
ms.openlocfilehash: 88603864ae0a31a193cab211b8ce8061ec63c169
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="get-c-reference"></a><span data-ttu-id="8545f-102">get（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="8545f-102">get (C# Reference)</span></span>

<span data-ttu-id="8545f-103">`get` 关键字在属性或索引器中定义访问器方法，它将返回属性值或索引器元素。</span><span class="sxs-lookup"><span data-stu-id="8545f-103">The `get` keyword defines an *accessor* method in a property or indexer that returns the property value or the indexer element.</span></span> <span data-ttu-id="8545f-104">有关详细信息，请参阅[属性](../../../csharp/programming-guide/classes-and-structs/properties.md)、[自动实现的属性](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)和[索引器](../../../csharp/programming-guide/indexers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="8545f-104">For more information, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) and [Indexers](../../../csharp/programming-guide/indexers/index.md).</span></span>  
  
<span data-ttu-id="8545f-105">以下示例为名为 `Seconds` 的属性同时定义 `get` 和 `set` 访问器。</span><span class="sxs-lookup"><span data-stu-id="8545f-105">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="8545f-106">它使用名为 `_seconds` 的私有字段备份属性值。</span><span class="sxs-lookup"><span data-stu-id="8545f-106">It uses a private field named `_seconds` to back the property value.</span></span>  
 
 <span data-ttu-id="8545f-107">[!code-cs[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8545f-107">[!code-cs[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]</span></span>  
  
<span data-ttu-id="8545f-108">通常，`get` 访问器包含返回一个值的单个语句，如前面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="8545f-108">Often, the `get` accessor consists of a single statement that returns a value, as it did in the previous example.</span></span> <span data-ttu-id="8545f-109">从 C# 7 开始，可以将 `get` 访问器作为 expression-bodied 成员实现。</span><span class="sxs-lookup"><span data-stu-id="8545f-109">Starting with C# 7, you can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="8545f-110">以下示例将 `get` 和 `set` 访问器都作为 expression-bodied 成员实现。</span><span class="sxs-lookup"><span data-stu-id="8545f-110">The following example implements both the `get` and the `set` accessor as expression-bodied members.</span></span>

 <span data-ttu-id="8545f-111">[!code-cs[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8545f-111">[!code-cs[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]</span></span>   
 
<span data-ttu-id="8545f-112">对于属性的 `get` 和 `set` 访问器不执行除设置或检索私有支持字段中的值以外的任何其他操作的简单情况，可以利用 C# 编译器对自动实现的属性的支持。</span><span class="sxs-lookup"><span data-stu-id="8545f-112">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="8545f-113">以下示例将 `Hours` 作为自动实现的属性来实现。</span><span class="sxs-lookup"><span data-stu-id="8545f-113">The following example implements `Hours` as an auto-implemented property.</span></span> 
  
 <span data-ttu-id="8545f-114">[!code-cs[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8545f-114">[!code-cs[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="8545f-115">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="8545f-115">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8545f-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8545f-116">See Also</span></span>  
 <span data-ttu-id="8545f-117">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="8545f-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="8545f-118">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8545f-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8545f-119">[C# 关键字](../../../csharp/language-reference/keywords/index.md)[属性](../../../csharp/programming-guide/classes-and-structs/properties.md)</span><span class="sxs-lookup"><span data-stu-id="8545f-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md)</span></span>

