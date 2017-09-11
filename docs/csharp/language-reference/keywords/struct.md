---
title: "struct（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- struct_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
caps.latest.revision: 23
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
ms.openlocfilehash: 309e68a57e1ee869850d960ffaac6cf35eb6e260
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="struct-c-reference"></a><span data-ttu-id="5c5e1-102">struct（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5c5e1-102">struct (C# Reference)</span></span>
<span data-ttu-id="5c5e1-103">`struct` 类型是一种值类型，通常用来封装小型相关变量组，例如，矩形的坐标或库存商品的特征。</span><span class="sxs-lookup"><span data-stu-id="5c5e1-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="5c5e1-104">下面的示例显示了一个简单的结构声明：</span><span class="sxs-lookup"><span data-stu-id="5c5e1-104">The following example shows a simple struct declaration:</span></span>  
  
```  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="5c5e1-105">备注</span><span class="sxs-lookup"><span data-stu-id="5c5e1-105">Remarks</span></span>  
 <span data-ttu-id="5c5e1-106">结构还可以包含[构造函数](../../../csharp/programming-guide/classes-and-structs/constructors.md)、[常量](../../../csharp/programming-guide/classes-and-structs/constants.md)、[字段](../../../csharp/programming-guide/classes-and-structs/fields.md)、[方法](../../../csharp/programming-guide/classes-and-structs/methods.md)、[属性](../../../csharp/programming-guide/classes-and-structs/properties.md)、[索引器](../../../csharp/programming-guide/indexers/index.md)、[运算符](../../../csharp/programming-guide/statements-expressions-operators/operators.md)、[事件](../../../csharp/programming-guide/events/index.md)和[嵌套类型](../../../csharp/programming-guide/classes-and-structs/nested-types.md)，但如果同时需要上述几种成员，则应当考虑改为使用类作为类型。</span><span class="sxs-lookup"><span data-stu-id="5c5e1-106">Structs can also contain [constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md), [constants](../../../csharp/programming-guide/classes-and-structs/constants.md), [fields](../../../csharp/programming-guide/classes-and-structs/fields.md), [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [indexers](../../../csharp/programming-guide/indexers/index.md), [operators](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [events](../../../csharp/programming-guide/events/index.md), and [nested types](../../../csharp/programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>  
  
 <span data-ttu-id="5c5e1-107">有关示例，请参阅[使用结构](../../../csharp/programming-guide/classes-and-structs/using-structs.md)。</span><span class="sxs-lookup"><span data-stu-id="5c5e1-107">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
 <span data-ttu-id="5c5e1-108">结构可以实现接口，但它们无法继承另一个结构。</span><span class="sxs-lookup"><span data-stu-id="5c5e1-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="5c5e1-109">因此，结构成员无法声明为 `protected`。</span><span class="sxs-lookup"><span data-stu-id="5c5e1-109">For that reason, struct members cannot be declared as `protected`.</span></span>  
  
 <span data-ttu-id="5c5e1-110">有关详细信息，请参阅[结构](../../../csharp/programming-guide/classes-and-structs/structs.md)。</span><span class="sxs-lookup"><span data-stu-id="5c5e1-110">For more information, see [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5c5e1-111">示例</span><span class="sxs-lookup"><span data-stu-id="5c5e1-111">Examples</span></span>  
 <span data-ttu-id="5c5e1-112">有关示例和详细信息，请参阅[使用结构](../../../csharp/programming-guide/classes-and-structs/using-structs.md)。</span><span class="sxs-lookup"><span data-stu-id="5c5e1-112">For examples and more information, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5c5e1-113">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5c5e1-113">C# Language Specification</span></span>  
 <span data-ttu-id="5c5e1-114">有关示例，请参阅[使用结构](../../../csharp/programming-guide/classes-and-structs/using-structs.md)。</span><span class="sxs-lookup"><span data-stu-id="5c5e1-114">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c5e1-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c5e1-115">See Also</span></span>  
 <span data-ttu-id="5c5e1-116">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5c5e1-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5c5e1-117">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5c5e1-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5c5e1-118">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="5c5e1-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="5c5e1-119">[默认值表](../../../csharp/language-reference/keywords/default-values-table.md) </span><span class="sxs-lookup"><span data-stu-id="5c5e1-119">[Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md) </span></span>  
 <span data-ttu-id="5c5e1-120">[内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="5c5e1-120">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="5c5e1-121">[类型](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="5c5e1-121">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="5c5e1-122">[值类型](../../../csharp/language-reference/keywords/value-types.md) </span><span class="sxs-lookup"><span data-stu-id="5c5e1-122">[Value Types](../../../csharp/language-reference/keywords/value-types.md) </span></span>  
 <span data-ttu-id="5c5e1-123">[类](../../../csharp/language-reference/keywords/class.md) </span><span class="sxs-lookup"><span data-stu-id="5c5e1-123">[class](../../../csharp/language-reference/keywords/class.md) </span></span>  
 <span data-ttu-id="5c5e1-124">[接口](../../../csharp/language-reference/keywords/interface.md) </span><span class="sxs-lookup"><span data-stu-id="5c5e1-124">[interface](../../../csharp/language-reference/keywords/interface.md) </span></span>  
 [<span data-ttu-id="5c5e1-125">类和结构</span><span class="sxs-lookup"><span data-stu-id="5c5e1-125">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)

