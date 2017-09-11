---
title: "^= 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ^=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
caps.latest.revision: 16
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
ms.openlocfilehash: 33b0dccf5031809bb4fcb73d0f7d6a344accdea3
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="e339b-102">^= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="e339b-102">^= Operator (C# Reference)</span></span>
<span data-ttu-id="e339b-103">异或赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="e339b-103">The exclusive-OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e339b-104">备注</span><span class="sxs-lookup"><span data-stu-id="e339b-104">Remarks</span></span>  
 <span data-ttu-id="e339b-105">形式如下的表达式</span><span class="sxs-lookup"><span data-stu-id="e339b-105">An expression of the form</span></span>  
  
```  
x ^= y  
```  
  
 <span data-ttu-id="e339b-106">计算结果为</span><span class="sxs-lookup"><span data-stu-id="e339b-106">is evaluated as</span></span>  
  
```  
x = x ^ y  
```  
  
 <span data-ttu-id="e339b-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="e339b-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="e339b-108">[^ 运算符](../../../csharp/language-reference/operators/xor-operator.md) 对整型操作数执行按位异或运算，对 [bool](../../../csharp/language-reference/keywords/bool.md) 操作数执行逻辑异或运算。</span><span class="sxs-lookup"><span data-stu-id="e339b-108">The [^ operator](../../../csharp/language-reference/operators/xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../../../csharp/language-reference/keywords/bool.md) operands.</span></span>  
  
 <span data-ttu-id="e339b-109">不能直接重载 ^= 运算符，但用户定义的类型可重载 [^ 运算符](../../../csharp/language-reference/operators/xor-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="e339b-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](../../../csharp/language-reference/operators/xor-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e339b-110">示例</span><span class="sxs-lookup"><span data-stu-id="e339b-110">Example</span></span>  
 <span data-ttu-id="e339b-111">[!code-cs[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e339b-111">[!code-cs[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e339b-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e339b-112">See Also</span></span>  
 <span data-ttu-id="e339b-113">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e339b-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e339b-114">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e339b-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="e339b-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="e339b-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

