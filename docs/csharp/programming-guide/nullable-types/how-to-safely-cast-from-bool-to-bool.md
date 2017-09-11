---
title: "如何：安全地将 bool? 强制转换为 bool（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
caps.latest.revision: 9
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
ms.openlocfilehash: c8a3dc3280b7dca802b327d9454c7f0ba9ed44be
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-safely-cast-from-bool-to-bool-c-programming-guide"></a><span data-ttu-id="1fbbd-102">如何：安全地将 bool? 强制转换为 bool（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="1fbbd-102">How to: Safely Cast from bool? to bool (C# Programming Guide)</span></span>
<span data-ttu-id="1fbbd-103">可以为 null 的类型 `bool?` 可包含三个不同的值：`true`、`false` 和 `null`。</span><span class="sxs-lookup"><span data-stu-id="1fbbd-103">The `bool?` nullable type can contain three different values: `true`, `false`, and `null`.</span></span> <span data-ttu-id="1fbbd-104">因此，`bool?` 类型不能用于条件语句，例如与 `if`、`for` 或 `while` 等一起使用。</span><span class="sxs-lookup"><span data-stu-id="1fbbd-104">Therefore, the `bool?` type cannot be used in conditionals such as with `if`, `for`, or `while`.</span></span> <span data-ttu-id="1fbbd-105">例如，下面的代码会导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="1fbbd-105">For example, the following code causes a compiler error.</span></span>  
  
```  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 <span data-ttu-id="1fbbd-106">这是不允许的，因为在条件语句上下文中，`null` 表示的含义不清楚。</span><span class="sxs-lookup"><span data-stu-id="1fbbd-106">This is not allowed because it is unclear what `null` means in the context of a conditional.</span></span> <span data-ttu-id="1fbbd-107">若要在条件语句中使用 `bool?`，首先请检查其 <xref:System.Nullable%601.HasValue%2A> 属性，确保该属性的值不是 `null`，然后将其转换为 `bool`。</span><span class="sxs-lookup"><span data-stu-id="1fbbd-107">To use a `bool?` in a conditional statement, first check its <xref:System.Nullable%601.HasValue%2A> property to ensure that its value is not `null`, and then cast it to `bool`.</span></span> <span data-ttu-id="1fbbd-108">有关详细信息，请参阅 [bool](../../../csharp/language-reference/keywords/bool.md)。</span><span class="sxs-lookup"><span data-stu-id="1fbbd-108">For more information, see [bool](../../../csharp/language-reference/keywords/bool.md).</span></span> <span data-ttu-id="1fbbd-109">如果对值为 `null` 的 `bool?` 执行转换，则会在条件测试中引发 <xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="1fbbd-109">If you perform the cast on a `bool?` with a value of `null`, a <xref:System.InvalidOperationException> will be thrown in the conditional test.</span></span> <span data-ttu-id="1fbbd-110">以下示例演示了一种将 `bool?` 安全转换为 `bool` 的方式：</span><span class="sxs-lookup"><span data-stu-id="1fbbd-110">The following example shows one way to safely cast from `bool?` to `bool`:</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fbbd-111">示例</span><span class="sxs-lookup"><span data-stu-id="1fbbd-111">Example</span></span>  
  
```csharp  
bool? test = null;  
// Other code that may or may not  
// give a value to test.  
if(!test.HasValue) //check for a value  
{  
    // Assume that IsInitialized  
    // returns either true or false.  
    test = IsInitialized();  
}  
if((bool)test) //now this cast is safe  
{  
   // Do something.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1fbbd-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fbbd-112">See Also</span></span>  
 <span data-ttu-id="1fbbd-113">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1fbbd-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1fbbd-114">[文字关键字](../../../csharp/language-reference/keywords/literal-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="1fbbd-114">[Literal Keywords](../../../csharp/language-reference/keywords/literal-keywords.md) </span></span>  
 <span data-ttu-id="1fbbd-115">[可以为 null 的类型](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="1fbbd-115">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 [<span data-ttu-id="1fbbd-116">??运算符</span><span class="sxs-lookup"><span data-stu-id="1fbbd-116">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)

