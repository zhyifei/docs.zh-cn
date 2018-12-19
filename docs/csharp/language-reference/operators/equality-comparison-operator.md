---
title: == 运算符 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: c6f93be4d422fe42787e36f5b86e2cccbfc645b7
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239009"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a4b1b-102">== 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a4b1b-102">== Operator (C# Reference)</span></span>
<span data-ttu-id="a4b1b-103">对于预定义的值类型，如果其操作数的值相等，则相等运算符 (`==`) 返回 true，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="a4b1b-103">For predefined value types, the equality operator (`==`) returns true if the values of its operands are equal, `false` otherwise.</span></span> <span data-ttu-id="a4b1b-104">对于 [string](../../../csharp/language-reference/keywords/string.md) 外的引用类型，如果两个操作数引用同一对象，则 `==` 会返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="a4b1b-104">For reference types other than [string](../../../csharp/language-reference/keywords/string.md), `==` returns `true` if its two operands refer to the same object.</span></span> <span data-ttu-id="a4b1b-105">对于 `string` 类型，`==` 会比较字符串的值。</span><span class="sxs-lookup"><span data-stu-id="a4b1b-105">For the `string` type, `==` compares the values of the strings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4b1b-106">备注</span><span class="sxs-lookup"><span data-stu-id="a4b1b-106">Remarks</span></span>  
 <span data-ttu-id="a4b1b-107">用户定义的值类型可以重载 `==` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="a4b1b-107">User-defined value types can overload the `==` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="a4b1b-108">用户定义的引用类型情况也相似，但是默认情况下，`==` 的行为如上述预定义和用户定义的引用类型所述。</span><span class="sxs-lookup"><span data-stu-id="a4b1b-108">So can user-defined reference types, although by default `==` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="a4b1b-109">如果已重载 `==`，则必须同时重载 [!=](../../../csharp/language-reference/operators/not-equal-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="a4b1b-109">If `==` is overloaded, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="a4b1b-110">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="a4b1b-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4b1b-111">示例</span><span class="sxs-lookup"><span data-stu-id="a4b1b-111">Example</span></span>  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a4b1b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4b1b-112">See Also</span></span>

- [<span data-ttu-id="a4b1b-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="a4b1b-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="a4b1b-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a4b1b-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a4b1b-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="a4b1b-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
