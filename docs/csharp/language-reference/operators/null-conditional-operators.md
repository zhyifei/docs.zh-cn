---
title: "NULL 条件运算符（C# 和 Visual Basic）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c95b4079cf4e71c0ef9cd436ec230337f512229a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="04a91-102">NULL 条件运算符（C# 和 Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="04a91-102">Null-conditional Operators (C# and Visual Basic)</span></span>
<span data-ttu-id="04a91-103">用于在执行成员访问 (`?.`) 或索引 (`?[`) 操作之前，测试是否存在 NULL。</span><span class="sxs-lookup"><span data-stu-id="04a91-103">Used to test for null before performing a member access (`?.`) or index (`?[`) operation.</span></span>  <span data-ttu-id="04a91-104">这些运算符可帮助编写更少的代码来处理 null 检查，尤其是对于下降到数据结构。</span><span class="sxs-lookup"><span data-stu-id="04a91-104">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
```vb  
Dim length = customers?.Length  ' null if customers is null  
Dim first as Customer = customers?(0)  ' null if customers is null  
Dim count as Integer? = customers?(0)?.Orders?.Count()  ' null if customers, the first customer, or Orders is null  
```  
  
 <span data-ttu-id="04a91-105">最后一个示例演示 NULL 条件运算符会短路。</span><span class="sxs-lookup"><span data-stu-id="04a91-105">The last example demonstrates that the null-condition operators are short-circuiting.</span></span>  <span data-ttu-id="04a91-106">如果条件成员访问和索引操作链中的某个操作返回 NULL，则该链其余部分的执行将停止。</span><span class="sxs-lookup"><span data-stu-id="04a91-106">If one operation in a chain of conditional member access and index operation returns null, then the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="04a91-107">表达式中优先级较低的其他操作将继续。</span><span class="sxs-lookup"><span data-stu-id="04a91-107">Other operations with lower precedence in the expression continue.</span></span>  <span data-ttu-id="04a91-108">例如，下例中的 `E` 将在第二行中执行，且 `??` 和 `==` 操作将执行。</span><span class="sxs-lookup"><span data-stu-id="04a91-108">For example, `E` in the following executes in the second line, and the `??` and `==` operations execute.</span></span>  <span data-ttu-id="04a91-109">在第一行中，左侧的计算结果非 null 时，`??` 将短路且 `E` 不会执行。</span><span class="sxs-lookup"><span data-stu-id="04a91-109">In the first line, the `??` short circuits and `E` does not execute when the left side evaluates to non-null.</span></span>
  
```csharp
A?.B?.C?[0] ?? E  
A?.B?.C?[0] == E  
```

```vb
A?.B?.C?(0) ?? E  
A?.B?.C?(0) == E  
```  
  
 <span data-ttu-id="04a91-110">NULL 条件成员访问的另一个用途是使用非常少的代码以线程安全的方式调用委托。</span><span class="sxs-lookup"><span data-stu-id="04a91-110">Another use for the null-condition member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="04a91-111">旧方法需要如下所示的代码：</span><span class="sxs-lookup"><span data-stu-id="04a91-111">The old way requires code like the following:</span></span>  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```  
  
 <span data-ttu-id="04a91-112">新的方法是要简单得多：</span><span class="sxs-lookup"><span data-stu-id="04a91-112">The new way is much simpler:</span></span>  
  
```csharp
PropertyChanged?.Invoke(e)  
```  

```vb
PropertyChanged?.Invoke(e)
```  
  
 <span data-ttu-id="04a91-113">新方法是线程安全的，因为编译器生成的代码仅评估 `PropertyChanged` 一次，从而使结果保持在临时变量中。</span><span class="sxs-lookup"><span data-stu-id="04a91-113">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span>  
  
 <span data-ttu-id="04a91-114">你需要显式调用 `Invoke` 方法，因为不存在 NULL 条件委托调用语法 `PropertyChanged?(e)`。</span><span class="sxs-lookup"><span data-stu-id="04a91-114">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  <span data-ttu-id="04a91-115">有太多不明确的分析情况来允许它。</span><span class="sxs-lookup"><span data-stu-id="04a91-115">There were too many ambiguous parsing situations to allow it.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="04a91-116">语言规范</span><span class="sxs-lookup"><span data-stu-id="04a91-116">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 <span data-ttu-id="04a91-117">有关详细信息，请参阅 [Visual Basic 语言参考](../../../visual-basic/language-reference/index.md)。</span><span class="sxs-lookup"><span data-stu-id="04a91-117">For more information, see the [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a91-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04a91-118">See Also</span></span>  
 [<span data-ttu-id="04a91-119">??（null 合并运算符）</span><span class="sxs-lookup"><span data-stu-id="04a91-119">?? (null-coalescing operator)</span></span>](null-conditional-operator.md)  
 [<span data-ttu-id="04a91-120">C# 参考</span><span class="sxs-lookup"><span data-stu-id="04a91-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="04a91-121">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="04a91-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="04a91-122">Visual Basic 语言参考</span><span class="sxs-lookup"><span data-stu-id="04a91-122">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
 [<span data-ttu-id="04a91-123">Visual Basic 编程指南</span><span class="sxs-lookup"><span data-stu-id="04a91-123">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
