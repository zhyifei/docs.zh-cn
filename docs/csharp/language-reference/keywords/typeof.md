---
title: typeof（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 2493e78fd0782eebee17afd979e1c429339d0a3f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486800"
---
# <a name="typeof-c-reference"></a><span data-ttu-id="b495f-102">typeof（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b495f-102">typeof (C# Reference)</span></span>
<span data-ttu-id="b495f-103">用于为类型获取 `System.Type` 对象。</span><span class="sxs-lookup"><span data-stu-id="b495f-103">Used to obtain the `System.Type` object for a type.</span></span> <span data-ttu-id="b495f-104">`typeof` 表达式采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="b495f-104">A `typeof` expression takes the following form:</span></span>  
  
```csharp  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a><span data-ttu-id="b495f-105">备注</span><span class="sxs-lookup"><span data-stu-id="b495f-105">Remarks</span></span>  
 <span data-ttu-id="b495f-106">若要获取表达式的运行时类型，可以使用 .NET Framework 方法 <xref:System.Object.GetType%2A>，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="b495f-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>  
  
```csharp  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 <span data-ttu-id="b495f-107">不能重载 `typeof` 运算符。</span><span class="sxs-lookup"><span data-stu-id="b495f-107">The `typeof` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="b495f-108">`typeof` 运算符也可用于开放式泛型类型。</span><span class="sxs-lookup"><span data-stu-id="b495f-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="b495f-109">具有多个类型参数的类型必须在规范中具有适当数量的逗号。</span><span class="sxs-lookup"><span data-stu-id="b495f-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="b495f-110">以下示例显示如何确定方法的返回类型是否为泛型 <xref:System.Collections.Generic.IEnumerable%601>。</span><span class="sxs-lookup"><span data-stu-id="b495f-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="b495f-111">如果返回类型不是 <xref:System.Collections.Generic.IEnumerable%601> 泛型类型，则 <xref:System.Type.GetInterface%2A?displayProperty=nameWithType> 将返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="b495f-111"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> will return `null` if the return type is not an <xref:System.Collections.Generic.IEnumerable%601> generic type.</span></span>
  
 [!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]   
  
## <a name="example"></a><span data-ttu-id="b495f-112">示例</span><span class="sxs-lookup"><span data-stu-id="b495f-112">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="b495f-113">示例</span><span class="sxs-lookup"><span data-stu-id="b495f-113">Example</span></span>  
 <span data-ttu-id="b495f-114">此示例使用 <xref:System.Object.GetType%2A> 方法来确定用于包含数值计算结果的类型。</span><span class="sxs-lookup"><span data-stu-id="b495f-114">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="b495f-115">这取决于所得数字的存储要求。</span><span class="sxs-lookup"><span data-stu-id="b495f-115">This depends on the storage requirements of the resulting number.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="b495f-116">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b495f-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b495f-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b495f-117">See Also</span></span>

- <xref:System.Type?displayProperty=nameWithType>  
- [<span data-ttu-id="b495f-118">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b495f-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="b495f-119">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b495f-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b495f-120">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="b495f-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="b495f-121">is</span><span class="sxs-lookup"><span data-stu-id="b495f-121">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
- [<span data-ttu-id="b495f-122">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="b495f-122">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
