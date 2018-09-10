---
title: new 运算符（C# 参考）
ms.date: 03/15/2018
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 362217b247bd2ab7a2eec2f86cbaaf1a0652a3ad
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44275205"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="31bda-102">new 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="31bda-102">new operator (C# Reference)</span></span>

<span data-ttu-id="31bda-103">用于创建对象和调用构造函数。</span><span class="sxs-lookup"><span data-stu-id="31bda-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="31bda-104">例如:</span><span class="sxs-lookup"><span data-stu-id="31bda-104">For example:</span></span>

```csharp
Class1 obj  = new Class1();
```

<span data-ttu-id="31bda-105">它还用于创建匿名类型的实例：</span><span class="sxs-lookup"><span data-stu-id="31bda-105">It is also used to create instances of anonymous types:</span></span>

```csharp
var query = from cust in customers
            select new { Name = cust.Name, Address = cust.PrimaryAddress };
```

<span data-ttu-id="31bda-106">`new` 运算符还用于调用值类型的默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="31bda-106">The `new` operator is also used to invoke the default constructor for value types.</span></span> <span data-ttu-id="31bda-107">例如:</span><span class="sxs-lookup"><span data-stu-id="31bda-107">For example:</span></span>

```csharp
int i = new int();
```

<span data-ttu-id="31bda-108">在前面的语句中，`i` 的初始值为 `0`，这是类型 `int` 的默认值。</span><span class="sxs-lookup"><span data-stu-id="31bda-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="31bda-109">此语句与下面的语句的效果相同：</span><span class="sxs-lookup"><span data-stu-id="31bda-109">The statement has the same effect as the following:</span></span>

```csharp
int i = 0;
```

<span data-ttu-id="31bda-110">有关默认值的完整列表，请参阅[默认值表](default-values-table.md)。</span><span class="sxs-lookup"><span data-stu-id="31bda-110">For a complete list of default values, see [Default Values Table](default-values-table.md).</span></span>

<span data-ttu-id="31bda-111">请记住，为 [struct](struct.md) 声明默认构造函数是错误的，因为每个值类型均隐式含有公共默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="31bda-111">Remember that it is an error to declare a default constructor for a [struct](struct.md) because every value type implicitly has a public default constructor.</span></span> <span data-ttu-id="31bda-112">可以对结构类型声明参数化构造函数，以设置其初始值，但仅在需要除默认值以外的值时才需要这样做。</span><span class="sxs-lookup"><span data-stu-id="31bda-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>

<span data-ttu-id="31bda-113">值类型对象（如结构）和引用类型对象（如类）都会自动销毁，但值类型对象是在其包含的上下文被销毁时才会销毁，而引用类型对象是在对它们的最后一个引用被删除后的未指定时间由垃圾回收器销毁。</span><span class="sxs-lookup"><span data-stu-id="31bda-113">Both value-type objects such as structs and reference-type objects such as classes are destroyed automatically, but value-type objects are destroyed when their containing context is destroyed, whereas reference-type objects are destroyed by the garbage collector at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="31bda-114">对于包含文件句柄或网络连接等资源的类型，最好使用确定性清理来确保尽快释放其包含的资源。</span><span class="sxs-lookup"><span data-stu-id="31bda-114">For types that contain resources such as file handles, or network connections, it is desirable to employ deterministic cleanup to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="31bda-115">有关详细信息，请参阅 [Using 语句](using-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="31bda-115">For more information, see [using Statement](using-statement.md).</span></span>

<span data-ttu-id="31bda-116">不能重载 `new` 运算符。</span><span class="sxs-lookup"><span data-stu-id="31bda-116">The `new` operator cannot be overloaded.</span></span>

<span data-ttu-id="31bda-117">如果 `new` 运算符无法分配内存，则引发异常 <xref:System.OutOfMemoryException>。</span><span class="sxs-lookup"><span data-stu-id="31bda-117">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>

## <a name="example"></a><span data-ttu-id="31bda-118">示例</span><span class="sxs-lookup"><span data-stu-id="31bda-118">Example</span></span>

<span data-ttu-id="31bda-119">在下面的示例中，使用 `new` 运算符创建并初始化 `struct` 对象和类对象，并向它们分配值。</span><span class="sxs-lookup"><span data-stu-id="31bda-119">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="31bda-120">显示默认值和分配的值。</span><span class="sxs-lookup"><span data-stu-id="31bda-120">The default and the assigned values are displayed.</span></span>

[!code-csharp[csrefKeywordsOperator#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#7)]

<span data-ttu-id="31bda-121">请注意，本示例中字符串的默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="31bda-121">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="31bda-122">因此，未显示此字符串。</span><span class="sxs-lookup"><span data-stu-id="31bda-122">Therefore, it is not displayed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="31bda-123">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="31bda-123">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="31bda-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="31bda-124">See also</span></span>

- [<span data-ttu-id="31bda-125">C# 参考</span><span class="sxs-lookup"><span data-stu-id="31bda-125">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="31bda-126">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="31bda-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="31bda-127">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="31bda-127">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="31bda-128">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="31bda-128">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="31bda-129">new</span><span class="sxs-lookup"><span data-stu-id="31bda-129">new</span></span>](new.md)
- [<span data-ttu-id="31bda-130">匿名类型</span><span class="sxs-lookup"><span data-stu-id="31bda-130">Anonymous Types</span></span>](../../programming-guide/classes-and-structs/anonymous-types.md)