---
title: NULL 条件运算符 - C# 参考
ms.custom: seodec18
ms.date: 04/03/2015
helpviewer_keywords:
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: 38298cded904cbfedeaf3c6b66c74d610d714902
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333234"
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="500b9-102">?.</span><span class="sxs-lookup"><span data-stu-id="500b9-102">?.</span></span> <span data-ttu-id="500b9-103">和 ?[] NULL 条件运算符（C# 和 Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="500b9-103">and ?[] null-conditional operators (C# and Visual Basic)</span></span>

<span data-ttu-id="500b9-104">执行成员访问 (`?.`) 或索引 (`?[]`) 操作之前，测试左侧操作数的值为 null，如果左侧操作数计算结果为 `null`，则返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="500b9-104">Tests the value of the left-hand operand for null before performing a member access (`?.`) or index (`?[]`) operation; returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="500b9-105">这些运算符可帮助编写更少的代码来处理 null 检查，尤其是对于下降到数据结构。</span><span class="sxs-lookup"><span data-stu-id="500b9-105">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>

```csharp
int? length = customers?.Length; // null if customers is null
Customer first = customers?[0];  // null if customers is null
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null
```

<span data-ttu-id="500b9-106">NULL 条件运算符采用最小化求值策略。</span><span class="sxs-lookup"><span data-stu-id="500b9-106">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="500b9-107">如果条件成员访问和索引操作链中的某个操作返回 NULL，则该链其余部分的执行将停止。</span><span class="sxs-lookup"><span data-stu-id="500b9-107">If one operation in a chain of conditional member access and index operations returns null, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="500b9-108">在下面的示例中，如果 `A`、`B` 或 `C` 的计算结果为 NULL，就不会执行 `E`。</span><span class="sxs-lookup"><span data-stu-id="500b9-108">In the following example, `E` doesn't execute if `A`, `B`, or `C` evaluates to null.</span></span>

```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

<span data-ttu-id="500b9-109">NULL 条件成员访问的另一个用途是使用非常少的代码以线程安全的方式调用委托。</span><span class="sxs-lookup"><span data-stu-id="500b9-109">Another use for the null-conditional member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="500b9-110">旧方法需要如下所示的代码：</span><span class="sxs-lookup"><span data-stu-id="500b9-110">The old way requires code like the following:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
    handler(…);
```

<span data-ttu-id="500b9-111">新的方法是要简单得多：</span><span class="sxs-lookup"><span data-stu-id="500b9-111">The new way is much simpler:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="500b9-112">新方法是线程安全的，因为编译器生成的代码仅评估 `PropertyChanged` 一次，从而使结果保持在临时变量中。</span><span class="sxs-lookup"><span data-stu-id="500b9-112">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="500b9-113">你需要显式调用 `Invoke` 方法，因为不存在 NULL 条件委托调用语法 `PropertyChanged?(e)`。</span><span class="sxs-lookup"><span data-stu-id="500b9-113">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>

## <a name="language-specifications"></a><span data-ttu-id="500b9-114">语言规范</span><span class="sxs-lookup"><span data-stu-id="500b9-114">Language specifications</span></span>

<span data-ttu-id="500b9-115">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的 [null 条件运算符](~/_csharplang/spec/expressions.md#null-conditional-operator)。</span><span class="sxs-lookup"><span data-stu-id="500b9-115">For more information, see [Null-conditional operator](~/_csharplang/spec/expressions.md#null-conditional-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="500b9-116">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="500b9-116">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="500b9-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="500b9-117">See also</span></span>

- [<span data-ttu-id="500b9-118">??（空合运算符）</span><span class="sxs-lookup"><span data-stu-id="500b9-118">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="500b9-119">C# 参考</span><span class="sxs-lookup"><span data-stu-id="500b9-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="500b9-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="500b9-120">C# Programming Guide</span></span>](../../programming-guide/index.md)