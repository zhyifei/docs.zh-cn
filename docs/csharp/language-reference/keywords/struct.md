---
title: struct（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: ddea59e76835ccccd07c299f819796336cddada8
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
---
# <a name="struct-c-reference"></a><span data-ttu-id="90a36-102">struct（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="90a36-102">struct (C# Reference)</span></span>
<span data-ttu-id="90a36-103">`struct` 类型是一种值类型，通常用来封装小型相关变量组，例如，矩形的坐标或库存商品的特征。</span><span class="sxs-lookup"><span data-stu-id="90a36-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="90a36-104">下面的示例显示了一个简单的结构声明：</span><span class="sxs-lookup"><span data-stu-id="90a36-104">The following example shows a simple struct declaration:</span></span>  
  
```csharp  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="90a36-105">备注</span><span class="sxs-lookup"><span data-stu-id="90a36-105">Remarks</span></span>  
 <span data-ttu-id="90a36-106">结构还可以包含[构造函数](../../../csharp/programming-guide/classes-and-structs/constructors.md)、[常量](../../../csharp/programming-guide/classes-and-structs/constants.md)、[字段](../../../csharp/programming-guide/classes-and-structs/fields.md)、[方法](../../../csharp/programming-guide/classes-and-structs/methods.md)、[属性](../../../csharp/programming-guide/classes-and-structs/properties.md)、[索引器](../../../csharp/programming-guide/indexers/index.md)、[运算符](../../../csharp/programming-guide/statements-expressions-operators/operators.md)、[事件](../../../csharp/programming-guide/events/index.md)和[嵌套类型](../../../csharp/programming-guide/classes-and-structs/nested-types.md)，但如果同时需要上述几种成员，则应当考虑改为使用类作为类型。</span><span class="sxs-lookup"><span data-stu-id="90a36-106">Structs can also contain [constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md), [constants](../../../csharp/programming-guide/classes-and-structs/constants.md), [fields](../../../csharp/programming-guide/classes-and-structs/fields.md), [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [indexers](../../../csharp/programming-guide/indexers/index.md), [operators](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [events](../../../csharp/programming-guide/events/index.md), and [nested types](../../../csharp/programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>  
  
 <span data-ttu-id="90a36-107">有关示例，请参阅[使用结构](../../../csharp/programming-guide/classes-and-structs/using-structs.md)。</span><span class="sxs-lookup"><span data-stu-id="90a36-107">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
 <span data-ttu-id="90a36-108">结构可以实现接口，但它们无法继承另一个结构。</span><span class="sxs-lookup"><span data-stu-id="90a36-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="90a36-109">因此，结构成员无法声明为 `protected`。</span><span class="sxs-lookup"><span data-stu-id="90a36-109">For that reason, struct members cannot be declared as `protected`.</span></span>  
  
 <span data-ttu-id="90a36-110">有关详细信息，请参阅[结构](../../../csharp/programming-guide/classes-and-structs/structs.md)。</span><span class="sxs-lookup"><span data-stu-id="90a36-110">For more information, see [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="90a36-111">示例</span><span class="sxs-lookup"><span data-stu-id="90a36-111">Examples</span></span>  
 <span data-ttu-id="90a36-112">有关示例和详细信息，请参阅[使用结构](../../../csharp/programming-guide/classes-and-structs/using-structs.md)。</span><span class="sxs-lookup"><span data-stu-id="90a36-112">For examples and more information, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="90a36-113">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="90a36-113">C# Language Specification</span></span>  
 <span data-ttu-id="90a36-114">有关示例，请参阅[使用结构](../../../csharp/programming-guide/classes-and-structs/using-structs.md)。</span><span class="sxs-lookup"><span data-stu-id="90a36-114">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90a36-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="90a36-115">See Also</span></span>  
 [<span data-ttu-id="90a36-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="90a36-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="90a36-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="90a36-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="90a36-118">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="90a36-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="90a36-119">默认值表</span><span class="sxs-lookup"><span data-stu-id="90a36-119">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
 [<span data-ttu-id="90a36-120">内置类型表</span><span class="sxs-lookup"><span data-stu-id="90a36-120">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="90a36-121">类型</span><span class="sxs-lookup"><span data-stu-id="90a36-121">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="90a36-122">值类型</span><span class="sxs-lookup"><span data-stu-id="90a36-122">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="90a36-123">class</span><span class="sxs-lookup"><span data-stu-id="90a36-123">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
 [<span data-ttu-id="90a36-124">interface</span><span class="sxs-lookup"><span data-stu-id="90a36-124">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
 [<span data-ttu-id="90a36-125">类和结构</span><span class="sxs-lookup"><span data-stu-id="90a36-125">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
