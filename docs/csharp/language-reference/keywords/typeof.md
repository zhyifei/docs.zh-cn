---
title: "typeof（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords: typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: be24740ea7f6fbe8780dd9cac58b7dea9aaf6872
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="typeof-c-reference"></a><span data-ttu-id="cc364-102">typeof（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="cc364-102">typeof (C# Reference)</span></span>
<span data-ttu-id="cc364-103">用于为类型获取 `System.Type` 对象。</span><span class="sxs-lookup"><span data-stu-id="cc364-103">Used to obtain the `System.Type` object for a type.</span></span> <span data-ttu-id="cc364-104">`typeof` 表达式采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="cc364-104">A `typeof` expression takes the following form:</span></span>  
  
```  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a><span data-ttu-id="cc364-105">备注</span><span class="sxs-lookup"><span data-stu-id="cc364-105">Remarks</span></span>  
 <span data-ttu-id="cc364-106">若要获取表达式的运行时类型，可以使用 .NET Framework 方法 <xref:System.Object.GetType%2A>，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="cc364-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 <span data-ttu-id="cc364-107">不能重载 `typeof` 运算符。</span><span class="sxs-lookup"><span data-stu-id="cc364-107">The `typeof` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="cc364-108">`typeof` 运算符也可用于开放式泛型类型。</span><span class="sxs-lookup"><span data-stu-id="cc364-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="cc364-109">具有多个类型参数的类型必须在规范中具有适当数量的逗号。</span><span class="sxs-lookup"><span data-stu-id="cc364-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="cc364-110">以下示例显示如何确定方法的返回类型是否为泛型 <xref:System.Collections.Generic.IEnumerable%601>。</span><span class="sxs-lookup"><span data-stu-id="cc364-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="cc364-111">假设该方法是 MethodInfo 类型的实例：</span><span class="sxs-lookup"><span data-stu-id="cc364-111">Assume that method is an instance of a MethodInfo type:</span></span>  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## <a name="example"></a><span data-ttu-id="cc364-112">示例</span><span class="sxs-lookup"><span data-stu-id="cc364-112">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="cc364-113">示例</span><span class="sxs-lookup"><span data-stu-id="cc364-113">Example</span></span>  
 <span data-ttu-id="cc364-114">此示例使用 <xref:System.Object.GetType%2A> 方法来确定用于包含数值计算结果的类型。</span><span class="sxs-lookup"><span data-stu-id="cc364-114">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="cc364-115">这取决于所得数字的存储要求。</span><span class="sxs-lookup"><span data-stu-id="cc364-115">This depends on the storage requirements of the resulting number.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="cc364-116">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="cc364-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cc364-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc364-117">See Also</span></span>  
 <xref:System.Type?displayProperty=nameWithType>  
 [<span data-ttu-id="cc364-118">C# 参考</span><span class="sxs-lookup"><span data-stu-id="cc364-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="cc364-119">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="cc364-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="cc364-120">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="cc364-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="cc364-121">is</span><span class="sxs-lookup"><span data-stu-id="cc364-121">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
 [<span data-ttu-id="cc364-122">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="cc364-122">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
