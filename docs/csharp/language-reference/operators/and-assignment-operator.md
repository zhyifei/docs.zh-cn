---
title: "&amp;= 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
caps.latest.revision: 15
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
ms.openlocfilehash: 6dec8de5077c07150ea37b88979e7b59b231d610
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="b0c53-102">&amp;= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b0c53-102">&amp;= Operator (C# Reference)</span></span>
<span data-ttu-id="b0c53-103">AND 赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="b0c53-103">The AND assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0c53-104">备注</span><span class="sxs-lookup"><span data-stu-id="b0c53-104">Remarks</span></span>  
 <span data-ttu-id="b0c53-105">使用 `&=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="b0c53-105">An expression using the `&=` assignment operator, such as</span></span>  
  
```  
x &= y  
```  
  
 <span data-ttu-id="b0c53-106">等效于</span><span class="sxs-lookup"><span data-stu-id="b0c53-106">is equivalent to</span></span>  
  
```  
x = x & y  
```  
  
 <span data-ttu-id="b0c53-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="b0c53-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="b0c53-108">[& 运算符](../../../csharp/language-reference/operators/and-operator.md) 对整型操作数执行按位逻辑 AND 运算，对 `bool` 操作数执行逻辑 AND 运算。</span><span class="sxs-lookup"><span data-stu-id="b0c53-108">The [& operator](../../../csharp/language-reference/operators/and-operator.md) performs a bitwise logical AND operation on integral operands and logical AND on `bool` operands.</span></span>  
  
 <span data-ttu-id="b0c53-109">不能直接重载 `&=` 运算符，但用户定义的类型可重载二元 [& 运算符](../../../csharp/language-reference/operators/and-operator.md)（参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="b0c53-109">The `&=` operator cannot be overloaded directly, but user-defined types can overload the binary [& operator](../../../csharp/language-reference/operators/and-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0c53-110">示例</span><span class="sxs-lookup"><span data-stu-id="b0c53-110">Example</span></span>  
 <span data-ttu-id="b0c53-111">[!code-cs[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b0c53-111">[!code-cs[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0c53-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0c53-112">See Also</span></span>  
 <span data-ttu-id="b0c53-113">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b0c53-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b0c53-114">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b0c53-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b0c53-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="b0c53-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

