---
title: "! 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '!_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
caps.latest.revision: 13
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
ms.openlocfilehash: a040af8724240258b74a39c937a6a321499c3447
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="30ffd-103">!</span><span class="sxs-lookup"><span data-stu-id="30ffd-103">!</span></span> <span data-ttu-id="30ffd-104">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="30ffd-104">Operator (C# Reference)</span></span>
<span data-ttu-id="30ffd-105">逻辑非运算符 (`!`) 是一种否定其操作数的一元运算符。</span><span class="sxs-lookup"><span data-stu-id="30ffd-105">The logical negation operator (`!`) is a unary operator that negates its operand.</span></span> <span data-ttu-id="30ffd-106">它针对 `bool` 定义，当且仅当其操作数为 `false` 时返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="30ffd-106">It is defined for `bool` and returns `true` if and only if its operand is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30ffd-107">备注</span><span class="sxs-lookup"><span data-stu-id="30ffd-107">Remarks</span></span>  
 <span data-ttu-id="30ffd-108">用户定义的类型可以重载 `!` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="30ffd-108">User-defined types can overload the `!` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="30ffd-109">示例</span><span class="sxs-lookup"><span data-stu-id="30ffd-109">Example</span></span>  
 <span data-ttu-id="30ffd-110">[!code-cs[csRefOperators#7](../../../csharp/language-reference/operators/codesnippet/CSharp/logical-negation-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="30ffd-110">[!code-cs[csRefOperators#7](../../../csharp/language-reference/operators/codesnippet/CSharp/logical-negation-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30ffd-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30ffd-111">See Also</span></span>  
 <span data-ttu-id="30ffd-112">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="30ffd-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="30ffd-113">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="30ffd-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="30ffd-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="30ffd-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

