---
title: NULL 条件运算符（C# 和 Visual Basic）
ms.date: 04/03/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- null-conditional operators [C#]
- null-conditional operators [Visual Basic]
- ?. operator [C#]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3ffeaa3c2088d0bb2c000704cfe312b0f9453b68
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="912cd-102">?.</span><span class="sxs-lookup"><span data-stu-id="912cd-102">?.</span></span> <span data-ttu-id="912cd-103">和 ?[] NULL 条件运算符（C# 和 Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="912cd-103">and ?[] null-conditional Operators (C# and Visual Basic)</span></span>
<span data-ttu-id="912cd-104">用于在执行成员访问 (`?.`) 或索引 (`?[]`) 操作之前，测试是否存在 NULL。</span><span class="sxs-lookup"><span data-stu-id="912cd-104">Used to test for null before performing a member access (`?.`) or index (`?[]`) operation.</span></span>  <span data-ttu-id="912cd-105">这些运算符可帮助编写更少的代码来处理 null 检查，尤其是对于下降到数据结构。</span><span class="sxs-lookup"><span data-stu-id="912cd-105">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>  
  
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
  
 <span data-ttu-id="912cd-106">NULL 条件运算符采用最小化求值策略。</span><span class="sxs-lookup"><span data-stu-id="912cd-106">The null-condition operators are short-circuiting.</span></span>  <span data-ttu-id="912cd-107">如果条件成员访问和索引操作链中的某个操作返回 NULL，则该链其余部分的执行将停止。</span><span class="sxs-lookup"><span data-stu-id="912cd-107">If one operation in a chain of conditional member access and index operation returns null, then the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="912cd-108">在下面的示例中，如果 `A`、`B` 或 `C` 的计算结果为 NULL，就不会执行 `E`。</span><span class="sxs-lookup"><span data-stu-id="912cd-108">In the following example, `E` doesn't execute if `A`, `B`, or `C` evaluates to null.</span></span>
  
```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

```vb
A?.B?.C?.Do(E);
A?.B?.C?(E);
```  
  
 <span data-ttu-id="912cd-109">NULL 条件成员访问的另一个用途是使用非常少的代码以线程安全的方式调用委托。</span><span class="sxs-lookup"><span data-stu-id="912cd-109">Another use for the null-condition member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="912cd-110">旧方法需要如下所示的代码：</span><span class="sxs-lookup"><span data-stu-id="912cd-110">The old way requires code like the following:</span></span>  
  
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
  
 <span data-ttu-id="912cd-111">新的方法是要简单得多：</span><span class="sxs-lookup"><span data-stu-id="912cd-111">The new way is much simpler:</span></span>  
  
```csharp
PropertyChanged?.Invoke(e)  
```  

```vb
PropertyChanged?.Invoke(e)
```  
  
 <span data-ttu-id="912cd-112">新方法是线程安全的，因为编译器生成的代码仅评估 `PropertyChanged` 一次，从而使结果保持在临时变量中。</span><span class="sxs-lookup"><span data-stu-id="912cd-112">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span>  
  
 <span data-ttu-id="912cd-113">你需要显式调用 `Invoke` 方法，因为不存在 NULL 条件委托调用语法 `PropertyChanged?(e)`。</span><span class="sxs-lookup"><span data-stu-id="912cd-113">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="912cd-114">语言规范</span><span class="sxs-lookup"><span data-stu-id="912cd-114">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 <span data-ttu-id="912cd-115">有关详细信息，请参阅 [Visual Basic 语言参考](../../../visual-basic/language-reference/index.md)。</span><span class="sxs-lookup"><span data-stu-id="912cd-115">For more information, see the [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="912cd-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="912cd-116">See Also</span></span>  
 [<span data-ttu-id="912cd-117">??（空合运算符）</span><span class="sxs-lookup"><span data-stu-id="912cd-117">?? (null-coalescing operator)</span></span>](null-conditional-operator.md)  
 [<span data-ttu-id="912cd-118">C# 参考</span><span class="sxs-lookup"><span data-stu-id="912cd-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="912cd-119">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="912cd-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="912cd-120">Visual Basic 语言参考</span><span class="sxs-lookup"><span data-stu-id="912cd-120">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
 [<span data-ttu-id="912cd-121">Visual Basic 编程指南</span><span class="sxs-lookup"><span data-stu-id="912cd-121">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
