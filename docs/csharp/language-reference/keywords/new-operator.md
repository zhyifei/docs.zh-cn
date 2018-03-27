---
title: new 运算符（C# 参考）
ms.date: 03/15/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: ''
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ab582cd14bc649ca8d1678a583a8f95e78c6bf7e
ms.sourcegitcommit: 32172ca05d5dcce7ef3d327b9c8639c736e0fe2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2018
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="d6ba7-102">new 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="d6ba7-102">new Operator (C# Reference)</span></span>
<span data-ttu-id="d6ba7-103">用于创建对象和调用构造函数。</span><span class="sxs-lookup"><span data-stu-id="d6ba7-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="d6ba7-104">例如:</span><span class="sxs-lookup"><span data-stu-id="d6ba7-104">For example:</span></span>  
  
```csharp
Class1 obj  = new Class1();  
```  
  
 <span data-ttu-id="d6ba7-105">它还用于创建匿名类型的实例：</span><span class="sxs-lookup"><span data-stu-id="d6ba7-105">It is also used to create instances of anonymous types:</span></span>  
  
```csharp
var query = from cust in customers  
            select new { Name = cust.Name, Address = cust.PrimaryAddress };  
```  
  
 <span data-ttu-id="d6ba7-106">`new` 运算符还用于调用值类型的默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="d6ba7-106">The `new` operator is also used to invoke the default constructor for value types.</span></span> <span data-ttu-id="d6ba7-107">例如:</span><span class="sxs-lookup"><span data-stu-id="d6ba7-107">For example:</span></span>  
  
```csharp
int i = new int();  
```  
  
 <span data-ttu-id="d6ba7-108">在前面的语句中，`i` 的初始值为 `0`，这是类型 `int` 的默认值。</span><span class="sxs-lookup"><span data-stu-id="d6ba7-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="d6ba7-109">此语句与下面的语句的效果相同：</span><span class="sxs-lookup"><span data-stu-id="d6ba7-109">The statement has the same effect as the following:</span></span>  
  
```csharp
int i = 0;  
```  
  
 <span data-ttu-id="d6ba7-110">有关默认值的完整列表，请参阅[默认值表](../../../csharp/language-reference/keywords/default-values-table.md)。</span><span class="sxs-lookup"><span data-stu-id="d6ba7-110">For a complete list of default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="d6ba7-111">请记住，为 [struct](../../../csharp/language-reference/keywords/struct.md) 声明默认构造函数是错误的，因为每个值类型均隐式含有公共默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="d6ba7-111">Remember that it is an error to declare a default constructor for a [struct](../../../csharp/language-reference/keywords/struct.md) because every value type implicitly has a public default constructor.</span></span> <span data-ttu-id="d6ba7-112">可以对结构类型声明参数化构造函数，以设置其初始值，但仅在需要除默认值以外的值时才需要这样做。</span><span class="sxs-lookup"><span data-stu-id="d6ba7-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>  
  
 <span data-ttu-id="d6ba7-113">值类型对象（如结构）和引用类型对象（如类）都会自动销毁，但值类型对象是在其包含的上下文被销毁时才会销毁，而引用类型对象是在对它们的最后一个引用被删除后的未指定时间由垃圾回收器销毁。</span><span class="sxs-lookup"><span data-stu-id="d6ba7-113">Both value-type objects such as structs and reference-type objects such as classes are destroyed automatically, but value-type objects are destroyed when their containing context is destroyed, whereas reference-type objects are destroyed by the garbage collector at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="d6ba7-114">对于包含文件句柄或网络连接等资源的类型，最好使用确定性清理来确保尽快释放其包含的资源。</span><span class="sxs-lookup"><span data-stu-id="d6ba7-114">For types that contain resources such as file handles, or network connections, it is desirable to employ deterministic cleanup to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="d6ba7-115">有关详细信息，请参阅 [Using 语句](../../../csharp/language-reference/keywords/using-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d6ba7-115">For more information, see [using Statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span>  
  
 <span data-ttu-id="d6ba7-116">不能重载 `new` 运算符。</span><span class="sxs-lookup"><span data-stu-id="d6ba7-116">The `new` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="d6ba7-117">如果 `new` 运算符无法分配内存，则引发异常 <xref:System.OutOfMemoryException>。</span><span class="sxs-lookup"><span data-stu-id="d6ba7-117">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6ba7-118">示例</span><span class="sxs-lookup"><span data-stu-id="d6ba7-118">Example</span></span>  
 <span data-ttu-id="d6ba7-119">在下面的示例中，使用 `new` 运算符创建并初始化 `struct` 对象和类对象，并向它们分配值。</span><span class="sxs-lookup"><span data-stu-id="d6ba7-119">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="d6ba7-120">显示默认值和分配的值。</span><span class="sxs-lookup"><span data-stu-id="d6ba7-120">The default and the assigned values are displayed.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#7](codesnippet/CSharp/new-operator_1.cs)]  
  
 <span data-ttu-id="d6ba7-121">请注意，本示例中字符串的默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="d6ba7-121">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="d6ba7-122">因此，未显示此字符串。</span><span class="sxs-lookup"><span data-stu-id="d6ba7-122">Therefore, it is not displayed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d6ba7-123">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="d6ba7-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d6ba7-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6ba7-124">See Also</span></span>  
 [<span data-ttu-id="d6ba7-125">C# 参考</span><span class="sxs-lookup"><span data-stu-id="d6ba7-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d6ba7-126">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="d6ba7-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d6ba7-127">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="d6ba7-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="d6ba7-128">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="d6ba7-128">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="d6ba7-129">new</span><span class="sxs-lookup"><span data-stu-id="d6ba7-129">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
 [<span data-ttu-id="d6ba7-130">匿名类型</span><span class="sxs-lookup"><span data-stu-id="d6ba7-130">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
