---
title: "false 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- false operator keyword [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
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
ms.openlocfilehash: e12de403ca31952837913fdaaa8b221986f0e5fe
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="false-operator-c-reference"></a><span data-ttu-id="18217-102">false 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="18217-102">false Operator (C# Reference)</span></span>
<span data-ttu-id="18217-103">返回 [bool](../../../csharp/language-reference/keywords/bool.md) 值 `true` 以指示操作数为 `false`，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="18217-103">Returns the [bool](../../../csharp/language-reference/keywords/bool.md) value `true` to indicate that an operand is `false` and returns `false` otherwise.</span></span>  
  
 <span data-ttu-id="18217-104">在 C# 2.0 之前，`true` 和 `false` 运算符都用于创建用户定义的可为 null 的值类型，该类型可与 `SqlBool` 等类型兼容。</span><span class="sxs-lookup"><span data-stu-id="18217-104">Prior to C# 2.0, the `true` and `false` operators were used to create user-defined nullable value types that were compatible with types such as `SqlBool`.</span></span> <span data-ttu-id="18217-105">但是，现在该语言提供对可为 null 的值类型的内置支持，并且应尽可能使用这些支持而不是重载 `true` 和 `false` 运算符。</span><span class="sxs-lookup"><span data-stu-id="18217-105">However, the language now provides built-in support for nullable value types, and whenever possible you should use those instead of overloading the `true` and `false` operators.</span></span> <span data-ttu-id="18217-106">有关详细信息，请参阅[可以为 Null 的类型](../../../csharp/programming-guide/nullable-types/index.md)。</span><span class="sxs-lookup"><span data-stu-id="18217-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="18217-107">对于可以为 null 的布尔值，表达式 `a != b` 不一定等同于 `!(a == b)`，因为两个值（或之一）可能为 null。</span><span class="sxs-lookup"><span data-stu-id="18217-107">With nullable Booleans, the expression `a != b` is not necessarily equal to `!(a == b)` because one or both of the values might be null.</span></span> <span data-ttu-id="18217-108">必须分别重载 `true` 和 `false` 运算符以正确处理表达式中的 null 值。</span><span class="sxs-lookup"><span data-stu-id="18217-108">You have to overload both the `true` and `false` operators separately to correctly handle the null values in the expression.</span></span> <span data-ttu-id="18217-109">下面的示例演示如何重载和使用 `true` 和 `false` 运算符。</span><span class="sxs-lookup"><span data-stu-id="18217-109">The following example shows how to overload and use the `true` and `false` operators.</span></span>  
  
 <span data-ttu-id="18217-110">[!code-cs[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/false-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="18217-110">[!code-cs[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/false-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="18217-111">重载 `true` 和 `false` 运算符的类型可以用于 [if](../../../csharp/language-reference/keywords/if-else.md)、[do](../../../csharp/language-reference/keywords/do.md)、[while](../../../csharp/language-reference/keywords/while.md) 和 [for](../../../csharp/language-reference/keywords/for.md) 语句以及[条件表达式](../../../csharp/language-reference/operators/conditional-operator.md)中的控制表达式。</span><span class="sxs-lookup"><span data-stu-id="18217-111">A type that overloads the `true` and `false` operators can be used for the controlling expression in [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), and [for](../../../csharp/language-reference/keywords/for.md) statements and in [conditional expressions](../../../csharp/language-reference/operators/conditional-operator.md).</span></span>  
  
 <span data-ttu-id="18217-112">如果某一类型定义运算符 `false`，则它还必须定义运算符 [true](../../../csharp/language-reference/keywords/true.md)。</span><span class="sxs-lookup"><span data-stu-id="18217-112">If a type defines operator `false`, it must also define operator [true](../../../csharp/language-reference/keywords/true.md).</span></span>  
  
 <span data-ttu-id="18217-113">类型不能直接重载条件逻辑运算符 [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) 和 [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)，但可以通过重载常规逻辑运算符及运算符 `true` 和 `false` 达到同样的效果。</span><span class="sxs-lookup"><span data-stu-id="18217-113">A type cannot directly overload the conditional logical operators [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), but an equivalent effect can be achieved by overloading the regular logical operators and operators `true` and `false`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="18217-114">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="18217-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="18217-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="18217-115">See Also</span></span>  
 <span data-ttu-id="18217-116">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="18217-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="18217-117">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="18217-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="18217-118">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="18217-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="18217-119">[C# 运算符](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="18217-119">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="18217-120">true</span><span class="sxs-lookup"><span data-stu-id="18217-120">true</span></span>](../../../csharp/language-reference/keywords/true.md)

