---
title: "this（C# 参考）"
description: "this 关键字（C# 参考）"
keywords: "this (C#), this 关键字 (C#), this 关键字（C# 参考）, this 关键字（C# 语言参考）"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- this
- this_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
caps.latest.revision: 19
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
ms.openlocfilehash: 1e764bbd85d06a3b1898f6574064b2844f6d6813
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="this-c-reference"></a><span data-ttu-id="812c6-104">this（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="812c6-104">this (C# Reference)</span></span>
<span data-ttu-id="812c6-105">`this` 关键字指代类的当前实例，还可用作扩展方法的第一个参数的修饰符。</span><span class="sxs-lookup"><span data-stu-id="812c6-105">The `this` keyword refers to the current instance of the class and is also used as a modifier of the first parameter of an extension method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="812c6-106">本文介绍 `this` 在类实例中的用法。</span><span class="sxs-lookup"><span data-stu-id="812c6-106">This article discusses the use of `this` with class instances.</span></span> <span data-ttu-id="812c6-107">若要深入了解它在扩展方法中的用法，请参阅[扩展方法](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="812c6-107">For more information about its use in extension methods, see [Extension Methods](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span>  
  
 <span data-ttu-id="812c6-108">以下是 `this` 的常见用法：</span><span class="sxs-lookup"><span data-stu-id="812c6-108">The following are common uses of `this`:</span></span>  
  
-   <span data-ttu-id="812c6-109">限定类似名称隐藏的成员，例如：</span><span class="sxs-lookup"><span data-stu-id="812c6-109">To qualify members hidden by similar names, for example:</span></span>  
  
 <span data-ttu-id="812c6-110">[!code-cs[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="812c6-110">[!code-cs[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]</span></span>  
  
-   <span data-ttu-id="812c6-111">将对象作为参数传递给方法，例如：</span><span class="sxs-lookup"><span data-stu-id="812c6-111">To pass an object as a parameter to other methods, for example:</span></span>  
  
    ```  
    CalcTax(this);  
    ```  
  
-   <span data-ttu-id="812c6-112">声明索引器，例如：</span><span class="sxs-lookup"><span data-stu-id="812c6-112">To declare indexers, for example:</span></span>  
  
 <span data-ttu-id="812c6-113">[!code-cs[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="812c6-113">[!code-cs[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]</span></span>  
  
 <span data-ttu-id="812c6-114">静态成员函数，因为它们存在于类级别且不属于对象，不具有 `this` 指针。</span><span class="sxs-lookup"><span data-stu-id="812c6-114">Static member functions, because they exist at the class level and not as part of an object, do not have a `this` pointer.</span></span> <span data-ttu-id="812c6-115">在静态方法中引用 `this` 是错误的。</span><span class="sxs-lookup"><span data-stu-id="812c6-115">It is an error to refer to `this` in a static method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="812c6-116">示例</span><span class="sxs-lookup"><span data-stu-id="812c6-116">Example</span></span>  
 <span data-ttu-id="812c6-117">在此示例中，`this` 用于限定类似名称隐藏的 `Employee` 类成员、`name` 和 `alias`。</span><span class="sxs-lookup"><span data-stu-id="812c6-117">In this example, `this` is used to qualify the `Employee` class members, `name` and `alias`, which are hidden by similar names.</span></span> <span data-ttu-id="812c6-118">它还用于将某个对象传递给属于其他类的方法 `CalcTax`。</span><span class="sxs-lookup"><span data-stu-id="812c6-118">It is also used to pass an object to the method `CalcTax`, which belongs to another class.</span></span>  
  
 <span data-ttu-id="812c6-119">[!code-cs[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="812c6-119">[!code-cs[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="812c6-120">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="812c6-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="812c6-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="812c6-121">See Also</span></span>  
 <span data-ttu-id="812c6-122">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="812c6-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="812c6-123">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="812c6-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="812c6-124">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="812c6-124">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="812c6-125">[base](../../../csharp/language-reference/keywords/base.md) </span><span class="sxs-lookup"><span data-stu-id="812c6-125">[base](../../../csharp/language-reference/keywords/base.md) </span></span>  
 [<span data-ttu-id="812c6-126">方法</span><span class="sxs-lookup"><span data-stu-id="812c6-126">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

