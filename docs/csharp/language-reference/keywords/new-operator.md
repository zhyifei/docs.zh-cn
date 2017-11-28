---
title: "new 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3c2b484b9872a54ce42520de77a723b9edb441a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="acdb1-102">new 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="acdb1-102">new Operator (C# Reference)</span></span>
<span data-ttu-id="acdb1-103">用于创建对象和调用构造函数。</span><span class="sxs-lookup"><span data-stu-id="acdb1-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="acdb1-104">例如：</span><span class="sxs-lookup"><span data-stu-id="acdb1-104">For example:</span></span>  
  
```  
Class1 obj  = new Class1();  
```  
  
 <span data-ttu-id="acdb1-105">它还用于创建匿名类型的实例：</span><span class="sxs-lookup"><span data-stu-id="acdb1-105">It is also used to create instances of anonymous types:</span></span>  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 <span data-ttu-id="acdb1-106">`new` 运算符还用于调用值类型的默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="acdb1-106">The `new` operator is also used to invoke the default constructor for value types.</span></span> <span data-ttu-id="acdb1-107">例如：</span><span class="sxs-lookup"><span data-stu-id="acdb1-107">For example:</span></span>  
  
```  
int i = new int();  
```  
  
 <span data-ttu-id="acdb1-108">在前面的语句中，`i` 的初始值为 `0`，这是类型 `int` 的默认值。</span><span class="sxs-lookup"><span data-stu-id="acdb1-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="acdb1-109">此语句与下面的语句的效果相同：</span><span class="sxs-lookup"><span data-stu-id="acdb1-109">The statement has the same effect as the following:</span></span>  
  
```  
int i = 0;  
```  
  
 <span data-ttu-id="acdb1-110">有关默认值的完整列表，请参阅[默认值表](../../../csharp/language-reference/keywords/default-values-table.md)。</span><span class="sxs-lookup"><span data-stu-id="acdb1-110">For a complete list of default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="acdb1-111">请记住，为 [struct](../../../csharp/language-reference/keywords/struct.md) 声明默认构造函数是错误的，因为每个值类型均隐式含有公共默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="acdb1-111">Remember that it is an error to declare a default constructor for a [struct](../../../csharp/language-reference/keywords/struct.md) because every value type implicitly has a public default constructor.</span></span> <span data-ttu-id="acdb1-112">可以对结构类型声明参数化构造函数，以设置其初始值，但仅在需要除默认值以外的值时才需要这样做。</span><span class="sxs-lookup"><span data-stu-id="acdb1-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>  
  
 <span data-ttu-id="acdb1-113">值类型对象（例如结构）是在堆栈上创建的，而引用类型对象（例如类）是在堆上创建的。</span><span class="sxs-lookup"><span data-stu-id="acdb1-113">Value-type objects such as structs are created on the stack, while reference-type objects such as classes are created on the heap.</span></span> <span data-ttu-id="acdb1-114">这两种类型的对象均被自动销毁，但基于值类型的对象是在它们超出范围时被销毁，而基于引用类型的对象是在删除对它们的最后一个引用后在非指定时间被销毁。</span><span class="sxs-lookup"><span data-stu-id="acdb1-114">Both types of objects are destroyed automatically, but objects based on value types are destroyed when they go out of scope, whereas objects based on reference types are destroyed at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="acdb1-115">对于占用固定资源（如大量内存、文件句柄或网络连接）的引用类型，有时需要应用确定性终结，以确保尽快销毁对象。</span><span class="sxs-lookup"><span data-stu-id="acdb1-115">For reference types that consume fixed resources such as large amounts of memory, file handles, or network connections, it is sometimes desirable to employ deterministic finalization to ensure that the object is destroyed as soon as possible.</span></span> <span data-ttu-id="acdb1-116">有关详细信息，请参阅 [Using 语句](../../../csharp/language-reference/keywords/using-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="acdb1-116">For more information, see [using Statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span>  
  
 <span data-ttu-id="acdb1-117">不能重载 `new` 运算符。</span><span class="sxs-lookup"><span data-stu-id="acdb1-117">The `new` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="acdb1-118">如果 `new` 运算符无法分配内存，则引发异常 <xref:System.OutOfMemoryException>。</span><span class="sxs-lookup"><span data-stu-id="acdb1-118">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acdb1-119">示例</span><span class="sxs-lookup"><span data-stu-id="acdb1-119">Example</span></span>  
 <span data-ttu-id="acdb1-120">在下面的示例中，使用 `new` 运算符创建并初始化 `struct` 对象和类对象，并向它们分配值。</span><span class="sxs-lookup"><span data-stu-id="acdb1-120">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="acdb1-121">显示默认值和分配的值。</span><span class="sxs-lookup"><span data-stu-id="acdb1-121">The default and the assigned values are displayed.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]  
  
 <span data-ttu-id="acdb1-122">请注意，本示例中字符串的默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="acdb1-122">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="acdb1-123">因此，未显示此字符串。</span><span class="sxs-lookup"><span data-stu-id="acdb1-123">Therefore, it is not displayed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="acdb1-124">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="acdb1-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="acdb1-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="acdb1-125">See Also</span></span>  
 [<span data-ttu-id="acdb1-126">C# 参考</span><span class="sxs-lookup"><span data-stu-id="acdb1-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="acdb1-127">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="acdb1-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="acdb1-128">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="acdb1-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="acdb1-129">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="acdb1-129">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="acdb1-130">new</span><span class="sxs-lookup"><span data-stu-id="acdb1-130">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
 [<span data-ttu-id="acdb1-131">匿名类型</span><span class="sxs-lookup"><span data-stu-id="acdb1-131">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
