---
title: this（C# 参考）
description: this 关键字（C# 参考）
keywords: this (C#), this 关键字 (C#), this 关键字（C# 参考）, this 关键字（C# 语言参考）
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f159967707061481a34e72a97ec8cc8316d982ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="this-c-reference"></a><span data-ttu-id="b8756-104">this（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b8756-104">this (C# Reference)</span></span>
<span data-ttu-id="b8756-105">`this` 关键字指代类的当前实例，还可用作扩展方法的第一个参数的修饰符。</span><span class="sxs-lookup"><span data-stu-id="b8756-105">The `this` keyword refers to the current instance of the class and is also used as a modifier of the first parameter of an extension method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8756-106">本文介绍 `this` 在类实例中的用法。</span><span class="sxs-lookup"><span data-stu-id="b8756-106">This article discusses the use of `this` with class instances.</span></span> <span data-ttu-id="b8756-107">若要深入了解它在扩展方法中的用法，请参阅[扩展方法](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="b8756-107">For more information about its use in extension methods, see [Extension Methods](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span>  
  
 <span data-ttu-id="b8756-108">以下是 `this` 的常见用法：</span><span class="sxs-lookup"><span data-stu-id="b8756-108">The following are common uses of `this`:</span></span>  
  
-   <span data-ttu-id="b8756-109">限定类似名称隐藏的成员，例如：</span><span class="sxs-lookup"><span data-stu-id="b8756-109">To qualify members hidden by similar names, for example:</span></span>  
  
 [!code-csharp[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]  
  
-   <span data-ttu-id="b8756-110">将对象作为参数传递给方法，例如：</span><span class="sxs-lookup"><span data-stu-id="b8756-110">To pass an object as a parameter to other methods, for example:</span></span>  
  
    ```  
    CalcTax(this);  
    ```  
  
-   <span data-ttu-id="b8756-111">声明索引器，例如：</span><span class="sxs-lookup"><span data-stu-id="b8756-111">To declare indexers, for example:</span></span>  
  
 [!code-csharp[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]  
  
 <span data-ttu-id="b8756-112">静态成员函数，因为它们存在于类级别且不属于对象，不具有 `this` 指针。</span><span class="sxs-lookup"><span data-stu-id="b8756-112">Static member functions, because they exist at the class level and not as part of an object, do not have a `this` pointer.</span></span> <span data-ttu-id="b8756-113">在静态方法中引用 `this` 是错误的。</span><span class="sxs-lookup"><span data-stu-id="b8756-113">It is an error to refer to `this` in a static method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8756-114">示例</span><span class="sxs-lookup"><span data-stu-id="b8756-114">Example</span></span>  
 <span data-ttu-id="b8756-115">在此示例中，`this` 用于限定类似名称隐藏的 `Employee` 类成员、`name` 和 `alias`。</span><span class="sxs-lookup"><span data-stu-id="b8756-115">In this example, `this` is used to qualify the `Employee` class members, `name` and `alias`, which are hidden by similar names.</span></span> <span data-ttu-id="b8756-116">它还用于将某个对象传递给属于其他类的方法 `CalcTax`。</span><span class="sxs-lookup"><span data-stu-id="b8756-116">It is also used to pass an object to the method `CalcTax`, which belongs to another class.</span></span>  
  
 [!code-csharp[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="b8756-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b8756-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b8756-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8756-118">See Also</span></span>  
 [<span data-ttu-id="b8756-119">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b8756-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b8756-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b8756-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b8756-121">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="b8756-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="b8756-122">base</span><span class="sxs-lookup"><span data-stu-id="b8756-122">base</span></span>](../../../csharp/language-reference/keywords/base.md)  
 [<span data-ttu-id="b8756-123">方法</span><span class="sxs-lookup"><span data-stu-id="b8756-123">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)
