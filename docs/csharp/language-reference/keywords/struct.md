---
title: struct - C# 参考
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 8d9a23a0813423571c894758257b284ad67a72e2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744645"
---
# <a name="struct-c-reference"></a><span data-ttu-id="b27b4-102">struct（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b27b4-102">struct (C# Reference)</span></span>

<span data-ttu-id="b27b4-103">`struct` 类型是一种值类型，通常用来封装小型相关变量组，例如，矩形的坐标或库存商品的特征。</span><span class="sxs-lookup"><span data-stu-id="b27b4-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="b27b4-104">下面的示例显示了一个简单的结构声明：</span><span class="sxs-lookup"><span data-stu-id="b27b4-104">The following example shows a simple struct declaration:</span></span>

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a><span data-ttu-id="b27b4-105">备注</span><span class="sxs-lookup"><span data-stu-id="b27b4-105">Remarks</span></span>

<span data-ttu-id="b27b4-106">结构还可以包含[构造函数](../../programming-guide/classes-and-structs/constructors.md)、[常量](../../programming-guide/classes-and-structs/constants.md)、[字段](../../programming-guide/classes-and-structs/fields.md)、[方法](../../programming-guide/classes-and-structs/methods.md)、[属性](../../programming-guide/classes-and-structs/properties.md)、[索引器](../../programming-guide/indexers/index.md)、[运算符](../operators/index.md)、[事件](../../programming-guide/events/index.md)和[嵌套类型](../../programming-guide/classes-and-structs/nested-types.md)，但如果同时需要上述几种成员，则应当考虑改为使用类作为类型。</span><span class="sxs-lookup"><span data-stu-id="b27b4-106">Structs can also contain [constructors](../../programming-guide/classes-and-structs/constructors.md), [constants](../../programming-guide/classes-and-structs/constants.md), [fields](../../programming-guide/classes-and-structs/fields.md), [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [indexers](../../programming-guide/indexers/index.md), [operators](../operators/index.md), [events](../../programming-guide/events/index.md), and [nested types](../../programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>

<span data-ttu-id="b27b4-107">有关示例，请参阅[使用结构](../../programming-guide/classes-and-structs/using-structs.md)。</span><span class="sxs-lookup"><span data-stu-id="b27b4-107">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

<span data-ttu-id="b27b4-108">结构可以实现接口，但它们无法继承另一个结构。</span><span class="sxs-lookup"><span data-stu-id="b27b4-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="b27b4-109">因此，结构成员无法声明为 `protected`。</span><span class="sxs-lookup"><span data-stu-id="b27b4-109">For that reason, struct members cannot be declared as `protected`.</span></span>

<span data-ttu-id="b27b4-110">有关详细信息，请参阅[结构](../../programming-guide/classes-and-structs/structs.md)。</span><span class="sxs-lookup"><span data-stu-id="b27b4-110">For more information, see [Structs](../../programming-guide/classes-and-structs/structs.md).</span></span>

## <a name="examples"></a><span data-ttu-id="b27b4-111">示例</span><span class="sxs-lookup"><span data-stu-id="b27b4-111">Examples</span></span>

<span data-ttu-id="b27b4-112">有关示例和详细信息，请参阅[使用结构](../../programming-guide/classes-and-structs/using-structs.md)。</span><span class="sxs-lookup"><span data-stu-id="b27b4-112">For examples and more information, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b27b4-113">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b27b4-113">C# language specification</span></span>

<span data-ttu-id="b27b4-114">有关示例，请参阅[使用结构](../../programming-guide/classes-and-structs/using-structs.md)。</span><span class="sxs-lookup"><span data-stu-id="b27b4-114">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b27b4-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="b27b4-115">See also</span></span>

- [<span data-ttu-id="b27b4-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b27b4-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b27b4-117">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="b27b4-117">C# keywords</span></span>](index.md)
- [<span data-ttu-id="b27b4-118">内置类型表</span><span class="sxs-lookup"><span data-stu-id="b27b4-118">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="b27b4-119">值类型</span><span class="sxs-lookup"><span data-stu-id="b27b4-119">Value types</span></span>](../builtin-types/value-types.md)
- [<span data-ttu-id="b27b4-120">class</span><span class="sxs-lookup"><span data-stu-id="b27b4-120">class</span></span>](class.md)
- [<span data-ttu-id="b27b4-121">interface</span><span class="sxs-lookup"><span data-stu-id="b27b4-121">interface</span></span>](interface.md)
- [<span data-ttu-id="b27b4-122">类和结构</span><span class="sxs-lookup"><span data-stu-id="b27b4-122">Classes and structs</span></span>](../../programming-guide/classes-and-structs/index.md)
