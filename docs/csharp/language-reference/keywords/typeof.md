---
title: "typeof（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeof
- typeof_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: 21
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
ms.openlocfilehash: fdb335e44a5a3634520d3a86495a4508597b4f70
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="typeof-c-reference"></a><span data-ttu-id="50d43-102">typeof（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="50d43-102">typeof (C# Reference)</span></span>
<span data-ttu-id="50d43-103">用于为类型获取 `System.Type` 对象。</span><span class="sxs-lookup"><span data-stu-id="50d43-103">Used to obtain the `System.Type` object for a type.</span></span> <span data-ttu-id="50d43-104">`typeof` 表达式采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="50d43-104">A `typeof` expression takes the following form:</span></span>  
  
```  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a><span data-ttu-id="50d43-105">备注</span><span class="sxs-lookup"><span data-stu-id="50d43-105">Remarks</span></span>  
 <span data-ttu-id="50d43-106">若要获取表达式的运行时类型，可以使用 .NET Framework 方法 <xref:System.Object.GetType%2A>，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="50d43-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 <span data-ttu-id="50d43-107">不能重载 `typeof` 运算符。</span><span class="sxs-lookup"><span data-stu-id="50d43-107">The `typeof` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="50d43-108">`typeof` 运算符也可用于开放式泛型类型。</span><span class="sxs-lookup"><span data-stu-id="50d43-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="50d43-109">具有多个类型参数的类型必须在规范中具有适当数量的逗号。</span><span class="sxs-lookup"><span data-stu-id="50d43-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="50d43-110">以下示例显示如何确定方法的返回类型是否为泛型 <xref:System.Collections.Generic.IEnumerable%601>。</span><span class="sxs-lookup"><span data-stu-id="50d43-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="50d43-111">假设该方法是 MethodInfo 类型的实例：</span><span class="sxs-lookup"><span data-stu-id="50d43-111">Assume that method is an instance of a MethodInfo type:</span></span>  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## <a name="example"></a><span data-ttu-id="50d43-112">示例</span><span class="sxs-lookup"><span data-stu-id="50d43-112">Example</span></span>  
 <span data-ttu-id="50d43-113">[!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="50d43-113">[!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="50d43-114">示例</span><span class="sxs-lookup"><span data-stu-id="50d43-114">Example</span></span>  
 <span data-ttu-id="50d43-115">此示例使用 <xref:System.Object.GetType%2A> 方法来确定用于包含数值计算结果的类型。</span><span class="sxs-lookup"><span data-stu-id="50d43-115">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="50d43-116">这取决于所得数字的存储要求。</span><span class="sxs-lookup"><span data-stu-id="50d43-116">This depends on the storage requirements of the resulting number.</span></span>  
  
 <span data-ttu-id="50d43-117">[!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="50d43-117">[!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="50d43-118">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="50d43-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="50d43-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50d43-119">See Also</span></span>  
 <span data-ttu-id="50d43-120"><xref:System.Type?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="50d43-120"><xref:System.Type?displayProperty=fullName></span></span>   
 <span data-ttu-id="50d43-121">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="50d43-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="50d43-122">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="50d43-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="50d43-123">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="50d43-123">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="50d43-124">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="50d43-124">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 [<span data-ttu-id="50d43-125">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="50d43-125">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

